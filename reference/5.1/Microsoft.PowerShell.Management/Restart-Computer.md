---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229797"
---
# <span data-ttu-id="66990-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="66990-103">Restart-Computer</span></span>

## <span data-ttu-id="66990-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="66990-104">SYNOPSIS</span></span>
<span data-ttu-id="66990-105">Перезапускает операционную систему на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="66990-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="66990-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66990-106">SYNTAX</span></span>

### <span data-ttu-id="66990-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="66990-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66990-108">асжобсет</span><span class="sxs-lookup"><span data-stu-id="66990-108">AsJobSet</span></span>

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66990-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66990-109">DESCRIPTION</span></span>

<span data-ttu-id="66990-110">`Restart-Computer`Командлет перезапускает операционную систему на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="66990-110">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="66990-111">Параметры можно использовать `Restart-Computer` для запуска операций перезапуска в качестве фонового задания, для указания уровней проверки подлинности и альтернативных учетных данных, для ограничения операций, выполняемых одновременно, и для принудительной перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="66990-111">You can use the parameters of `Restart-Computer` to run the restart operations as a background job, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="66990-112">Начиная с Windows PowerShell 3,0, перед выполнением следующей команды можно дождаться завершения перезапуска.</span><span class="sxs-lookup"><span data-stu-id="66990-112">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="66990-113">Укажите время ожидания и интервал запроса, а также дождитесь доступности определенных служб на перезагруженном компьютере.</span><span class="sxs-lookup"><span data-stu-id="66990-113">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="66990-114">Эта функция делает ее практичной для использования `Restart-Computer` в скриптах и функциях.</span><span class="sxs-lookup"><span data-stu-id="66990-114">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

<span data-ttu-id="66990-115">Для перезагрузки компьютера можно использовать протокол WS-Management (WSMan). в случае блокировки вызовов DCOM блокируются, например, брандмауэром предприятия.</span><span class="sxs-lookup"><span data-stu-id="66990-115">You can use the WS-Management (WSMan) protocol to restart the computer, in case Distributed Component Object Model (DCOM) calls are blocked, such as by an enterprise firewall.</span></span> <span data-ttu-id="66990-116">Дополнительные сведения см. в разделе [протокол WS-Management](/windows/desktop/WinRM/ws-management-protocol).</span><span class="sxs-lookup"><span data-stu-id="66990-116">For more information, see [WS-Management Protocol](/windows/desktop/WinRM/ws-management-protocol).</span></span>

<span data-ttu-id="66990-117">Этому командлету удаленное взаимодействие Windows PowerShell необходимо только при использовании параметра **AsJob**.</span><span class="sxs-lookup"><span data-stu-id="66990-117">This cmdlet requires Windows PowerShell remoting only when you use the **AsJob** parameter in a command.</span></span>

## <span data-ttu-id="66990-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="66990-118">EXAMPLES</span></span>

### <span data-ttu-id="66990-119">Пример 1. перезапуск локального компьютера</span><span class="sxs-lookup"><span data-stu-id="66990-119">Example 1: Restart the local computer</span></span>

<span data-ttu-id="66990-120">`Restart-Computer` перезапускает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="66990-120">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="66990-121">Пример 2. перезапуск нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="66990-121">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="66990-122">`Restart-Computer` может перезапустить удаленный и локальный компьютеры.</span><span class="sxs-lookup"><span data-stu-id="66990-122">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="66990-123">Параметр **ComputerName** принимает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-123">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="66990-124">Пример 3. перезапуск компьютеров в качестве фонового задания</span><span class="sxs-lookup"><span data-stu-id="66990-124">Example 3: Restart computers as a background job</span></span>

<span data-ttu-id="66990-125">Эти команды выполняют `Restart-Computer` команду в качестве фонового задания на двух удаленных компьютерах, а затем получают результаты.</span><span class="sxs-lookup"><span data-stu-id="66990-125">These commands run a `Restart-Computer` command as a background job on two remote computers, and then get the results.</span></span>

<span data-ttu-id="66990-126">Поскольку функция **AsJob** создает задание на локальном компьютере и автоматически возвращает результаты на локальный компьютер, можно выполнить `Receive-Job` локальную команду.</span><span class="sxs-lookup"><span data-stu-id="66990-126">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

