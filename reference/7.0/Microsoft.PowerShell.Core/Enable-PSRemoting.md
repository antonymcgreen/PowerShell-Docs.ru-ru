---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 4d00b875aab2e175465b262a320e7b16893c255c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347386"
---
# <span data-ttu-id="c1fbd-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="c1fbd-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="c1fbd-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1fbd-104">SYNOPSIS</span></span>
<span data-ttu-id="c1fbd-105">Настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="c1fbd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1fbd-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c1fbd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1fbd-107">DESCRIPTION</span></span>

<span data-ttu-id="c1fbd-108">`Enable-PSRemoting`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span> <span data-ttu-id="c1fbd-109">Удаленное взаимодействие PowerShell на основе WS-Management в настоящее время поддерживается только на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-109">WS-Management based PowerShell remoting is currently supported only on Windows platform.</span></span>

<span data-ttu-id="c1fbd-110">Удаленное взаимодействие PowerShell включено по умолчанию на платформах Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-110">PowerShell remoting is enabled by default on Windows Server platforms.</span></span> <span data-ttu-id="c1fbd-111">С помощью можно `Enable-PSRemoting` включить удаленное взаимодействие PowerShell в других поддерживаемых версиях Windows и повторно включить удаленное взаимодействие, если оно будет отключено.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-111">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting if it becomes disabled.</span></span>

<span data-ttu-id="c1fbd-112">Эту команду необходимо выполнить только один раз на каждом компьютере, который будет принимать команды.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-112">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="c1fbd-113">Ее не нужно выполнять на компьютерах, которые только отправляют команды.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-113">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="c1fbd-114">Так как конфигурация запускает прослушиватели для приема удаленных подключений, целесообразно запускать ее только там, где это необходимо.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-114">Because the configuration starts listeners to accept remote connections, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="c1fbd-115">Включение удаленного взаимодействия PowerShell для клиентских версий Windows, когда компьютер находится в общедоступной сети, обычно запрещен, но это ограничение можно пропустить с помощью параметра **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="c1fbd-115">Enabling PowerShell remoting on client versions of Windows when the computer is on a public network is normally disallowed, but you can skip this restriction by using the **SkipNetworkProfileCheck** parameter.</span></span> <span data-ttu-id="c1fbd-116">Подробнее см. в описании параметра **SkipNetworkProfileCheck**.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-116">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="c1fbd-117">Несколько установок PowerShell могут существовать параллельно на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-117">Multiple PowerShell installations can exist side-by-side on a single computer.</span></span> <span data-ttu-id="c1fbd-118">`Enable-PSRemoting`При запуске будет настроена конечная точка удаленного взаимодействия для конкретной версии установки, в которой выполняется командлет.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-118">Running `Enable-PSRemoting` will configure a remoting endpoint for the specific installation version that you are running the cmdlet in.</span></span> <span data-ttu-id="c1fbd-119">Поэтому при запуске `Enable-PSRemoting` powershell 6,2 будет настроена конечная точка удаленного взаимодействия, которая запускает powershell 6,2.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-119">So if you run `Enable-PSRemoting` while running PowerShell 6.2, a remoting endpoint will be configured that runs PowerShell 6.2.</span></span> <span data-ttu-id="c1fbd-120">При запуске `Enable-PSRemoting` PowerShell 7-Preview конечная точка удаленного взаимодействия будет настроена под управлением PowerShell 7-Preview.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-120">If you run `Enable-PSRemoting` while running PowerShell 7-preview, a remoting endpoint will be configured that runs PowerShell 7-preview.</span></span>

