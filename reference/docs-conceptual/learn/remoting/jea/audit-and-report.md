---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Аудит и отчеты для JEA
description: Это поможет вам убедиться, что доступ к конечной точке JEA получают уполномоченные для этого люди и что назначенные им роли по-прежнему являются допустимыми.
ms.openlocfilehash: 2140d6b756ae38d82e4943c373e8a75beea30e28
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92500017"
---
# <a name="auditing-and-reporting-on-jea"></a><span data-ttu-id="5aa9c-104">Аудит и отчеты для JEA</span><span class="sxs-lookup"><span data-stu-id="5aa9c-104">Auditing and Reporting on JEA</span></span>

<span data-ttu-id="5aa9c-105">После развертывания JEA требуется регулярно проводить аудит конфигурации JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-105">After you've deployed JEA, you need to regularly audit the JEA configuration.</span></span> <span data-ttu-id="5aa9c-106">Это поможет вам убедиться, что доступ к конечной точке JEA получают уполномоченные для этого люди и что назначенные им роли по-прежнему являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-106">Auditing helps you assess that the correct people have access to the JEA endpoint and their assigned roles are still appropriate.</span></span>

## <a name="find-registered-jea-sessions-on-a-machine"></a><span data-ttu-id="5aa9c-107">Поиск зарегистрированных сеансов JEA на компьютере</span><span class="sxs-lookup"><span data-stu-id="5aa9c-107">Find registered JEA sessions on a machine</span></span>