<span data-ttu-id="66990-127">`Restart-Computer` использует параметр **ComputerName** для указания **Server01** и **Server02**.</span><span class="sxs-lookup"><span data-stu-id="66990-127">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** and **Server02**.</span></span> <span data-ttu-id="66990-128">Параметр **AsJob** выполняет команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="66990-128">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="66990-129">Объект задания хранится в `$Job` переменной.</span><span class="sxs-lookup"><span data-stu-id="66990-129">The job object is stored in the `$Job` variable.</span></span> <span data-ttu-id="66990-130">`$Job` отправляется по конвейеру в `Receive-Job` командлет, который получает результаты.</span><span class="sxs-lookup"><span data-stu-id="66990-130">`$Job` is sent down the pipeline to the `Receive-Job` cmdlet that gets the results.</span></span>

### <span data-ttu-id="66990-131">Пример 4. перезапуск удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="66990-131">Example 4: Restart a remote computer</span></span>

<span data-ttu-id="66990-132">`Restart-Computer` перезапускает удаленный компьютер с настроенными параметрами олицетворения и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="66990-132">`Restart-Computer` restarts a remote computer with customized impersonation and authentication settings.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="66990-133">`Restart-Computer` использует параметр **ComputerName** для указания **Server01**.</span><span class="sxs-lookup"><span data-stu-id="66990-133">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="66990-134">Параметр **олицетворения** указывает Anonymous, чтобы скрыть удостоверение инициатора запроса.</span><span class="sxs-lookup"><span data-stu-id="66990-134">The **Impersonation** parameter specifies Anonymous to hide the requester's identity.</span></span> <span data-ttu-id="66990-135">Параметр **дкомаусентикатион** указывает паккетинтегрити в качестве уровня проверки подлинности соединения.</span><span class="sxs-lookup"><span data-stu-id="66990-135">The **DcomAuthentication** parameter specifies PacketIntegrity as the connection's authentication level.</span></span>

### <span data-ttu-id="66990-136">Пример 5. принудительный перезапуск компьютеров, перечисленных в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="66990-136">Example 5: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="66990-137">В этом примере выполняется принудительная перезагрузка компьютеров, перечисленных в `Domain01.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="66990-137">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="66990-138">Имена компьютеров из текстового файла хранятся в переменной.</span><span class="sxs-lookup"><span data-stu-id="66990-138">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="66990-139">Параметр **Force** принудительно вызывает немедленный перезапуск, а параметр **ThrottleLimit** ограничивает количество одновременных подключений.</span><span class="sxs-lookup"><span data-stu-id="66990-139">The **Force** parameter forces an immediate restart and the **ThrottleLimit** parameter limits the number of concurrent connections.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

<span data-ttu-id="66990-140">`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**.</span><span class="sxs-lookup"><span data-stu-id="66990-140">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="66990-141">Имена компьютеров хранятся в переменной `$Names` .</span><span class="sxs-lookup"><span data-stu-id="66990-141">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="66990-142">`Get-Credential` запрашивает имя пользователя и пароль и сохраняет значения в переменной `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="66990-142">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="66990-143">`Restart-Computer` использует параметры **ComputerName** и **Credential** с их переменными.</span><span class="sxs-lookup"><span data-stu-id="66990-143">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="66990-144">Параметр **Force** приводит к немедленному перезапуску каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-144">The **Force** parameter causes an immediate restart of each computer.</span></span> <span data-ttu-id="66990-145">Параметр **ThrottleLimit** ограничивает команду до 10 одновременных подключений.</span><span class="sxs-lookup"><span data-stu-id="66990-145">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span>