<span data-ttu-id="c1fbd-121">`Enable-PSRemoting` При необходимости создает две конфигурации удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-121">`Enable-PSRemoting` creates two remoting endpoint configurations as needed.</span></span> <span data-ttu-id="c1fbd-122">Если конфигурации конечных точек уже существуют, они просто гарантируют их включение.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-122">If the endpoint configurations already exist, then they are simply ensured to be enabled.</span></span> <span data-ttu-id="c1fbd-123">Созданные конфигурации идентичны, но имеют разные имена.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-123">The created configurations are identical but have different names.</span></span> <span data-ttu-id="c1fbd-124">У одной из них будет простое имя, соответствующее версии PowerShell, в которой размещен сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-124">One will have a simple name corresponding to the PowerShell version that hosts the session.</span></span> <span data-ttu-id="c1fbd-125">Другое имя конфигурации содержит более подробные сведения о версии PowerShell, в которой размещен сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-125">The other configuration name contains more detailed information about the PowerShell version which hosts the session.</span></span> <span data-ttu-id="c1fbd-126">Например, при выполнении `Enable-PSRemoting` в PowerShell 6,2 вы получите две настроенные конечные точки с именем **PowerShell. 6** , **PowerShell. 6.2.2**.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-126">For example, when running `Enable-PSRemoting` in PowerShell 6.2, you will get two configured endpoints named **PowerShell.6** , **PowerShell.6.2.2**.</span></span>
<span data-ttu-id="c1fbd-127">Это позволяет создать подключение к последней версии узла PowerShell 6 с помощью простого имени **PowerShell. 6**.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-127">This allows you to create a connection to the latest PowerShell 6 host version by using the simple name **PowerShell.6**.</span></span> <span data-ttu-id="c1fbd-128">Или можно подключиться к определенной версии узла PowerShell с помощью более длинного имени **PowerShell. 6.2.2**.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-128">Or you can connect to a specific PowerShell host version by using the longer name **PowerShell.6.2.2**.</span></span>

<span data-ttu-id="c1fbd-129">Чтобы использовать только что включенные конечные точки удаленного взаимодействия, необходимо указать их по имени с помощью параметра **configurationName** при создании удаленного соединения с `Invoke-Command` помощью `New-PSSession` `Enter-PSSession` командлетов,,.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-129">To use the newly enabled remoting endpoints, you must specify them by name with the **ConfigurationName** parameter when creating a remote connection using the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.</span></span> <span data-ttu-id="c1fbd-130">Дополнительные сведения см. в примере 4.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-130">For more information, see Example 4.</span></span>

