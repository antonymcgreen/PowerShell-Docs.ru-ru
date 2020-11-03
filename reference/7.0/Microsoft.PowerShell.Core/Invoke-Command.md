---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: b4e065ba0055c43a0ab4475878a049e4f9fde3e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230086"
---
# <span data-ttu-id="d9c17-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d9c17-103">Invoke-Command</span></span>

## <span data-ttu-id="d9c17-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d9c17-104">SYNOPSIS</span></span>
<span data-ttu-id="d9c17-105">Выполняет команды на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="d9c17-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9c17-106">SYNTAX</span></span>

### <span data-ttu-id="d9c17-107">Необрабатываемый (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d9c17-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-108">филепасрунспаце</span><span class="sxs-lookup"><span data-stu-id="d9c17-108">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-109">Сеанс</span><span class="sxs-lookup"><span data-stu-id="d9c17-109">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-110">филепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="d9c17-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="d9c17-111">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="d9c17-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="d9c17-112">URI</span><span class="sxs-lookup"><span data-stu-id="d9c17-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-113">филепасури</span><span class="sxs-lookup"><span data-stu-id="d9c17-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-114">VMId</span><span class="sxs-lookup"><span data-stu-id="d9c17-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-115">VMName</span><span class="sxs-lookup"><span data-stu-id="d9c17-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-116">филепасвмид</span><span class="sxs-lookup"><span data-stu-id="d9c17-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-117">филепасвмнаме</span><span class="sxs-lookup"><span data-stu-id="d9c17-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-118">сшхост</span><span class="sxs-lookup"><span data-stu-id="d9c17-118">SSHHost</span></span>

```
Invoke-Command [-Port <Int32>] [-AsJob] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> -HostName <String[]> [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-119">ContainerId</span><span class="sxs-lookup"><span data-stu-id="d9c17-119">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-120">филепасконтаинерид</span><span class="sxs-lookup"><span data-stu-id="d9c17-120">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d9c17-121">сшхоссашпарам</span><span class="sxs-lookup"><span data-stu-id="d9c17-121">SSHHostHashParam</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] [-JobName <String>] [-ScriptBlock] <ScriptBlock>
 -SSHConnection <Hashtable[]> [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="d9c17-122">филепассшхост</span><span class="sxs-lookup"><span data-stu-id="d9c17-122">FilePathSSHHost</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -HostName <String[]>
 [-UserName <String>] [-KeyFilePath <String>] [-SSHTransport] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9c17-123">филепассшхоссаш</span><span class="sxs-lookup"><span data-stu-id="d9c17-123">FilePathSSHHostHash</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -SSHConnection <Hashtable[]>
 [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="d9c17-124">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d9c17-124">DESCRIPTION</span></span>

<span data-ttu-id="d9c17-125">`Invoke-Command`Командлет выполняет команды на локальном или удаленном компьютере и возвращает все выходные данные команд, включая ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9c17-125">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="d9c17-126">С помощью одной `Invoke-Command` команды можно выполнять команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-126">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="d9c17-127">Чтобы выполнить одну команду на удаленном компьютере, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-127">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="d9c17-128">Чтобы выполнить ряд связанных команд, совместно использующих данные, используйте `New-PSSession` командлет, чтобы создать **сеанс PSSession** (постоянное подключение) на удаленном компьютере, а затем используйте параметр **Session** для, `Invoke-Command` чтобы выполнить команду в **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-128">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession** .</span></span> <span data-ttu-id="d9c17-129">Чтобы выполнить команду в отключенном сеансе, используйте параметр **InDisconnectedSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-129">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="d9c17-130">Чтобы выполнить команду в фоновом задании, используйте параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-130">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="d9c17-131">Можно также использовать `Invoke-Command` на локальном компьютере в качестве команды в блоке сценария.</span><span class="sxs-lookup"><span data-stu-id="d9c17-131">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="d9c17-132">PowerShell сразу же выполняет блок сценария в дочерней области текущей области.</span><span class="sxs-lookup"><span data-stu-id="d9c17-132">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="d9c17-133">Прежде чем использовать `Invoke-Command` для запуска команд на удаленном компьютере, прочитайте [about_Remote](./About/about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-133">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="d9c17-134">Начиная с PowerShell 6,0 можно использовать Secure Shell (SSH) для установки подключения к удаленным компьютерам и вызова команд.</span><span class="sxs-lookup"><span data-stu-id="d9c17-134">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and invoke commands on remote computers.</span></span> <span data-ttu-id="d9c17-135">SSH должен быть установлен на локальном компьютере, а удаленный компьютер должен быть настроен с использованием конечной точки SSH для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-135">SSH must be installed on the local computer and the remote computer must be configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="d9c17-136">Преимуществом удаленного сеанса PowerShell на основе SSH является то, что он работает на нескольких платформах (Windows, Linux, macOS).</span><span class="sxs-lookup"><span data-stu-id="d9c17-136">The benefit of an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="d9c17-137">Для сеанса на основе SSH используйте параметры **HostName** или **сшконнектион** , чтобы указать удаленный компьютер и соответствующие сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="d9c17-137">For SSH based session you use the **HostName** or **SSHConnection** parameters to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="d9c17-138">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="d9c17-138">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="d9c17-139">В некоторых примерах кода для уменьшения длины строки используется Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="d9c17-139">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="d9c17-140">Дополнительные сведения см. в разделе [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-140">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="d9c17-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="d9c17-141">EXAMPLES</span></span>

### <span data-ttu-id="d9c17-142">Пример 1. Запуск скрипта на сервере</span><span class="sxs-lookup"><span data-stu-id="d9c17-142">Example 1: Run a script on a server</span></span>

<span data-ttu-id="d9c17-143">В этом примере `Test.ps1` сценарий выполняется на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="d9c17-143">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="d9c17-144">Параметр **FilePath** указывает скрипт, расположенный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-144">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="d9c17-145">Скрипт выполняется на удаленном компьютере, и результаты возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-145">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="d9c17-146">Пример 2. выполнение команды на удаленном сервере</span><span class="sxs-lookup"><span data-stu-id="d9c17-146">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="d9c17-147">В этом примере выполняется `Get-Culture` команда на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="d9c17-147">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="d9c17-148">Параметр **ComputerName** задает имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-148">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="d9c17-149">Параметр **Credential** используется для выполнения команды в контексте безопасности Domain01\User01 — пользователя, имеющего разрешение на выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="d9c17-149">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="d9c17-150">Параметр **ScriptBlock** указывает команду, выполняемую на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-150">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="d9c17-151">В ответ PowerShell запрашивает пароль и метод проверки подлинности для учетной записи User01.</span><span class="sxs-lookup"><span data-stu-id="d9c17-151">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="d9c17-152">Затем на компьютере Server01 запускается команда и возвращается результат.</span><span class="sxs-lookup"><span data-stu-id="d9c17-152">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="d9c17-153">Пример 3. выполнение команды в постоянном подключении</span><span class="sxs-lookup"><span data-stu-id="d9c17-153">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="d9c17-154">В этом примере выполняется та же `Get-Culture` команда в сеансе с использованием постоянного подключения на удаленном компьютере с именем Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-154">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="d9c17-155">`New-PSSession`Командлет создает сеанс на удаленном компьютере Server02 и сохраняет его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-155">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="d9c17-156">Как правило, сеанс создается только при выполнении ряда команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-156">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="d9c17-157">`Invoke-Command`Командлет выполняет `Get-Culture` команду в Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-157">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="d9c17-158">Параметр **Session** указывает сеанс, сохраненный в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-158">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="d9c17-159">В ответ PowerShell выполняет команду в сеансе на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-159">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="d9c17-160">Пример 4. Использование сеанса для выполнения ряда команд, которые совместно используют данные</span><span class="sxs-lookup"><span data-stu-id="d9c17-160">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="d9c17-161">В этом примере сравниваются последствия использования **ComputerName** и параметров **сеанса** `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-161">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="d9c17-162">В нем показано, как использовать сеанс для запуска ряда команд с общими данными.</span><span class="sxs-lookup"><span data-stu-id="d9c17-162">It shows how to use a session to run a series of commands that share the same data.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