<span data-ttu-id="5aa9c-108">Чтобы узнать, какие сеансы JEA зарегистрированы на компьютере, используйте командлет [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration).</span><span class="sxs-lookup"><span data-stu-id="5aa9c-108">To check which JEA sessions are registered on a machine, use the [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet.</span></span>

```powershell
# Filter for sessions that are configured as 'RestrictedRemoteServer' to find JEA-like session configurations
Get-PSSessionConfiguration | Where-Object { $_.SessionType -eq 'RestrictedRemoteServer' }
```

```Output
Name          : JEAMaintenance
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : CONTOSO\JEA_DNS_ADMINS AccessAllowed, CONTOSO\JEA_DNS_OPERATORS AccessAllowed,
                CONTOSO\JEA_DNS_AUDITORS AccessAllowed
```

<span data-ttu-id="5aa9c-109">Действующие права для конечной точки перечислены в свойстве **Permission**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-109">The effective rights for the endpoint are listed in the **Permission** property.</span></span> <span data-ttu-id="5aa9c-110">Эти пользователи имеют право на подключение к конечной точке JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-110">These users have the right to connect to the JEA endpoint.</span></span> <span data-ttu-id="5aa9c-111">Доступные им роли и команды определяются в свойстве **RoleDefinitions**[файла конфигурации сеанса](session-configurations.md), который использовался для регистрации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-111">However, the roles and commands they have access to is determined by the **RoleDefinitions** property in the [session configuration file](session-configurations.md) that was used to register the endpoint.</span></span> <span data-ttu-id="5aa9c-112">Вы можете оценить сопоставления ролей в зарегистрированной конечной точке JEA, развернув данные в свойстве **RoleDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-112">Expand the **RoleDefinitions** property to evaluate the role mappings in a registered JEA endpoint.</span></span>

```powershell
# Get the desired session configuration
$jea = Get-PSSessionConfiguration -Name 'JEAMaintenance'

# Enumerate users/groups and which roles they have access to
$jea.RoleDefinitions.GetEnumerator() | Select-Object Name, @{
  Name = 'Role Capabilities'
  Expression = { $_.Value.RoleCapabilities }
}
```

## <a name="find-available-role-capabilities-on-the-machine"></a><span data-ttu-id="5aa9c-113">Поиск доступных возможностей ролей на компьютере</span><span class="sxs-lookup"><span data-stu-id="5aa9c-113">Find available role capabilities on the machine</span></span>

<span data-ttu-id="5aa9c-114">JEA получает возможности ролей из `.psrc`-файлов, хранящихся в папке **RoleCapabilities** внутри модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-114">JEA gets role capabilities from the `.psrc` files stored in the **RoleCapabilities** folder inside a PowerShell module.</span></span> <span data-ttu-id="5aa9c-115">Следующая функция находит все возможности ролей, доступные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-115">The following function finds all role capabilities available on a computer.</span></span>

```powershell
function Find-LocalRoleCapability {
    $results = @()

    # Find modules with a "RoleCapabilities" subfolder and add any PSRC files to the result set
    Get-Module -ListAvailable | ForEach-Object {
        $psrcpath = Join-Path -Path $_.ModuleBase -ChildPath 'RoleCapabilities'
        if (Test-Path $psrcpath) {
            $results += Get-ChildItem -Path $psrcpath -Filter *.psrc
        }
    }

    # Format the results nicely to make it easier to read
    $results | Select-Object @{ Name = 'Name'; Expression = { $_.Name.TrimEnd('.psrc') }}, @{
        Name = 'Path'; Expression = { $_.FullName }
    } | Sort-Object Name
}
```

> [!NOTE]
> <span data-ttu-id="5aa9c-116">Порядок результатов, получаемых из этой функции, необязательно соответствует порядку, в котором будут выбираться возможности ролей, когда несколько возможностей ролей имеют одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-116">The order of results from this function is not necessarily the order in which the role capabilities will be selected if multiple role capabilities share the same name.</span></span>

## <a name="check-effective-rights-for-a-specific-user"></a><span data-ttu-id="5aa9c-117">Проверка действующих прав для конкретного пользователя</span><span class="sxs-lookup"><span data-stu-id="5aa9c-117">Check effective rights for a specific user</span></span>

<span data-ttu-id="5aa9c-118">Командлет [Get-PSSessionCapability](/powershell/module/microsoft.powershell.core/Get-PSSessionCapability) перечисляет все команды, доступные на конечной точке JEA, в зависимости от членства пользователя в группах.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-118">The [Get-PSSessionCapability](/powershell/module/microsoft.powershell.core/Get-PSSessionCapability) cmdlet enumerates all the commands available on a JEA endpoint based on a user's group memberships.</span></span>
<span data-ttu-id="5aa9c-119">Выходные данные `Get-PSSessionCapability` идентичны данным для указанного пользователя, запустившего `Get-Command -CommandType All` в сеансе JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-119">The output of `Get-PSSessionCapability` is identical to that of the specified user running `Get-Command -CommandType All` in a JEA session.</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName 'JEAMaintenance' -Username 'CONTOSO\Alice'
```

<span data-ttu-id="5aa9c-120">Если пользователи не являются постоянными членами групп, предоставляющих им дополнительные права JEA, этот командлет может не отражать такие дополнительные разрешения.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-120">If your users aren't permanent members of groups that would grant them additional JEA rights, this cmdlet may not reflect those extra permissions.</span></span> <span data-ttu-id="5aa9c-121">Такое происходит, когда с помощью систем управления привилегированным доступом JIT реализуется временная принадлежность пользователей к группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-121">This happens when using just-in-time privileged access management systems to allow users to temporarily belong to a security group.</span></span> <span data-ttu-id="5aa9c-122">Тщательно оцените сопоставление пользователей с ролями и возможностями, чтобы убедиться, что пользователи получают только уровень доступа, необходимый для успешного выполнения поставленных задач.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-122">Carefully evaluate the mapping of users to roles and capabilities to ensure that users only get the level of access needed to do their jobs successfully.</span></span>

## <a name="powershell-event-logs"></a><span data-ttu-id="5aa9c-123">Журналы событий PowerShell</span><span class="sxs-lookup"><span data-stu-id="5aa9c-123">PowerShell event logs</span></span>

<span data-ttu-id="5aa9c-124">Если в системе включено ведение журнала для модуля или блока сценария, в журнале событий Windows можно найти события для каждой команды, которую пользователь выполнял в своих сеансах JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-124">If you enabled module or script block logging on the system, you can see events in the Windows event logs for each command a user runs in a JEA session.</span></span> <span data-ttu-id="5aa9c-125">Чтобы найти эти события, откройте журнал событий **Microsoft-Windows-PowerShell/Operational** и найдите события с идентификатором **4104**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-125">To find these events, open **Microsoft-Windows-PowerShell/Operational** event log and look for events with event ID **4104**.</span></span>

<span data-ttu-id="5aa9c-126">Каждая запись журнала событий содержит сведения о сеансе, в котором была запущена команда.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-126">Each event log entry includes information about the session in which the command was run.</span></span> <span data-ttu-id="5aa9c-127">Для сеансов JEA событие включает сведения о **ConnectedUser** и **RunAsUser**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-127">For JEA sessions, the event includes information about the **ConnectedUser** and the **RunAsUser**.</span></span> <span data-ttu-id="5aa9c-128">**ConnectedUser** является фактическим пользователем, создавшим сеанс JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-128">The **ConnectedUser** is the actual user who created the JEA session.</span></span> <span data-ttu-id="5aa9c-129">Учетная запись **RunAsUser** используется JEA для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-129">The **RunAsUser** is the account JEA used to execute the command.</span></span>

<span data-ttu-id="5aa9c-130">Журналы событий приложений показывают изменения, внесенные от имени **RunAsUser**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-130">Application event logs show changes being made by the **RunAsUser**.</span></span> <span data-ttu-id="5aa9c-131">Поэтому включение журнала модулей и скриптов является обязательным для трассировки вызова определенных команд обратно к **ConnectedUser**.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-131">So having module and script logging enabled is required to trace a specific command invocation back to the **ConnectedUser**.</span></span>

## <a name="application-event-logs"></a><span data-ttu-id="5aa9c-132">Журналы событий приложений</span><span class="sxs-lookup"><span data-stu-id="5aa9c-132">Application event logs</span></span>

<span data-ttu-id="5aa9c-133">Команды, которые выполняются в рамках сеанса JEA и взаимодействуют с внешними приложениями или службами, могут записывать события в собственные журналы.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-133">Commands run in a JEA session that interact with external applications or services may log events to their own event logs.</span></span> <span data-ttu-id="5aa9c-134">В отличие от журналов и записей PowerShell, другие механизмы ведения журнала не записывают действия подключенного пользователя сеанса JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-134">Unlike PowerShell logs and transcripts, other logging mechanisms don't capture the connected user of the JEA session.</span></span> <span data-ttu-id="5aa9c-135">Вместо этого эти приложения записывают только виртуальную учетную запись пользователя запуска от имени.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-135">Instead, those applications only log the virtual run-as user.</span></span>
<span data-ttu-id="5aa9c-136">Чтобы определить, кем выполнена команда, требуется просмотреть [запись сеанса](#session-transcripts) или сопоставлять журналы событий PowerShell с временем и пользователем, указанными в журнале событий приложений.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-136">To determine who ran the command, you need to consult a [session transcript](#session-transcripts) or correlate PowerShell event logs with the time and user shown in the application event log.</span></span>

<span data-ttu-id="5aa9c-137">Журнал WinRM может помочь сопоставить пользователей, от имени которых выполняется запуск, в журнале событий приложения с подключающимся пользователем.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-137">The WinRM log can also help you correlate run-as users to the connecting user in an application event log.</span></span> <span data-ttu-id="5aa9c-138">Событие с идентификатором **193** в журнале **Microsoft-Windows-Windows Remote Management/Operational** регистрирует идентификатор безопасности (SID) и имя учетной записи как для подключающегося пользователя, так и для пользователя, от имени которого выполняется запуск, при каждом создании сеанса JEA.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-138">Event ID **193** in the **Microsoft-Windows-Windows Remote Management/Operational** log records the security identifier (SID) and account name for both the connecting user and run as user for every new JEA session.</span></span>

## <a name="session-transcripts"></a><span data-ttu-id="5aa9c-139">Записи сеансов</span><span class="sxs-lookup"><span data-stu-id="5aa9c-139">Session transcripts</span></span>

<span data-ttu-id="5aa9c-140">Если вы настроили JEA для создания записи для каждого сеанса пользователя, в указанной папке будет храниться текстовая копия перечня всех действий каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-140">If you configured JEA to create a transcript for each user session, a text copy of every user's actions are stored in the specified folder.</span></span>

<span data-ttu-id="5aa9c-141">Следующая команда (от имени администратора) находит все каталоги записей.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-141">The following command (as an administrator) finds all transcript directories.</span></span>

```powershell
Get-PSSessionConfiguration |
  Where-Object { $_.TranscriptDirectory -ne $null } |
    Format-Table Name, TranscriptDirectory
```

<span data-ttu-id="5aa9c-142">Каждая запись начинается со сведений о том, когда запущен сеанс, какой пользователь подключился к нему и какое удостоверение JEA было им присвоено.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-142">Each transcript starts with information about the time the session started, which user connected to the session, and which JEA identity was assigned to them.</span></span>

```
**********************
Windows PowerShell transcript start
Start time: 20160710144736
Username: CONTOSO\Alice
RunAs User: WinRM Virtual Users\WinRM VA_1_CONTOSO_Alice
Machine: SERVER01 (Microsoft Windows NT 10.0.14393.0)
[...]
```

<span data-ttu-id="5aa9c-143">В основной части записи регистрируются сведения о каждой из вызванных пользователем команд.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-143">The body of the transcript contains information about each command the user invoked.</span></span> <span data-ttu-id="5aa9c-144">Точный синтаксис команды, использованной в сеансах JEA, недоступен из-за способа преобразования команд для удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-144">The exact syntax of the command used is unavailable in JEA sessions because of the way commands are transformed for PowerShell remoting.</span></span> <span data-ttu-id="5aa9c-145">Тем не менее, все же можно определить, какая была выполнена команда.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-145">However, you can still determine the effective command that was executed.</span></span> <span data-ttu-id="5aa9c-146">Ниже приведен пример фрагмента записи для пользователя, запускающего `Get-Service Dns` в сеансе JEA:</span><span class="sxs-lookup"><span data-stu-id="5aa9c-146">Below is an example transcript snippet from a user running `Get-Service Dns` in a JEA session:</span></span>

```
PS>CommandInvocation(Get-Service): "Get-Service"
>> ParameterBinding(Get-Service): name="Name"; value="Dns"
>> CommandInvocation(Out-Default): "Out-Default"
>> ParameterBinding(Out-Default): name="InputObject"; value="Dns"

Running  Dns                DNS Server
```

<span data-ttu-id="5aa9c-147">Строка **CommandInvocation** записывается для каждой команды, которую запускает пользователь.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-147">A **CommandInvocation** line is written for each command a user runs.</span></span> <span data-ttu-id="5aa9c-148">В **ParameterBindings** записывается каждый параметр и значение, указанное с помощью команды.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-148">**ParameterBindings** record each parameter and value supplied with the command.</span></span> <span data-ttu-id="5aa9c-149">В приведенном выше примере можно заметить, что параметр **Name** получил значение **Dns** для командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-149">In the previous example, you can see that the parameter **Name** was supplied the with value **Dns** for the `Get-Service` cmdlet.</span></span>

<span data-ttu-id="5aa9c-150">Выходные данные каждой команды также вызывают **CommandInvocation**, обычно `Out-Default`.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-150">The output of each command also triggers a **CommandInvocation**, usually to `Out-Default`.</span></span> <span data-ttu-id="5aa9c-151">**InputObject** в `Out-Default` представляет собой объект PowerShell, возвращаемый из команды.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-151">The **InputObject** of `Out-Default` is the PowerShell object returned from the command.</span></span> <span data-ttu-id="5aa9c-152">Сведения об этом объекте выводятся несколькими строчками ниже, в точности имитируя то, что увидел бы пользователь.</span><span class="sxs-lookup"><span data-stu-id="5aa9c-152">The details of that object are printed a few lines below, closely mimicking what the user would have seen.</span></span>

## <a name="see-also"></a><span data-ttu-id="5aa9c-153">См. также</span><span class="sxs-lookup"><span data-stu-id="5aa9c-153">See also</span></span>

[<span data-ttu-id="5aa9c-154">Запись блога *PowerShell ♥ the Blue Team* по безопасности</span><span class="sxs-lookup"><span data-stu-id="5aa9c-154">*PowerShell ♥ the Blue Team* blog post on security</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