### <span data-ttu-id="66990-146">Пример 6. перезапуск удаленного компьютера и ожидание PowerShell</span><span class="sxs-lookup"><span data-stu-id="66990-146">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="66990-147">`Restart-Computer` перезапускает удаленный компьютер, после чего ждет до 5 минут (300 секунд), чтобы PowerShell был доступен на перезагруженном компьютере, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="66990-147">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="66990-148">`Restart-Computer` использует параметр **ComputerName** для указания **Server01**.</span><span class="sxs-lookup"><span data-stu-id="66990-148">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="66990-149">Параметр **Wait** ожидает завершения перезапуска.</span><span class="sxs-lookup"><span data-stu-id="66990-149">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="66990-150">**Для** указывает, что PowerShell может выполнять команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="66990-150">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="66990-151">Параметр **timeout** задает время ожидания в пять минут.</span><span class="sxs-lookup"><span data-stu-id="66990-151">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="66990-152">Параметр **delay** запрашивает удаленный компьютер каждые две секунды, чтобы определить, перезапущен ли он.</span><span class="sxs-lookup"><span data-stu-id="66990-152">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="66990-153">Пример 7. перезагрузка компьютера с помощью протокола WSMan</span><span class="sxs-lookup"><span data-stu-id="66990-153">Example 7: Restart a computer by using the WSMan Protocol</span></span>

<span data-ttu-id="66990-154">`Restart-Computer` перезапускает удаленный компьютер с помощью протокола WSMan, а не по умолчанию, DCOM.</span><span class="sxs-lookup"><span data-stu-id="66990-154">`Restart-Computer` restarts the remote computer by using the WSMan protocol instead of the default, DCOM.</span></span> <span data-ttu-id="66990-155">Проверка подлинности Kerberos определяет, имеет ли текущий пользователь разрешение на перезапуск удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-155">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span>

<span data-ttu-id="66990-156">Эти параметры предназначены для предприятий, в которых перезапуски на основе DCOM завершаются сбоем из-за блокировки DCOM.</span><span class="sxs-lookup"><span data-stu-id="66990-156">These settings are designed for enterprises in which DCOM-based restarts fail because DCOM is blocked.</span></span> <span data-ttu-id="66990-157">Например, брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="66990-157">For example, by a firewall.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

<span data-ttu-id="66990-158">`Restart-Computer` использует параметр **ComputerName** для указания удаленного компьютера **Server01**.</span><span class="sxs-lookup"><span data-stu-id="66990-158">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="66990-159">Параметр **протокола** задает использование протокола WSMan.</span><span class="sxs-lookup"><span data-stu-id="66990-159">The **Protocol** parameter specifies to use the WSMan protocol.</span></span> <span data-ttu-id="66990-160">Параметр **всманаусентикатион** указывает метод проверки подлинности **Kerberos**.</span><span class="sxs-lookup"><span data-stu-id="66990-160">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="66990-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66990-161">PARAMETERS</span></span>

### <span data-ttu-id="66990-162">-AsJob</span><span class="sxs-lookup"><span data-stu-id="66990-162">-AsJob</span></span>

<span data-ttu-id="66990-163">Указывает, что `Restart-Computer` выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="66990-163">Indicates that `Restart-Computer` runs as a background job.</span></span>

<span data-ttu-id="66990-164">Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="66990-164">To use this parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="66990-165">В Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="66990-165">On Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as Administrator** option.</span></span> <span data-ttu-id="66990-166">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66990-166">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="66990-167">При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="66990-167">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="66990-168">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="66990-168">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="66990-169">Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="66990-169">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="66990-170">Чтобы управлять заданием, используйте командлеты **Job**.</span><span class="sxs-lookup"><span data-stu-id="66990-170">To manage the job, use the **Job** cmdlets.</span></span> <span data-ttu-id="66990-171">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="66990-171">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="66990-172">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="66990-172">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="66990-173">-ComputerName</span></span>

<span data-ttu-id="66990-174">Указывает одно имя компьютера или разделенный запятыми массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-174">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="66990-175">`Restart-Computer` принимает объекты **ComputerName** из конвейера или переменных.</span><span class="sxs-lookup"><span data-stu-id="66990-175">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="66990-176">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-176">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="66990-177">Чтобы указать локальный компьютер, введите имя компьютера, точку `.` или localhost.</span><span class="sxs-lookup"><span data-stu-id="66990-177">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="66990-178">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66990-178">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="66990-179">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="66990-179">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="66990-180">Если параметр **ComputerName** не указан, `Restart-Computer` перезапускает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="66990-180">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66990-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="66990-181">-Credential</span></span>