<span data-ttu-id="d9c17-163">Первые две команды используют параметр **ComputerName** `Invoke-Command` команды для выполнения команд на удаленном компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-163">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="d9c17-164">Первая команда использует командлет, `Get-Process` чтобы получить процесс PowerShell на удаленном компьютере и сохранить его в `$p` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-164">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="d9c17-165">Вторая команда получает значение свойства **VirtualMemorySize** процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-165">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="d9c17-166">При использовании параметра **ComputerName** PowerShell создает новый сеанс для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-166">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="d9c17-167">Сеанс закрывается после завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-167">The session is closed when the command completes.</span></span> <span data-ttu-id="d9c17-168">`$p`Переменная была создана в одном соединении, но не существует в соединении, созданном для второй команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-168">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="d9c17-169">Проблему можно решить, создав постоянный сеанс на удаленном компьютере, а затем выполнив обе команды в том же сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-169">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="d9c17-170">`New-PSSession`Командлет создает постоянный сеанс на компьютере Server02 и сохраняет сеанс в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-170">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="d9c17-171">`Invoke-Command`Следующие строки используют параметр **Session** для выполнения обеих команд в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-171">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="d9c17-172">Так как обе команды выполняются в одном сеансе, `$p` значение остается активным.</span><span class="sxs-lookup"><span data-stu-id="d9c17-172">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="d9c17-173">Пример 5. Ввод команды, хранящейся в локальной переменной</span><span class="sxs-lookup"><span data-stu-id="d9c17-173">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="d9c17-174">В этом примере показано, как создать команду, которая хранится в виде блока скрипта в локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-174">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="d9c17-175">При сохранении блока скрипта в локальной переменной можно указать переменную в качестве значения параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-175">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-WinEvent -LogName PowerShellCore/Operational |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="d9c17-176">`$command`Переменная хранит `Get-WinEvent` команду, отформатированную в виде блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-176">The `$command` variable stores the `Get-WinEvent` command that's formatted as a script block.</span></span> <span data-ttu-id="d9c17-177">`Invoke-Command`Запускает команду, сохраненную в `$command` на удаленных компьютерах S1 и S2.</span><span class="sxs-lookup"><span data-stu-id="d9c17-177">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="d9c17-178">Пример 6. выполнение одной команды на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="d9c17-178">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="d9c17-179">В этом примере демонстрируется использование `Invoke-Command` для выполнения одной команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-179">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-WinEvent -LogName PowerShellCore/Operational }
}
Invoke-Command @parameters
```

<span data-ttu-id="d9c17-180">Параметр **ComputerName** задает разделенный запятыми список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-180">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="d9c17-181">Список компьютеров содержит значение localhost, которое представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-181">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="d9c17-182">Параметр **configurationName** задает альтернативную конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-182">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="d9c17-183">Параметр **ScriptBlock** выполняется `Get-WinEvent` для получения журналов событий PowerShellCore/Operation с каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-183">The **ScriptBlock** parameter runs `Get-WinEvent` to get the PowerShellCore/Operational event logs from each computer.</span></span>

### <span data-ttu-id="d9c17-184">Пример 7. Получение версии основной программы на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="d9c17-184">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="d9c17-185">В этом примере получается версия программы PowerShell Host, работающей на 200 удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-185">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="d9c17-186">Поскольку выполняется только одна команда, не нужно создавать постоянные подключения к каждому из этих компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-186">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="d9c17-187">Вместо этого команда использует параметр **ComputerName** для указания компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-187">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="d9c17-188">Чтобы указать компьютеры, он использует `Get-Content` командлет для получения содержимого файла Machine.txt, файла имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-188">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="d9c17-189">`Invoke-Command`Командлет выполняет `Get-Host` команду на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-189">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="d9c17-190">Он использует точечную нотацию для получения свойства **Version** узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-190">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="d9c17-191">Эти команды выполняются по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="d9c17-191">These commands run one at a time.</span></span> <span data-ttu-id="d9c17-192">После выполнения команд выходные данные команд из всех компьютеров сохраняются в `$version` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-192">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="d9c17-193">В выходные данные включается имя компьютера, с которого были получены данные.</span><span class="sxs-lookup"><span data-stu-id="d9c17-193">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="d9c17-194">Пример 8. Выполнение фонового задания на нескольких удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="d9c17-194">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="d9c17-195">В этом примере выполняется команда на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-195">This example runs a command on two remote computers.</span></span> <span data-ttu-id="d9c17-196">`Invoke-Command`Команда использует параметр **AsJob** , чтобы команда выполнялась как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="d9c17-196">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="d9c17-197">Команды выполняются на удаленных компьютерах, но задание существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-197">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="d9c17-198">Результаты передаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-198">The results are transmitted to the local computer.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

<span data-ttu-id="d9c17-199">`New-PSSession`Командлет создает сеансы на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-199">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="d9c17-200">`Invoke-Command`Командлет запускает фоновое задание в каждом сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-200">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="d9c17-201">Команда с помощью параметра **AsJob** выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="d9c17-201">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="d9c17-202">Эта команда возвращает объект задания, который содержит два дочерних объекта задания: один для каждого из заданий, запущенных на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-202">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="d9c17-203">`Get-Job`Команда сохраняет объект задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-203">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="d9c17-204">`$j`Затем переменная передается в `Format-List` командлет для вывода всех свойств объекта Job в списке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-204">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="d9c17-205">Последняя команда возвращает результаты заданий.</span><span class="sxs-lookup"><span data-stu-id="d9c17-205">The last command gets the results of the jobs.</span></span> <span data-ttu-id="d9c17-206">Он передает объект задания в `$j` `Receive-Job` командлет и сохраняет результаты в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-206">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="d9c17-207">Пример 9. Включение локальных переменных в команде, выполняемой на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="d9c17-207">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="d9c17-208">В этом примере показано, как включить значения локальных переменных в команду, запущенную на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-208">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="d9c17-209">Команда использует `Using` Модификатор области для определения локальной переменной в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-209">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="d9c17-210">По умолчанию предполагается, что все переменные определяются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-210">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="d9c17-211">`Using`Модификатор области появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-211">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="d9c17-212">Дополнительные сведения об `Using` модификаторе области см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md) и [about_Scopes](./about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-212">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "PowerShellCore/Operational"
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-WinEvent -LogName $Using:Log -MaxEvents 10}
```

<span data-ttu-id="d9c17-213">`$Log`Переменная хранит имя журнала событий, PowerShellCore/эксплуатация.</span><span class="sxs-lookup"><span data-stu-id="d9c17-213">The `$Log` variable stores the name of the event log, PowerShellCore/Operational.</span></span> <span data-ttu-id="d9c17-214">`Invoke-Command`Командлет выполняется `Get-WinEvent` в Server01 для получения десяти самых новых событий из журнала событий.</span><span class="sxs-lookup"><span data-stu-id="d9c17-214">The `Invoke-Command` cmdlet runs `Get-WinEvent` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="d9c17-215">Значением параметра "параметр **задания" является** `$Log` переменная, которая предваряется `Using` модификатором области, чтобы указать, что она была создана в локальном сеансе, а не в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-215">The value of the **LogName** parameter is the `$Log` variable that is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="d9c17-216">Пример 10. Скрытие имени компьютера</span><span class="sxs-lookup"><span data-stu-id="d9c17-216">Example 10: Hide the computer name</span></span>