<span data-ttu-id="c1fbd-131">`Enable-PSRemoting`Командлет выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="c1fbd-131">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="c1fbd-132">Выполняет командлет [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , который выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c1fbd-132">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="c1fbd-133">Запускает службу WinRM.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-133">Starts the WinRM service.</span></span>
  - <span data-ttu-id="c1fbd-134">Задает автоматический тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-134">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="c1fbd-135">Создает прослушиватель для приема запросов по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-135">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="c1fbd-136">Включает исключение брандмауэра для WS-Management связи.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-136">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="c1fbd-137">Создает простые и длинные конфигурации конечной точки сеанса, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-137">Creates the simple and long name session endpoint configurations if needed.</span></span>
  - <span data-ttu-id="c1fbd-138">Включает все конфигурации сеансов.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-138">Enables all session configurations.</span></span>
  - <span data-ttu-id="c1fbd-139">Изменяет дескриптор безопасности всех конфигураций сеансов, чтобы разрешить удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-139">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="c1fbd-140">Перезапускает службу WinRM, чтобы внести предыдущие изменения в силу.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-140">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="c1fbd-141">Чтобы запустить этот командлет на платформе Windows, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-141">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="c1fbd-142">Этот командлет недоступен в версиях PowerShell для Linux и MacOS.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-142">This cmdlet is not available on Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="c1fbd-143">Этот командлет не влияет на конфигурации удаленных конечных точек, созданные Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-143">This cmdlet does not affect remote endpoint configurations created by Windows PowerShell.</span></span>
> <span data-ttu-id="c1fbd-144">Он влияет только на конечные точки, созданные с помощью PowerShell версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-144">It only affects endpoints created with PowerShell version 6 and greater.</span></span> <span data-ttu-id="c1fbd-145">Чтобы включить и отключить удаленные конечные точки PowerShell, размещенные в Windows PowerShell, запустите `Enable-PSRemoting` командлет из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-145">To enable and disable PowerShell remoting endpoints that are hosted by Windows PowerShell, run the `Enable-PSRemoting` cmdlet from within a Windows PowerShell session.</span></span>

## <span data-ttu-id="c1fbd-146">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1fbd-146">EXAMPLES</span></span>

### <span data-ttu-id="c1fbd-147">Пример 1. Настройка приема удаленных команд на компьютере</span><span class="sxs-lookup"><span data-stu-id="c1fbd-147">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="c1fbd-148">Эта команда настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-148">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="c1fbd-149">Пример 2. Настройка приема удаленных команд без запроса подтверждения на компьютере</span><span class="sxs-lookup"><span data-stu-id="c1fbd-149">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="c1fbd-150">Эта команда настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-150">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="c1fbd-151">Параметр **Force** подавляет запросы пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-151">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="c1fbd-152">Пример 3. Разрешение удаленного доступа для клиентов</span><span class="sxs-lookup"><span data-stu-id="c1fbd-152">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="c1fbd-153">В этом примере показано, как разрешить удаленный доступ из общедоступных сетей в клиентских версиях ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-153">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="c1fbd-154">Имя правила брандмауэра может отличаться для разных версий Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-154">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="c1fbd-155">Используйте `Get-NetFirewallRule` для просмотра списка правил.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-155">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="c1fbd-156">Перед включением правила брандмауэра просмотрите параметры безопасности в правиле, чтобы убедиться, что конфигурация подходит для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-156">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="c1fbd-157">По умолчанию `Enable-PSRemoting` создает правила сети, разрешающие удаленный доступ из частных и доменных сетей.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-157">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="c1fbd-158">В команде используется параметр **SkipNetworkProfileCheck** для разрешения удаленного доступа из общедоступных сетей в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-158">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="c1fbd-159">В команде указывается параметр **Force** , блокирующий вывод запросов подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-159">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="c1fbd-160">Параметр **SkipNetworkProfileCheck** не влияет на серверные версии операционной системы Windows, которые по умолчанию разрешают удаленный доступ из общедоступных сетей в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-160">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="c1fbd-161">`Set-NetFirewallRule`Командлет в модуле **NetSecurity** добавляет правило брандмауэра, которое разрешает удаленный доступ из общедоступных сетей из любого удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-161">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="c1fbd-162">включая расположения в других подсетях.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-162">This includes locations in different subnets.</span></span>

### <span data-ttu-id="c1fbd-163">Пример 4. Создание удаленного сеанса для вновь включенной конфигурации конечной точки</span><span class="sxs-lookup"><span data-stu-id="c1fbd-163">Example 4: Create a remote session to the newly enabled endpoint configuration</span></span>

<span data-ttu-id="c1fbd-164">В этом примере показано, как включить удаленное взаимодействие PowerShell на компьютере, найти настроенные имена конечных точек и создать удаленный сеанс для одной из конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-164">This example shows how to enable PowerShell remoting on a computer, find the configured endpoint names, and create a remote session to one of the endpoints.</span></span>

<span data-ttu-id="c1fbd-165">Первая команда включает удаленное взаимодействие PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-165">The first command enables PowerShell remoting on the computer.</span></span>

<span data-ttu-id="c1fbd-166">Вторая команда выводит список конфигураций конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-166">The second command lists the endpoint configurations.</span></span>

<span data-ttu-id="c1fbd-167">Третья команда создает удаленный сеанс PowerShell на том же компьютере, указывая конечную точку **PowerShell. 6** по имени.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-167">The third command creates a remote PowerShell session to the same machine, specifying the **PowerShell.6** endpoint by name.</span></span> <span data-ttu-id="c1fbd-168">Удаленный сеанс будет размещен в последней версии PowerShell 6 (6.2.2).</span><span class="sxs-lookup"><span data-stu-id="c1fbd-168">The remote session will be hosted with the latest PowerShell 6 version (6.2.2).</span></span>

<span data-ttu-id="c1fbd-169">Последняя команда обращается к `$PSVersionTable` переменной в удаленном сеансе, чтобы отобразить версию PowerShell, в которой размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-169">The last command accesses the `$PSVersionTable` variable in the remote session to display the PowerShell version that is hosting the session.</span></span>

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> <span data-ttu-id="c1fbd-170">Имя правила брандмауэра может отличаться в зависимости от версии Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-170">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="c1fbd-171">Используйте `Get-NetFirewallRule` командлет, чтобы вывести список имен правил в системе.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-171">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="c1fbd-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1fbd-172">PARAMETERS</span></span>

### <span data-ttu-id="c1fbd-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c1fbd-173">-Confirm</span></span>

<span data-ttu-id="c1fbd-174">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-174">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1fbd-175">-Force</span><span class="sxs-lookup"><span data-stu-id="c1fbd-175">-Force</span></span>

<span data-ttu-id="c1fbd-176">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-176">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1fbd-177">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="c1fbd-177">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="c1fbd-178">Указывает, что этот командлет включает удаленное взаимодействие в клиентских версиях ОС Windows, если компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-178">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="c1fbd-179">Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-179">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="c1fbd-180">Этот параметр не оказывает влияния на серверные версии ОС Windows, в которых для общедоступных сетей по умолчанию задано правило брандмауэра локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-180">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="c1fbd-181">Если правило брандмауэра локальной подсети отключено на версии сервера, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-181">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="c1fbd-182">Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="c1fbd-182">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="c1fbd-183">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-183">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1fbd-184">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c1fbd-184">-WhatIf</span></span>

<span data-ttu-id="c1fbd-185">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-185">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c1fbd-186">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-186">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1fbd-187">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1fbd-187">CommonParameters</span></span>

<span data-ttu-id="c1fbd-188">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1fbd-189">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1fbd-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1fbd-190">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1fbd-190">INPUTS</span></span>

### <span data-ttu-id="c1fbd-191">Нет</span><span class="sxs-lookup"><span data-stu-id="c1fbd-191">None</span></span>

<span data-ttu-id="c1fbd-192">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c1fbd-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1fbd-193">OUTPUTS</span></span>

### <span data-ttu-id="c1fbd-194">System.String</span><span class="sxs-lookup"><span data-stu-id="c1fbd-194">System.String</span></span>

<span data-ttu-id="c1fbd-195">Этот командлет возвращает строки, которые описывают результаты его выполнения.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-195">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="c1fbd-196">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1fbd-196">NOTES</span></span>

<span data-ttu-id="c1fbd-197">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-197">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="c1fbd-198">В серверных версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, разрешающих удаленный доступ, и создает правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-198">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="c1fbd-199">В клиентских версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, которые обеспечивают неограниченный удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-199">On client versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="c1fbd-200">Чтобы создать правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ из той же локальной подсети, используйте параметр **SkipNetworkProfileCheck**.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-200">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="c1fbd-201">В клиентской или серверной версиях операционной системы Windows для создания правила брандмауэра для общедоступных сетей, которое удаляет ограничение локальной подсети и разрешает удаленный доступ, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity для выполнения следующей команды: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="c1fbd-201">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="c1fbd-202">`Enable-PSRemoting` включает все конфигурации сеансов, устанавливая для свойства **Enabled** всех конфигураций сеансов значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="c1fbd-202">`Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="c1fbd-203">`Enable-PSRemoting` Удаляет параметры **Deny_All** и **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="c1fbd-203">`Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="c1fbd-204">Это обеспечивает удаленный доступ к конфигурациям сеансов, зарезервированным для локального использования.</span><span class="sxs-lookup"><span data-stu-id="c1fbd-204">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="c1fbd-205">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1fbd-205">RELATED LINKS</span></span>

[<span data-ttu-id="c1fbd-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1fbd-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="c1fbd-207">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1fbd-207">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="c1fbd-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1fbd-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="c1fbd-209">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1fbd-209">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="c1fbd-210">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1fbd-210">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="c1fbd-211">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="c1fbd-211">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="c1fbd-212">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="c1fbd-212">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="c1fbd-213">about_Remote</span><span class="sxs-lookup"><span data-stu-id="c1fbd-213">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="c1fbd-214">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="c1fbd-214">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