<span data-ttu-id="66990-182">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="66990-182">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="66990-183">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="66990-183">The default is the current user.</span></span>

<span data-ttu-id="66990-184">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="66990-184">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="66990-185">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="66990-185">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="66990-186">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="66990-186">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="66990-187">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="66990-187">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-188">-Дкомаусентикатион</span><span class="sxs-lookup"><span data-stu-id="66990-188">-DcomAuthentication</span></span>

<span data-ttu-id="66990-189">Указывает уровень проверки подлинности, используемый для WMI-соединения.</span><span class="sxs-lookup"><span data-stu-id="66990-189">Specifies the authentication level that is used for the WMI connection.</span></span> <span data-ttu-id="66990-190">`Restart-Computer` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="66990-190">`Restart-Computer` uses WMI.</span></span>

<span data-ttu-id="66990-191">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="66990-191">Valid values are:</span></span>

- <span data-ttu-id="66990-192">**Вызов** : проверка подлинности COM на уровне вызова</span><span class="sxs-lookup"><span data-stu-id="66990-192">**Call** :            Call-level COM authentication</span></span>
- <span data-ttu-id="66990-193">**Подключение** : проверка подлинности COM на уровне подключения</span><span class="sxs-lookup"><span data-stu-id="66990-193">**Connect** :         Connect-level COM authentication</span></span>
- <span data-ttu-id="66990-194">**По умолчанию** : проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="66990-194">**Default** :         Windows Authentication</span></span>
- <span data-ttu-id="66990-195">**Нет** : нет проверки подлинности COM</span><span class="sxs-lookup"><span data-stu-id="66990-195">**None** :            No COM authentication</span></span>
- <span data-ttu-id="66990-196">**Пакет** : проверка подлинности COM на уровне пакетов.</span><span class="sxs-lookup"><span data-stu-id="66990-196">**Packet** :          Packet-level COM authentication.</span></span>
- <span data-ttu-id="66990-197">**Паккетинтегрити** : проверка подлинности COM на уровне целостности пакетов</span><span class="sxs-lookup"><span data-stu-id="66990-197">**PacketIntegrity** : Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="66990-198">**Паккетприваци** : проверка подлинности COM уровня конфиденциальности пакета.</span><span class="sxs-lookup"><span data-stu-id="66990-198">**PacketPrivacy** :   Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="66990-199">**Без изменений** : уровень проверки подлинности совпадает с предыдущей командой.</span><span class="sxs-lookup"><span data-stu-id="66990-199">**Unchanged** :       The authentication level is the same as the previous command.</span></span>