<span data-ttu-id="d9c17-217">В этом примере показан результат использования параметра **хидекомпутернаме** метода `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-217">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="d9c17-218">**Хидекомпутернаме** не изменяет объект, возвращаемый этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="d9c17-218">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="d9c17-219">Он изменяет только отображение.</span><span class="sxs-lookup"><span data-stu-id="d9c17-219">It changes only the display.</span></span> <span data-ttu-id="d9c17-220">Вы по-прежнему можете использовать командлеты **Format** для вывода свойства **PSComputerName** любого из затронутых объектов.</span><span class="sxs-lookup"><span data-stu-id="d9c17-220">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

<span data-ttu-id="d9c17-221">Первые две команды используют `Invoke-Command` для выполнения `Get-Process` команды для процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-221">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="d9c17-222">В выходных данных первой команды содержится свойство **PsComputerName** с именем компьютера, на котором запущена команда.</span><span class="sxs-lookup"><span data-stu-id="d9c17-222">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="d9c17-223">Выходные данные второй команды, в которой используется **хидекомпутернаме** , не включают столбец **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-223">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="d9c17-224">Пример 11. Использование ключевого слова param в блоке script</span><span class="sxs-lookup"><span data-stu-id="d9c17-224">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="d9c17-225">`Param`Ключевое слово и параметр **ArgumentList** используются для передачи значений переменных в именованные параметры в блоке script.</span><span class="sxs-lookup"><span data-stu-id="d9c17-225">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="d9c17-226">В этом примере отображаются имена файлов, которые начинаются с буквы `a` и имеют `.pdf` расширение.</span><span class="sxs-lookup"><span data-stu-id="d9c17-226">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="d9c17-227">Дополнительные сведения о `Param` ключевом слове см. в разделе [about_Language_Keywords](./about/about_language_keywords.md#param).</span><span class="sxs-lookup"><span data-stu-id="d9c17-227">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

<span data-ttu-id="d9c17-228">`Invoke-Command` использует параметр **ScriptBlock** , определяющий две переменные: `$param1` и `$param2` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-228">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="d9c17-229">`Get-ChildItem` использует именованные параметры, **Name** и **include** с именами переменных.</span><span class="sxs-lookup"><span data-stu-id="d9c17-229">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="d9c17-230">**ArgumentList** передает значения переменным.</span><span class="sxs-lookup"><span data-stu-id="d9c17-230">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="d9c17-231">Пример 12. Использование автоматической переменной $args в блоке сценария</span><span class="sxs-lookup"><span data-stu-id="d9c17-231">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="d9c17-232">`$args`Автоматическая переменная и параметр **ArgumentList** используются для передачи значений массива позициям параметров в блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-232">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="d9c17-233">В этом примере отображается содержимое файлов каталога сервера `.txt` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-233">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="d9c17-234">Параметр `Get-ChildItem` **path** имеет значение расположения 0, а параметр **фильтра** — "расположение"</span><span class="sxs-lookup"><span data-stu-id="d9c17-234">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="d9c17-235">Дополнительные сведения о `$args` переменной см. в разделе [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="d9c17-235">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

<span data-ttu-id="d9c17-236">`Invoke-Command` использует параметр **ScriptBlock** и `Get-ChildItem` задает `$args[0]` `$args[1]` значения массива и.</span><span class="sxs-lookup"><span data-stu-id="d9c17-236">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="d9c17-237">**ArgumentList** передает `$args` значения массива на `Get-ChildItem` позиции параметров для **path** и **Filter** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-237">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter** .</span></span>

### <span data-ttu-id="d9c17-238">Пример 13. выполнение сценария на всех компьютерах, перечисленных в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="d9c17-238">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="d9c17-239">В этом примере используется `Invoke-Command` командлет для выполнения `Sample.ps1` скрипта на всех компьютерах, перечисленных в `Servers.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="d9c17-239">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="d9c17-240">Команда использует параметр **FilePath** , чтобы указать файл скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-240">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="d9c17-241">Эта команда позволяет запустить сценарий на удаленных компьютерах, даже если файл скрипта недоступен для удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-241">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="d9c17-242">При отправке команды содержимое `Sample.ps1` файла копируется в блок скрипта, а блок сценария выполняется на каждом удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-242">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="d9c17-243">Эта процедура эквивалентна использованию параметра **ScriptBlock** для отправки содержимого скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-243">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="d9c17-244">Пример 14. выполнение команды на удаленном компьютере с помощью URI</span><span class="sxs-lookup"><span data-stu-id="d9c17-244">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="d9c17-245">В этом примере показано, как выполнить команду на удаленном компьютере, идентифицируемом по универсальному идентификатору ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="d9c17-245">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="d9c17-246">В этом конкретном примере выполняется `Set-Mailbox` команда на удаленном сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="d9c17-246">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

<span data-ttu-id="d9c17-247">В первой строке используется `Get-Credential` командлет для хранения учетных данных Windows Live ID в `$LiveCred` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-247">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="d9c17-248">PowerShell предлагает пользователю ввести учетные данные Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="d9c17-248">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="d9c17-249">`$parameters`Переменная является хэш-таблицей, содержащей параметры, передаваемые в `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="d9c17-249">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="d9c17-250">`Invoke-Command`Командлет выполняет `Set-Mailbox` команду, используя конфигурацию сеанса **Microsoft. Exchange** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-250">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="d9c17-251">Параметр **ConnectionURI** указывает URL-адрес конечной точки сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9c17-251">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="d9c17-252">Параметр **Credential** указывает учетные данные, хранящиеся в `$LiveCred` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-252">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="d9c17-253">Параметр **AuthenticationMechanism** указывает способ использования обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d9c17-253">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="d9c17-254">Параметр **ScriptBlock** указывает блок скрипта, который содержит команду.</span><span class="sxs-lookup"><span data-stu-id="d9c17-254">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="d9c17-255">Пример 15. Использование параметра Session</span><span class="sxs-lookup"><span data-stu-id="d9c17-255">Example 15: Use a session option</span></span>

<span data-ttu-id="d9c17-256">В этом примере показано, как создать и использовать параметр **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-256">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="d9c17-257">`New-PSSessionOption`Командлет создает объект параметра сеанса, который заставляет удаленный элемент не проверять центр сертификации, каноническое имя и списки отзыва при оценке ВХОДЯЩЕГО HTTPS-подключения.</span><span class="sxs-lookup"><span data-stu-id="d9c17-257">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="d9c17-258">Объект **SessionOption** сохраняется в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-258">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="d9c17-259">Отключение этих проверок удобно для устранения неполадок, но очевидно небезопасно.</span><span class="sxs-lookup"><span data-stu-id="d9c17-259">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="d9c17-260">`Invoke-Command`Командлет запускает `Get-HotFix` команду удаленно.</span><span class="sxs-lookup"><span data-stu-id="d9c17-260">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="d9c17-261">Параметр **SessionOption** получает `$so` переменную.</span><span class="sxs-lookup"><span data-stu-id="d9c17-261">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="d9c17-262">Пример 16. Управление перенаправлением URI в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="d9c17-262">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="d9c17-263">В этом примере показано, как использовать параметры **AllowRedirection** и **SessionOption** для управления перенаправлением URI в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-263">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

<span data-ttu-id="d9c17-264">`New-PSSessionOption`Командлет создает объект **PSSessionOption** , который сохраняется в `$max` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-264">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="d9c17-265">Команда использует параметр **MaximumRedirection** , чтобы задать для свойства **MaximumConnectionRedirectionCount** объекта **PSSessionOption** значение 1.</span><span class="sxs-lookup"><span data-stu-id="d9c17-265">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="d9c17-266">`Invoke-Command`Командлет выполняет `Get-Mailbox` команду на удаленном сервере Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="d9c17-266">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="d9c17-267">Параметр **AllowRedirection** предоставляет явное разрешение для перенаправления подключения к альтернативной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-267">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="d9c17-268">Параметр **SessionOption** использует объект Session, хранящийся в `$max` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-268">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="d9c17-269">В результате, если удаленный компьютер, указанный параметром **ConnectionURI** , возвращает сообщение о перенаправлении, то PowerShell перенаправляет соединение, но если новое назначение возвращает другое сообщение перенаправления, то превышено значение счетчика перенаправления, равное 1, и `Invoke-Command` возвращает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="d9c17-269">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="d9c17-270">Пример 17. доступ к сетевой папке в удаленном сеансе</span><span class="sxs-lookup"><span data-stu-id="d9c17-270">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="d9c17-271">В этом примере показано, как получить доступ к сетевой папке из удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-271">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="d9c17-272">Для демонстрации примера используются три компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-272">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="d9c17-273">Server01 — локальный компьютер, Server02 — удаленный компьютер, а Net03 содержит сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="d9c17-273">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="d9c17-274">Server01 подключается к Server02, а затем Server02 выполняет второй прыжок к Net03 для доступа к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-274">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="d9c17-275">Дополнительные сведения о том, как удаленное взаимодействие PowerShell поддерживает переходы между компьютерами, см. [в статье Создание второго прыжка в удаленном взаимодействии PowerShell](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span><span class="sxs-lookup"><span data-stu-id="d9c17-275">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="d9c17-276">Требуемое делегирование поставщика поддержки безопасности учетных данных (CredSSP) включено в параметрах клиента на локальном компьютере и в параметрах службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-276">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="d9c17-277">Для выполнения команд в этом примере необходимо быть членом группы " **Администраторы** " на локальном компьютере и удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-277">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

<span data-ttu-id="d9c17-278">`Enable-WSManCredSSP`Командлет включает делегирование CredSSP с локального компьютера Server01 на удаленный компьютер Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-278">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="d9c17-279">Параметр **Role** указывает **клиент** для настройки параметра клиента CredSSP на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-279">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="d9c17-280">`New-PSSession` Создает объект **PSSession** для Server02 и сохраняет объект в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d9c17-280">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="d9c17-281">`Invoke-Command`Командлет использует `$s` переменную для подключения к удаленному компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="d9c17-281">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="d9c17-282">Параметр **ScriptBlock** выполняется `Enable-WSManCredSSP` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-282">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="d9c17-283">Параметр **Role** указывает **сервер** для настройки параметра сервера CredSSP на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-283">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="d9c17-284">`$parameters`Переменная содержит значения параметров для подключения к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-284">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="d9c17-285">`Invoke-Command`Командлет выполняет `Get-Item` команду в сеансе в `$s` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-285">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="d9c17-286">Эта команда возвращает скрипт из `\\Net03\Scripts` общей сетевой папки.</span><span class="sxs-lookup"><span data-stu-id="d9c17-286">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="d9c17-287">Команда использует параметр **authentication** со значением **CredSSP** и параметром **Credential** со значением **Domain01\Admin01** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-287">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01** .</span></span>

### <span data-ttu-id="d9c17-288">Пример 18. Запуск сценариев на многих удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="d9c17-288">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="d9c17-289">В этом примере сценарий выполняется на более чем сотни компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-289">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="d9c17-290">Чтобы свести к минимуму влияние на локальный компьютер, она подключается к каждому компьютеру, запускает скрипт, а затем отключается.</span><span class="sxs-lookup"><span data-stu-id="d9c17-290">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="d9c17-291">Скрипт продолжает выполняться в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-291">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="d9c17-292">Команда использует `Invoke-Command` для запуска скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-292">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="d9c17-293">Значение параметра **ComputerName** — это `Get-Content` команда, которая получает имена удаленных компьютеров из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="d9c17-293">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="d9c17-294">Параметр **InDisconnectedSession** отключает сеансы сразу при запуске команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-294">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="d9c17-295">Значение параметра **FilePath** — это скрипт, который `Invoke-Command` выполняется на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-295">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="d9c17-296">Значение **SessionOption** является хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="d9c17-296">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="d9c17-297">Для параметра **аутпутбуфферингмоде** устанавливается значение **Drop** , а для параметра **IdleTimeout** — значение **43200000** миллисекунд (12 часов).</span><span class="sxs-lookup"><span data-stu-id="d9c17-297">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="d9c17-298">Чтобы получить результаты выполнения команд и сценариев в отключенных сеансах, используйте `Receive-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="d9c17-298">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

### <span data-ttu-id="d9c17-299">Пример 19. выполнение команды на удаленном компьютере с помощью SSH</span><span class="sxs-lookup"><span data-stu-id="d9c17-299">Example 19: Run a command on a remote computer using SSH</span></span>

<span data-ttu-id="d9c17-300">В этом примере показано, как выполнить команду на удаленном компьютере с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d9c17-300">This example shows how to run a command on a remote computer using Secure Shell (SSH).</span></span> <span data-ttu-id="d9c17-301">Если на удаленном компьютере настроен протокол SSH для запроса паролей, вы получите запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="d9c17-301">If SSH is configured on the remote computer to prompt for passwords, then you'll get a password prompt.</span></span>
<span data-ttu-id="d9c17-302">В противном случае необходимо использовать проверку подлинности пользователя на основе ключа SSH.</span><span class="sxs-lookup"><span data-stu-id="d9c17-302">Otherwise, you'll have to use SSH key-based user authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * }
```

### <span data-ttu-id="d9c17-303">Пример 20. выполнение команды на удаленном компьютере с помощью SSH и указание ключа проверки подлинности пользователя</span><span class="sxs-lookup"><span data-stu-id="d9c17-303">Example 20: Run a command on a remote computer using SSH and specify a user authentication key</span></span>

<span data-ttu-id="d9c17-304">В этом примере показано, как выполнить команду на удаленном компьютере с помощью SSH и указать файл ключа для проверки подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-304">This example shows how to run a command on a remote computer using SSH and specifying a key file for user authentication.</span></span> <span data-ttu-id="d9c17-305">Вам не будет предложено ввести пароль, если не удастся выполнить проверку подлинности ключа и на удаленном компьютере разрешена обычная проверка пароля.</span><span class="sxs-lookup"><span data-stu-id="d9c17-305">You won't be prompted for a password unless the key authentication fails and the remote computer is configured to allow basic password authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * } -KeyFilePath /UserA/UserAKey_rsa
```

### <span data-ttu-id="d9c17-306">Пример 21. Запуск файла скрипта на нескольких удаленных компьютерах с помощью SSH в качестве задания</span><span class="sxs-lookup"><span data-stu-id="d9c17-306">Example 21: Run a script file on multiple remote computers using SSH as a job</span></span>

<span data-ttu-id="d9c17-307">В этом примере показано, как запустить файл скрипта на нескольких удаленных компьютерах с помощью SSH и набора параметров **сшконнектион** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-307">This example shows how to run a script file on multiple remote computers using SSH and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="d9c17-308">Параметр **сшконнектион** принимает массив хэш-таблиц, содержащих сведения о соединении для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-308">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each computer.</span></span> <span data-ttu-id="d9c17-309">В этом примере требуется, чтобы на целевых удаленных компьютерах был настроен SSH для поддержки проверки подлинности пользователей на основе ключей.</span><span class="sxs-lookup"><span data-stu-id="d9c17-309">This example requires that the target remote computers have SSH configured to support key-based user authentication.</span></span>

```powershell
$sshConnections =
@{ HostName="WinServer1"; UserName="Domain\UserA"; KeyFilePath="C:\Users\UserA\id_rsa" },
@{ HostName="UserB@LinuxServer5"; KeyFilePath="/Users/UserB/id_rsa" }
$results = Invoke-Command -FilePath c:\Scripts\CollectEvents.ps1 -SSHConnection $sshConnections
```

## <span data-ttu-id="d9c17-310">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d9c17-310">PARAMETERS</span></span>

### <span data-ttu-id="d9c17-311">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="d9c17-311">-AllowRedirection</span></span>

<span data-ttu-id="d9c17-312">Разрешает перенаправление данного соединения на альтернативный URI.</span><span class="sxs-lookup"><span data-stu-id="d9c17-312">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="d9c17-313">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="d9c17-313">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="d9c17-314">По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.</span><span class="sxs-lookup"><span data-stu-id="d9c17-314">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="d9c17-315">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-315">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="d9c17-316">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="d9c17-316">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="d9c17-317">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="d9c17-317">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-318">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d9c17-318">-ApplicationName</span></span>

<span data-ttu-id="d9c17-319">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="d9c17-319">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="d9c17-320">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-320">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="d9c17-321">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-321">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="d9c17-322">Если эта переменная предпочтений не определена, по умолчанию используется значение WSMAN.</span><span class="sxs-lookup"><span data-stu-id="d9c17-322">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="d9c17-323">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="d9c17-323">This value is appropriate for most uses.</span></span> <span data-ttu-id="d9c17-324">Дополнительные сведения см. в разделе [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-324">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="d9c17-325">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="d9c17-325">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="d9c17-326">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-326">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-327">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="d9c17-327">-ArgumentList</span></span>

<span data-ttu-id="d9c17-328">Предоставляет значения локальных переменных в команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-328">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="d9c17-329">Переменные в команде заменяются этими значениями до выполнения команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-329">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="d9c17-330">Введите значения в список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="d9c17-330">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="d9c17-331">Значения связаны с переменными в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="d9c17-331">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="d9c17-332">Псевдоним для **ArgumentList** — args.</span><span class="sxs-lookup"><span data-stu-id="d9c17-332">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="d9c17-333">Значения в параметре **ArgumentList** могут быть фактическими значениями, например 1024, или ссылками на локальные переменные, например `$max` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-333">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="d9c17-334">Чтобы использовать локальные переменные в команде, воспользуйтесь следующим форматом команды:</span><span class="sxs-lookup"><span data-stu-id="d9c17-334">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="d9c17-335">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -или- `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="d9c17-335">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="d9c17-336">Ключевое слово **param** перечисляет локальные переменные, используемые в команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-336">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="d9c17-337">**ArgumentList** предоставляет значения переменных в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="d9c17-337">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="d9c17-338">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="d9c17-338">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-339">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d9c17-339">-AsJob</span></span>

<span data-ttu-id="d9c17-340">Указывает, что этот командлет выполняет команду в качестве фонового задания на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-340">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="d9c17-341">Этот параметр используется для выполнения команд, выполнение которых занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="d9c17-341">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="d9c17-342">При использовании параметра **AsJob** команда возвращает объект, представляющий задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="d9c17-342">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="d9c17-343">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="d9c17-343">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="d9c17-344">Для управления заданием используйте `*-Job` командлеты.</span><span class="sxs-lookup"><span data-stu-id="d9c17-344">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="d9c17-345">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="d9c17-345">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="d9c17-346">Параметр **AsJob** напоминает использование `Invoke-Command` командлета для `Start-Job` удаленного выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="d9c17-346">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="d9c17-347">Однако при использовании **AsJob** задание создается на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-347">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="d9c17-348">Результаты удаленного задания автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-348">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="d9c17-349">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-349">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-350">-Authentication</span><span class="sxs-lookup"><span data-stu-id="d9c17-350">-Authentication</span></span>

<span data-ttu-id="d9c17-351">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-351">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="d9c17-352">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="d9c17-352">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="d9c17-353">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d9c17-353">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d9c17-354">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="d9c17-354">Default</span></span>
- <span data-ttu-id="d9c17-355">Базовый</span><span class="sxs-lookup"><span data-stu-id="d9c17-355">Basic</span></span>
- <span data-ttu-id="d9c17-356">CredSSP</span><span class="sxs-lookup"><span data-stu-id="d9c17-356">Credssp</span></span>
- <span data-ttu-id="d9c17-357">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="d9c17-357">Digest</span></span>
- <span data-ttu-id="d9c17-358">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d9c17-358">Kerberos</span></span>
- <span data-ttu-id="d9c17-359">Согласование</span><span class="sxs-lookup"><span data-stu-id="d9c17-359">Negotiate</span></span>
- <span data-ttu-id="d9c17-360">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="d9c17-360">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="d9c17-361">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="d9c17-361">The default value is Default.</span></span>

<span data-ttu-id="d9c17-362">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="d9c17-362">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="d9c17-363">Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-363">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d9c17-364">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="d9c17-364">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d9c17-365">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="d9c17-365">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="d9c17-366">Дополнительные сведения см. в разделе [поставщик поддержки безопасности учетных данных](/windows/win32/secauthn/credential-security-support-provider).</span><span class="sxs-lookup"><span data-stu-id="d9c17-366">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:
Accepted values: Basic, Default, Credssp, Digest, Kerberos, Negotiate, NegotiateWithImplicitCredential

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-367">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d9c17-367">-CertificateThumbprint</span></span>

<span data-ttu-id="d9c17-368">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="d9c17-368">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="d9c17-369">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="d9c17-369">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d9c17-370">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="d9c17-370">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d9c17-371">Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="d9c17-371">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="d9c17-372">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="d9c17-372">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-373">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d9c17-373">-ComputerName</span></span>

<span data-ttu-id="d9c17-374">Указывает компьютеры, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d9c17-374">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="d9c17-375">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-375">The default is the local computer.</span></span>

<span data-ttu-id="d9c17-376">При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется только для выполнения указанной команды и затем закрывается.</span><span class="sxs-lookup"><span data-stu-id="d9c17-376">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="d9c17-377">Если требуется постоянное подключение, используйте параметр **Session** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-377">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="d9c17-378">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="d9c17-378">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="d9c17-379">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="d9c17-379">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="d9c17-380">Чтобы использовать IP-адрес в значении **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-380">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="d9c17-381">Компьютер должен быть настроен для транспорта HTTPS, или IP-адрес удаленного компьютера должен быть включен в список **TrustedHosts** для WinRM локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-381">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="d9c17-382">Инструкции по добавлению имени компьютера в список **TrustedHosts** см. в разделе [Добавление компьютера в список надежных узлов](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span><span class="sxs-lookup"><span data-stu-id="d9c17-382">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="d9c17-383">В Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение **ComputerName** необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-383">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-384">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d9c17-384">-ConfigurationName</span></span>

<span data-ttu-id="d9c17-385">Указывает конфигурацию сеанса, используемую для нового **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-385">Specifies the session configuration that is used for the new **PSSession** .</span></span>

<span data-ttu-id="d9c17-386">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-386">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="d9c17-387">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-387">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="d9c17-388">При использовании с SSH этот параметр указывает подсистему для использования в целевом объекте, как определено в `sshd_config` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-388">When used with SSH, this parameter specifies the subsystem to use on the target as defined in `sshd_config`.</span></span> <span data-ttu-id="d9c17-389">Значение по умолчанию для SSH — `powershell` подсистема.</span><span class="sxs-lookup"><span data-stu-id="d9c17-389">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="d9c17-390">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-390">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="d9c17-391">Если на удаленном компьютере не существует указанной конфигурации сеанса, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d9c17-391">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="d9c17-392">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-392">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="d9c17-393">Если эта переменная предпочтений не задана, по умолчанию используется **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-393">If this preference variable isn't set, the default is **Microsoft.PowerShell** .</span></span> <span data-ttu-id="d9c17-394">Дополнительные сведения см. в разделе [about_Preference_Variables](about/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-394">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-395">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d9c17-395">-ConnectionUri</span></span>

<span data-ttu-id="d9c17-396">Задает универсальный код ресурса (URI), который определяет конечную точку подключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-396">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="d9c17-397">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="d9c17-397">The URI must be fully qualified.</span></span>

<span data-ttu-id="d9c17-398">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d9c17-398">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="d9c17-399">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d9c17-399">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="d9c17-400">Если не указать URI соединения, можно использовать параметры **UseSSL** и **Port** , чтобы указать значения универсального кода ресурса (URI) соединения.</span><span class="sxs-lookup"><span data-stu-id="d9c17-400">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="d9c17-401">Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d9c17-401">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d9c17-402">Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс будет создан с использованием стандартов ports: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d9c17-402">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d9c17-403">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d9c17-403">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="d9c17-404">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-404">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-405">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="d9c17-405">-ContainerId</span></span>

<span data-ttu-id="d9c17-406">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-406">Specifies an array of container IDs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-407">-Credential</span><span class="sxs-lookup"><span data-stu-id="d9c17-407">-Credential</span></span>

<span data-ttu-id="d9c17-408">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="d9c17-408">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d9c17-409">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="d9c17-409">The default is the current user.</span></span>

<span data-ttu-id="d9c17-410">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="d9c17-410">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d9c17-411">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="d9c17-411">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d9c17-412">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d9c17-412">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d9c17-413">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d9c17-413">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-414">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="d9c17-414">-EnableNetworkAccess</span></span>

<span data-ttu-id="d9c17-415">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-415">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="d9c17-416">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-416">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="d9c17-417">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="d9c17-417">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="d9c17-418">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-418">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="d9c17-419">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot ( `.` ), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="d9c17-419">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="d9c17-420">По умолчанию, сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-420">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="d9c17-421">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-421">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="d9c17-422">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d9c17-422">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="d9c17-423">Можно разрешить удаленный доступ в сеансе замыкания на себя, используя значение **CredSSP** параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.</span><span class="sxs-lookup"><span data-stu-id="d9c17-423">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="d9c17-424">Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="d9c17-424">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="d9c17-425">Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d9c17-425">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="d9c17-426">Для получения дополнительной информации см. `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="d9c17-426">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="d9c17-427">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-427">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-428">-FilePath</span><span class="sxs-lookup"><span data-stu-id="d9c17-428">-FilePath</span></span>

<span data-ttu-id="d9c17-429">Задает локальный скрипт, выполняемый этим командлетом на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-429">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="d9c17-430">Введите путь и имя файла скрипта или передайте путь к сценарию `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-430">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="d9c17-431">Сценарий должен существовать на локальном компьютере или в каталоге, к которому может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-431">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="d9c17-432">Используйте **ArgumentList** , чтобы указать значения параметров в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d9c17-432">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="d9c17-433">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта, передает блок сценария на удаленный компьютер и запускает его на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-433">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId, FilePathSSHHost, FilePathSSHHostHash
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-434">-Хидекомпутернаме</span><span class="sxs-lookup"><span data-stu-id="d9c17-434">-HideComputerName</span></span>

<span data-ttu-id="d9c17-435">Указывает, что этот командлет опускает имя компьютера для каждого объекта, отображаемого в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d9c17-435">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="d9c17-436">По умолчанию имя компьютера, создавшего объект, отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="d9c17-436">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="d9c17-437">Этот параметр влияет только на отображение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d9c17-437">This parameter affects only the output display.</span></span> <span data-ttu-id="d9c17-438">Он не изменяет объект.</span><span class="sxs-lookup"><span data-stu-id="d9c17-438">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases: HCN

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-439">-HostName</span><span class="sxs-lookup"><span data-stu-id="d9c17-439">-HostName</span></span>

<span data-ttu-id="d9c17-440">Указывает массив имен компьютеров для подключения на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d9c17-440">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="d9c17-441">Это похоже на параметр **ComputerName** , за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.</span><span class="sxs-lookup"><span data-stu-id="d9c17-441">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="d9c17-442">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-442">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-443">-InDisconnectedSession</span><span class="sxs-lookup"><span data-stu-id="d9c17-443">-InDisconnectedSession</span></span>

<span data-ttu-id="d9c17-444">Указывает, что этот командлет запускает команду или сценарий в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d9c17-444">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="d9c17-445">При использовании параметра **InDisconnectedSession** `Invoke-Command` создает постоянный сеанс на каждом удаленном компьютере, запускает команду, указанную параметром **ScriptBlock** или **FilePath** , а затем отключается от сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-445">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="d9c17-446">Команды продолжают выполняться в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-446">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="d9c17-447">**InDisconnectedSession** позволяет выполнять команды без подключения к удаленным сеансам.</span><span class="sxs-lookup"><span data-stu-id="d9c17-447">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="d9c17-448">И, поскольку сеанс отключается перед возвратом результатов, **InDisconnectedSession** гарантирует, что все результаты команды возвращаются к повторно подключенному сеансу, а не распределяются между сеансами.</span><span class="sxs-lookup"><span data-stu-id="d9c17-448">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="d9c17-449">Нельзя использовать **InDisconnectedSession** с параметром **Session** или **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-449">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="d9c17-450">Команды, использующие **InDisconnectedSession** , возвращают объект **PSSession** , представляющий отключенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="d9c17-450">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="d9c17-451">Они не возвращают выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-451">They don't return the command output.</span></span> <span data-ttu-id="d9c17-452">Чтобы подключиться к отключенному сеансу, используйте `Connect-PSSession` `Receive-PSSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="d9c17-452">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="d9c17-453">Чтобы получить результаты команд, которые выполнялись в сеансе, используйте `Receive-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="d9c17-453">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="d9c17-454">Чтобы выполнить команды, создающие выходные данные в отключенном сеансе, установите для параметра сеанса **аутпутбуфферингмоде** значение **Drop** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-454">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop** .</span></span> <span data-ttu-id="d9c17-455">Если вы планируете подключиться к отключенному сеансу, установите время ожидания простоя в сеансе, чтобы обеспечить достаточное время для подключения перед удалением сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-455">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="d9c17-456">Можно задать режим буферизации вывода и время ожидания простоя в параметре **SessionOption** или в `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="d9c17-456">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="d9c17-457">Дополнительные сведения о параметрах сеанса см. в статьях `New-PSSessionOption` и [about_Preference_Variables](./about/about_preference_variables.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-457">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="d9c17-458">Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-458">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="d9c17-459">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-459">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-460">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d9c17-460">-InputObject</span></span>

<span data-ttu-id="d9c17-461">Указывает входные данные команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-461">Specifies input to the command.</span></span> <span data-ttu-id="d9c17-462">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="d9c17-462">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="d9c17-463">При использовании параметра **InputObject** используйте `$Input` автоматическую переменную в значении параметра **ScriptBlock** для представления входных объектов.</span><span class="sxs-lookup"><span data-stu-id="d9c17-463">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-464">-JobName</span><span class="sxs-lookup"><span data-stu-id="d9c17-464">-JobName</span></span>

<span data-ttu-id="d9c17-465">Указывает понятное имя для фонового задания.</span><span class="sxs-lookup"><span data-stu-id="d9c17-465">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="d9c17-466">По умолчанию задания именуются `Job<n>` , где `<n>` — порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="d9c17-466">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="d9c17-467">Если в команде используется параметр **JobName** , команда выполняется как задание и `Invoke-Command` возвращает объект задания, даже если в команде не включена функция **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-467">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="d9c17-468">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-468">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-469">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="d9c17-469">-KeyFilePath</span></span>

<span data-ttu-id="d9c17-470">Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-470">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="d9c17-471">SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля.</span><span class="sxs-lookup"><span data-stu-id="d9c17-471">SSH allows user authentication to be performed via private and public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="d9c17-472">Если на удаленном компьютере настроена проверка подлинности с помощью ключей, этот параметр можно использовать для предоставления ключа, определяющего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-472">If the remote computer is configured for key authentication, then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="d9c17-473">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-473">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-474">-Ноневскопе</span><span class="sxs-lookup"><span data-stu-id="d9c17-474">-NoNewScope</span></span>

<span data-ttu-id="d9c17-475">Указывает, что этот командлет выполняет указанную команду в текущей области.</span><span class="sxs-lookup"><span data-stu-id="d9c17-475">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="d9c17-476">По умолчанию `Invoke-Command` выполняет команды в своей собственной области.</span><span class="sxs-lookup"><span data-stu-id="d9c17-476">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="d9c17-477">Этот параметр допустим только в командах, которые выполняются в текущем сеансе, т. е. в командах, которые пропускают как параметр **ComputerName** , так и параметр **Session** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-477">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="d9c17-478">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-478">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-479">-Port</span><span class="sxs-lookup"><span data-stu-id="d9c17-479">-Port</span></span>

<span data-ttu-id="d9c17-480">Указывает сетевой порт на удаленном компьютере, используемый для этой команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-480">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="d9c17-481">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="d9c17-481">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="d9c17-482">Порты по умолчанию: 5985 (порт WinRM для HTTP) и 5986 (порт WinRM для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d9c17-482">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="d9c17-483">Перед использованием другого порта настройте прослушиватель WinRM на удаленном компьютере для прослушивания порта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-483">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="d9c17-484">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d9c17-484">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="d9c17-485">Не используйте параметр **Port** , если не требуется.</span><span class="sxs-lookup"><span data-stu-id="d9c17-485">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d9c17-486">Порт, который задается в команде, применяется ко всем компьютерам или сеансам, в которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d9c17-486">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d9c17-487">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d9c17-487">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, FilePathComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-488">-RemoteDebug</span><span class="sxs-lookup"><span data-stu-id="d9c17-488">-RemoteDebug</span></span>

<span data-ttu-id="d9c17-489">Используется для выполнения вызванной команды в режиме отладки в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-489">Used to run the invoked command in debug mode in the remote PowerShell session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-490">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="d9c17-490">-RunAsAdministrator</span></span>

<span data-ttu-id="d9c17-491">Указывает, что этот командлет вызывает команду от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="d9c17-491">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-492">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="d9c17-492">-ScriptBlock</span></span>

<span data-ttu-id="d9c17-493">Указывает выполняющиеся команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-493">Specifies the commands to run.</span></span> <span data-ttu-id="d9c17-494">Заключите команды в фигурные скобки, `{ }` чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9c17-494">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="d9c17-495">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="d9c17-495">This parameter is required.</span></span>

<span data-ttu-id="d9c17-496">По умолчанию все переменные в команде вычисляются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-496">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="d9c17-497">Чтобы включить локальные переменные в команду, используйте **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-497">To include local variables in the command, use **ArgumentList** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, SSHHost, ContainerId, SSHHostHashParam
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-498">-Session</span><span class="sxs-lookup"><span data-stu-id="d9c17-498">-Session</span></span>

<span data-ttu-id="d9c17-499">Указывает массив сеансов, в которых этот командлет выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="d9c17-499">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="d9c17-500">Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` команда или `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-500">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="d9c17-501">При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d9c17-501">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="d9c17-502">Используйте **PSSession** для выполнения ряда связанных команд, которые совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="d9c17-502">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="d9c17-503">Чтобы выполнить одну команду или ряд несвязанных команд, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-503">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="d9c17-504">Дополнительные сведения см. в разделе [about_PSSessions](./About/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-504">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: FilePathRunspace, Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-505">-SessionName</span><span class="sxs-lookup"><span data-stu-id="d9c17-505">-SessionName</span></span>

<span data-ttu-id="d9c17-506">Задает понятное имя для отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-506">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="d9c17-507">Имя можно использовать для ссылки на сеанс в последующих командах, таких как `Get-PSSession` команда.</span><span class="sxs-lookup"><span data-stu-id="d9c17-507">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="d9c17-508">Этот параметр допустим только при использовании с параметром **InDisconnectedSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-508">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="d9c17-509">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-509">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-510">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d9c17-510">-SessionOption</span></span>

<span data-ttu-id="d9c17-511">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-511">Specifies advanced options for the session.</span></span> <span data-ttu-id="d9c17-512">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-512">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="d9c17-513">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="d9c17-513">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="d9c17-514">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-514">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="d9c17-515">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-515">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="d9c17-516">Однако они не имеют приоритета над максимальными значениями, квотами или ограничениями, установленными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d9c17-516">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="d9c17-517">Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-517">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="d9c17-518">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-518">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="d9c17-519">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d9c17-519">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-520">-Сшконнектион</span><span class="sxs-lookup"><span data-stu-id="d9c17-520">-SSHConnection</span></span>

<span data-ttu-id="d9c17-521">Этот параметр принимает массив хэш-таблиц, где каждая хэш-таблица содержит один или несколько параметров соединения, необходимых для установления подключения Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d9c17-521">This parameter takes an array of hash tables where each hash table contains one or more connection parameters needed to establish a Secure Shell (SSH) connection.</span></span> <span data-ttu-id="d9c17-522">Параметр **сшконнектион** полезен для создания нескольких сеансов, в которых каждому сеансу требуются разные сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="d9c17-522">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="d9c17-523">Хэш-таблица содержит следующие члены:</span><span class="sxs-lookup"><span data-stu-id="d9c17-523">The hashtable has the following members:</span></span>

- <span data-ttu-id="d9c17-524">**ComputerName** (или **имя узла** )</span><span class="sxs-lookup"><span data-stu-id="d9c17-524">**ComputerName** (or **HostName** )</span></span>
- <span data-ttu-id="d9c17-525">**порт** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-525">**Port**</span></span>
- <span data-ttu-id="d9c17-526">**UserName**</span><span class="sxs-lookup"><span data-stu-id="d9c17-526">**UserName**</span></span>
- <span data-ttu-id="d9c17-527">**KeyFilePath** (или **идентитифилепас** )</span><span class="sxs-lookup"><span data-stu-id="d9c17-527">**KeyFilePath** (or **IdentityFilePath** )</span></span>

<span data-ttu-id="d9c17-528">**ComputerName** (или **HostName** ) — единственная обязательная пара "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="d9c17-528">**ComputerName** (or **HostName** ) is the only key-value pair that is required.</span></span>

<span data-ttu-id="d9c17-529">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-529">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam, FilePathSSHHostHash
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-530">-Сштранспорт</span><span class="sxs-lookup"><span data-stu-id="d9c17-530">-SSHTransport</span></span>

<span data-ttu-id="d9c17-531">Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d9c17-531">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="d9c17-532">По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d9c17-532">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="d9c17-533">Этот параметр заставляет PowerShell использовать параметр **HostName** для установления удаленного подключения на основе SSH.</span><span class="sxs-lookup"><span data-stu-id="d9c17-533">This switch forces PowerShell to use the **HostName** parameter for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="d9c17-534">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-534">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-535">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d9c17-535">-ThrottleLimit</span></span>

<span data-ttu-id="d9c17-536">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-536">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="d9c17-537">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="d9c17-537">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="d9c17-538">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d9c17-538">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-539">-UserName</span><span class="sxs-lookup"><span data-stu-id="d9c17-539">-UserName</span></span>

<span data-ttu-id="d9c17-540">Указывает имя пользователя для учетной записи, используемой для выполнения команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-540">Specifies the username for the account used to run a command on the remote computer.</span></span> <span data-ttu-id="d9c17-541">Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-541">The user authentication method depends on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="d9c17-542">Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-542">If SSH is configured for basic password authentication, then you'll be prompted for the user password.</span></span>

<span data-ttu-id="d9c17-543">Если SSH настроен для проверки подлинности пользователя на основе ключа, то путь к файлу ключа можно указать с помощью параметра **KeyFilePath** , и запрос пароля не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="d9c17-543">If SSH is configured for key-based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt occurs.</span></span> <span data-ttu-id="d9c17-544">Если файл ключа пользователя клиента находится в известном расположении SSH, параметр **KeyFilePath** не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-544">If the client user key file is located in an SSH known location, then the **KeyFilePath** parameter isn't needed for key-based authentication, and user authentication occurs automatically based on the username.</span></span> <span data-ttu-id="d9c17-545">Дополнительные сведения см. в документации по SSH вашей платформы о проверке подлинности пользователя на основе ключа.</span><span class="sxs-lookup"><span data-stu-id="d9c17-545">For more information, see your platform's SSH documentation about key-based user authentication.</span></span>

<span data-ttu-id="d9c17-546">Этот параметр не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d9c17-546">This isn't a required parameter.</span></span> <span data-ttu-id="d9c17-547">Если параметр **username** не указан, то для соединения используется текущее имя пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="d9c17-547">If the **UserName** parameter isn't specified, then the current logged on username is used for the connection.</span></span>

<span data-ttu-id="d9c17-548">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-548">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-549">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="d9c17-549">-UseSSL</span></span>

<span data-ttu-id="d9c17-550">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="d9c17-550">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="d9c17-551">По умолчанию протокол SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="d9c17-551">By default, SSL isn't used.</span></span>

<span data-ttu-id="d9c17-552">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="d9c17-552">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="d9c17-553">Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по протоколу HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="d9c17-553">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="d9c17-554">Если вы используете этот параметр, но протокол SSL недоступен в порте, используемом для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d9c17-554">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-555">— VMId</span><span class="sxs-lookup"><span data-stu-id="d9c17-555">-VMId</span></span>

<span data-ttu-id="d9c17-556">Указывает массив идентификаторов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d9c17-556">Specifies an array of IDs of virtual machines.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-557">-VMName</span><span class="sxs-lookup"><span data-stu-id="d9c17-557">-VMName</span></span>

<span data-ttu-id="d9c17-558">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d9c17-558">Specifies an array of names of virtual machines.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-559">-Подсистема</span><span class="sxs-lookup"><span data-stu-id="d9c17-559">-Subsystem</span></span>

<span data-ttu-id="d9c17-560">Указывает подсистему SSH, используемую для нового **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-560">Specifies the SSH subsystem used for the new **PSSession** .</span></span>

<span data-ttu-id="d9c17-561">Указывает подсистему для использования в целевом объекте, как определено в sshd_config.</span><span class="sxs-lookup"><span data-stu-id="d9c17-561">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="d9c17-562">Подсистема запускает определенную версию PowerShell с предопределенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d9c17-562">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="d9c17-563">Если указанная подсистема не существует на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d9c17-563">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="d9c17-564">Если этот параметр не используется, по умолчанию используется подсистема PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9c17-564">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9c17-565">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d9c17-565">CommonParameters</span></span>

<span data-ttu-id="d9c17-566">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d9c17-566">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d9c17-567">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d9c17-567">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d9c17-568">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d9c17-568">INPUTS</span></span>

### <span data-ttu-id="d9c17-569">System. Management. Automation. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="d9c17-569">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="d9c17-570">Команду можно передать в блок скрипта в `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d9c17-570">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="d9c17-571">Используйте `$Input` автоматическую переменную для представления входных объектов в команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-571">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="d9c17-572">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d9c17-572">OUTPUTS</span></span>

### <span data-ttu-id="d9c17-573">System. Management. Automation. Псремотингжоб, System. Management. Automation. пространства выполнения PSSession или выходные данные вызываемой команды</span><span class="sxs-lookup"><span data-stu-id="d9c17-573">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="d9c17-574">Этот командлет возвращает объект задания, если используется параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-574">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="d9c17-575">Если указан параметр **InDisconnectedSession** , `Invoke-Command` возвращает объект **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-575">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="d9c17-576">В противном случае он возвращает выходные данные вызванной команды, которая является значением параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-576">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="d9c17-577">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d9c17-577">NOTES</span></span>

<span data-ttu-id="d9c17-578">В Windows Vista и более поздних версиях операционной системы Windows для использования параметра **ComputerName** `Invoke-Command` функции для выполнения команды на локальном компьютере необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-578">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="d9c17-579">При выполнении команд на нескольких компьютерах PowerShell подключается к компьютерам в том порядке, в котором они отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="d9c17-579">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="d9c17-580">Однако выходные данные команды отображаются в порядке их получения с удаленных компьютеров, которые могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="d9c17-580">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="d9c17-581">Ошибки, возникающие в результате выполнения команды, `Invoke-Command` включаются в результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="d9c17-581">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="d9c17-582">Ошибки, являющиеся неустранимыми в локальной команде, рассматриваются как устранимые в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="d9c17-582">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="d9c17-583">Эта стратегия гарантирует, что завершающие ошибки на одном компьютере не закрывают команду на всех компьютерах, на которых он выполняется.</span><span class="sxs-lookup"><span data-stu-id="d9c17-583">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="d9c17-584">Такой подход используется, даже если удаленная команда выполняется на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9c17-584">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="d9c17-585">Если удаленный компьютер не входит в домен, которому доверяет локальный компьютер, возможно, компьютер не сможет проверить подлинность учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9c17-585">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="d9c17-586">Чтобы добавить удаленный компьютер в список надежных узлов в службе WS-Management, используйте следующую команду в `WSMAN` поставщике, где `<Remote-Computer-Name>` — имя удаленного компьютера:</span><span class="sxs-lookup"><span data-stu-id="d9c17-586">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="d9c17-587">При отключении **PSSession** с помощью параметра **InDisconnectedSession** состояние сеанса **отключается** , а доступность — **нет** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-587">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None** .</span></span> <span data-ttu-id="d9c17-588">Значение свойства **State** определяется текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="d9c17-588">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="d9c17-589">Значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="d9c17-589">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="d9c17-590">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="d9c17-590">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="d9c17-591">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="d9c17-591">It might be connected to a different session.</span></span> <span data-ttu-id="d9c17-592">Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="d9c17-592">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="d9c17-593">Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="d9c17-593">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="d9c17-594">Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="d9c17-594">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="d9c17-595">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="d9c17-595">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="d9c17-596">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="d9c17-596">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

<span data-ttu-id="d9c17-597">Параметры **HostName** и **сшконнектион** были добавлены начиная с PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="d9c17-597">The **HostName** and **SSHConnection** parameters were included starting with PowerShell 6.0.</span></span> <span data-ttu-id="d9c17-598">Они были добавлены для обеспечения удаленного взаимодействия PowerShell на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="d9c17-598">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="d9c17-599">PowerShell и SSH поддерживаются на нескольких платформах (Windows, Linux, macOS) и удаленное взаимодействие PowerShell работают на этих платформах, где установлены и настроены PowerShell и SSH.</span><span class="sxs-lookup"><span data-stu-id="d9c17-599">PowerShell and SSH are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting works over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="d9c17-600">Это отдельно от предыдущего удаленного взаимодействия Windows только на основе WinRM, а многие функции и ограничения WinRM не применяются.</span><span class="sxs-lookup"><span data-stu-id="d9c17-600">This is separate from the previous Windows only remoting that is based on WinRM and many of the WinRM specific features and limitations don't apply.</span></span> <span data-ttu-id="d9c17-601">Например, квоты на основе WinRM, параметры сеанса, конфигурация пользовательской конечной точки и функции отключения и повторного подключения сейчас не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d9c17-601">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="d9c17-602">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="d9c17-602">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="d9c17-603">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d9c17-603">RELATED LINKS</span></span>

[<span data-ttu-id="d9c17-604">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d9c17-604">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="d9c17-605">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d9c17-605">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="d9c17-606">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="d9c17-606">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="d9c17-607">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="d9c17-607">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="d9c17-608">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="d9c17-608">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="d9c17-609">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="d9c17-609">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="d9c17-610">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d9c17-610">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d9c17-611">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="d9c17-611">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d9c17-612">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d9c17-612">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="d9c17-613">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d9c17-613">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="d9c17-614">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d9c17-614">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d9c17-615">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d9c17-615">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="d9c17-616">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="d9c17-616">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