<span data-ttu-id="66990-200">Дополнительные сведения см. в разделе [перечисление аусентикатионлевел](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="66990-200">For more information, see [AuthenticationLevel Enumeration](/dotnet/api/system.management.authenticationlevel).</span></span>

<span data-ttu-id="66990-201">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-201">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-202">-Delay</span><span class="sxs-lookup"><span data-stu-id="66990-202">-Delay</span></span>

<span data-ttu-id="66990-203">Указывает частоту запросов в секундах.</span><span class="sxs-lookup"><span data-stu-id="66990-203">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="66990-204">PowerShell запрашивает службу, указанную **параметром, чтобы** определить, доступна ли служба после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-204">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="66990-205">Этот параметр допустим только вместе с параметрами **ожидания** и **для** параметров.</span><span class="sxs-lookup"><span data-stu-id="66990-205">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="66990-206">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="66990-207">Если параметр **delay** не указан, `Restart-Computer` использует 5-секундную задержку.</span><span class="sxs-lookup"><span data-stu-id="66990-207">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-208">— Для</span><span class="sxs-lookup"><span data-stu-id="66990-208">-For</span></span>

<span data-ttu-id="66990-209">Задает поведение PowerShell при ожидании доступности указанной службы или компонента после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-209">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="66990-210">Этот параметр допустим только с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="66990-210">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="66990-211">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="66990-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="66990-212">**По умолчанию** : ожидает перезапуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66990-212">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="66990-213">**PowerShell** : может выполнять команды в удаленном сеансе PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="66990-213">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="66990-214">**WMI** : получает ответ на запрос Win32_ComputerSystem компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-214">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="66990-215">**WinRM** : может установить удаленный сеанс для компьютера с помощью WS-Management.</span><span class="sxs-lookup"><span data-stu-id="66990-215">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="66990-216">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-217">-Force</span><span class="sxs-lookup"><span data-stu-id="66990-217">-Force</span></span>

<span data-ttu-id="66990-218">Вызывает немедленную перезагрузку компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-218">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-219">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="66990-219">-Impersonation</span></span>

<span data-ttu-id="66990-220">Задает уровень олицетворения, используемый этим командлетом для вызова WMI.</span><span class="sxs-lookup"><span data-stu-id="66990-220">Specifies the impersonation level that this cmdlet uses to call WMI.</span></span> <span data-ttu-id="66990-221">`Restart-Computer` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="66990-221">`Restart-Computer` uses WMI.</span></span>
<span data-ttu-id="66990-222">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="66990-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="66990-223">**По умолчанию** : олицетворение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66990-223">**Default** : Default impersonation.</span></span> <span data-ttu-id="66990-224">Несмотря на имя, это не значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66990-224">Despite the name, this isn't the default value.</span></span>
- <span data-ttu-id="66990-225">**Anonymous** : скрывает удостоверение вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="66990-225">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="66990-226">**Identify** : позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="66990-226">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="66990-227">**Impersonate** : позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="66990-227">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-228">-Protocol</span><span class="sxs-lookup"><span data-stu-id="66990-228">-Protocol</span></span>

<span data-ttu-id="66990-229">Указывает, какой протокол следует использовать для перезагрузки компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-229">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="66990-230">Допустимые значения: **WSMan** и **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="66990-230">The valid values are **WSMan** and **DCOM**.</span></span>

<span data-ttu-id="66990-231">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-232">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="66990-232">-ThrottleLimit</span></span>

<span data-ttu-id="66990-233">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="66990-233">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="66990-234">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="66990-234">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="66990-235">Если параметр **ThrottleLimit** не указан или используется значение 0, `Restart-Computer` использует не более 32 одновременных подключений.</span><span class="sxs-lookup"><span data-stu-id="66990-235">If the **ThrottleLimit** parameter isn't specified or a value of 0 is used, `Restart-Computer` uses a maximum of 32 concurrent connections.</span></span>

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-236">-Timeout</span><span class="sxs-lookup"><span data-stu-id="66990-236">-Timeout</span></span>

<span data-ttu-id="66990-237">Указывает время ожидания в секундах.</span><span class="sxs-lookup"><span data-stu-id="66990-237">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="66990-238">По истечении времени ожидания `Restart-Computer` возвращает в командную строку, даже если компьютеры не перезапускаются.</span><span class="sxs-lookup"><span data-stu-id="66990-238">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="66990-239">Параметр **timeout** допустим только с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="66990-239">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="66990-240">**Время ожидания** переопределяет неопределенный период ожидания в параметре **ожидания** .</span><span class="sxs-lookup"><span data-stu-id="66990-240">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="66990-241">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-241">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-242">-Wait</span><span class="sxs-lookup"><span data-stu-id="66990-242">-Wait</span></span>

<span data-ttu-id="66990-243">`Restart-Computer` подавляет командную строку PowerShell и блокирует конвейер до перезапуска компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-243">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="66990-244">Этот параметр можно использовать в скрипте для перезагрузки компьютеров и продолжения обработки после завершения перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="66990-244">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="66990-245">Параметр **Wait** ожидает неограниченное время ожидания перезапуска компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-245">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="66990-246">Можно использовать **время ожидания** для настройки времени, а параметры **для** и **задержки** ожидают, когда определенные службы станут доступны на перезагруженных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="66990-246">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="66990-247">Параметр **Wait** недопустим при перезапуске локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="66990-247">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="66990-248">Если значение параметра **ComputerName** содержит имена удаленных компьютеров и локального компьютера, `Restart-Computer` создает неустранимую ошибку для **ожидания** на локальном компьютере, но ожидает перезапуска удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-248">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="66990-249">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-250">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="66990-250">-WsmanAuthentication</span></span>

<span data-ttu-id="66990-251">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="66990-251">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="66990-252">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66990-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="66990-253">Допустимые значения для этого параметра: " **базовый** ", " **CredSSP** ", " **по умолчанию** ", " **дайджест** ", **Kerberos** и " **согласование** ".</span><span class="sxs-lookup"><span data-stu-id="66990-253">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="66990-254">Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="66990-254">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="66990-255">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="66990-255">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="66990-256">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="66990-256">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="66990-257">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="66990-257">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66990-258">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66990-258">-Confirm</span></span>

<span data-ttu-id="66990-259">Запрашивает подтверждение перед запуском `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="66990-259">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="66990-260">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66990-260">-WhatIf</span></span>

<span data-ttu-id="66990-261">Показывает, что произойдет при `Restart-Computer` выполнении.</span><span class="sxs-lookup"><span data-stu-id="66990-261">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="66990-262">`Restart-Computer`Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="66990-262">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="66990-263">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="66990-263">CommonParameters</span></span>

<span data-ttu-id="66990-264">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66990-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66990-265">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="66990-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66990-266">Входные данные</span><span class="sxs-lookup"><span data-stu-id="66990-266">INPUTS</span></span>

### <span data-ttu-id="66990-267">System.String</span><span class="sxs-lookup"><span data-stu-id="66990-267">System.String</span></span>

<span data-ttu-id="66990-268">`Restart-Computer` принимает имена компьютеров из конвейера или переменных.</span><span class="sxs-lookup"><span data-stu-id="66990-268">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

<span data-ttu-id="66990-269">В Windows PowerShell 2.0 параметр **ComputerName** принимает входные данные из конвейера только по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="66990-269">In Windows PowerShell 2.0, the **ComputerName** parameter takes input from the pipeline only by property name.</span></span> <span data-ttu-id="66990-270">В Windows PowerShell 3,0 и более поздних версиях параметр **ComputerName** принимает входные данные из конвейера по значению.</span><span class="sxs-lookup"><span data-stu-id="66990-270">In Windows PowerShell 3.0, and later, the **ComputerName** parameter takes input from the pipeline by value.</span></span>

## <span data-ttu-id="66990-271">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="66990-271">OUTPUTS</span></span>

### <span data-ttu-id="66990-272">Нет, System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="66990-272">None, System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="66990-273">Если указан параметр **AsJob** , `Restart-Computer` возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="66990-273">If you specify the **AsJob** parameter, `Restart-Computer` returns a job object.</span></span> <span data-ttu-id="66990-274">В противном случае никаких выходных данных не создается.</span><span class="sxs-lookup"><span data-stu-id="66990-274">Otherwise, no output is generated.</span></span>

## <span data-ttu-id="66990-275">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="66990-275">NOTES</span></span>

- <span data-ttu-id="66990-276">`Restart-Computer` работает только на компьютерах под управлением Windows и требует от WinRM и инструментария WMI для завершения работы системы, включая локальную систему.</span><span class="sxs-lookup"><span data-stu-id="66990-276">`Restart-Computer` only work on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="66990-277">`Restart-Computer` использует [метод Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) класса [WIN32_OPERATINGSYSTEM](/windows/desktop/CIMWin32Prov/win32-operatingsystem) инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="66990-277">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span>  <span data-ttu-id="66990-278">Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .</span><span class="sxs-lookup"><span data-stu-id="66990-278">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="66990-279">В Windows PowerShell 2,0 параметр **AsJob** не работает надежно при перезапуске или остановке удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="66990-279">In Windows PowerShell 2.0, the **AsJob** parameter doesn't work reliably when you are restarting or stopping remote computers.</span></span> <span data-ttu-id="66990-280">В Windows PowerShell 3.0 реализация была изменена, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="66990-280">In Windows PowerShell 3.0, the implementation is changed to resolve this problem.</span></span>

## <span data-ttu-id="66990-281">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="66990-281">RELATED LINKS</span></span>

[<span data-ttu-id="66990-282">О служба удаленного управления Windows</span><span class="sxs-lookup"><span data-stu-id="66990-282">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="66990-283">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="66990-283">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="66990-284">Протокол WS-Management</span><span class="sxs-lookup"><span data-stu-id="66990-284">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
