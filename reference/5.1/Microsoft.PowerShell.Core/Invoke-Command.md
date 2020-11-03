---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: 652ff321ea1c6507915be9748715604166207200
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229782"
---
# <span data-ttu-id="116f1-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="116f1-103">Invoke-Command</span></span>

## <span data-ttu-id="116f1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="116f1-104">SYNOPSIS</span></span>
<span data-ttu-id="116f1-105">Выполняет команды на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="116f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="116f1-106">SYNTAX</span></span>

### <span data-ttu-id="116f1-107">Необрабатываемый (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="116f1-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="116f1-108">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-109">филепасрунспаце</span><span class="sxs-lookup"><span data-stu-id="116f1-109">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="116f1-110">филепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="116f1-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-111">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="116f1-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-112">URI</span><span class="sxs-lookup"><span data-stu-id="116f1-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-113">филепасури</span><span class="sxs-lookup"><span data-stu-id="116f1-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="116f1-114">VMId</span><span class="sxs-lookup"><span data-stu-id="116f1-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="116f1-115">VMName</span><span class="sxs-lookup"><span data-stu-id="116f1-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="116f1-116">филепасвмид</span><span class="sxs-lookup"><span data-stu-id="116f1-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="116f1-117">филепасвмнаме</span><span class="sxs-lookup"><span data-stu-id="116f1-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="116f1-118">ContainerId</span><span class="sxs-lookup"><span data-stu-id="116f1-118">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="116f1-119">филепасконтаинерид</span><span class="sxs-lookup"><span data-stu-id="116f1-119">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

## <span data-ttu-id="116f1-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="116f1-120">DESCRIPTION</span></span>

<span data-ttu-id="116f1-121">`Invoke-Command`Командлет выполняет команды на локальном или удаленном компьютере и возвращает все выходные данные команд, включая ошибки.</span><span class="sxs-lookup"><span data-stu-id="116f1-121">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="116f1-122">С помощью одной `Invoke-Command` команды можно выполнять команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-122">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="116f1-123">Чтобы выполнить одну команду на удаленном компьютере, используйте параметр **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="116f1-123">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="116f1-124">Чтобы выполнить ряд связанных команд, совместно использующих данные, используйте `New-PSSession` командлет, чтобы создать **сеанс PSSession** (постоянное подключение) на удаленном компьютере, а затем используйте параметр **Session** для, `Invoke-Command` чтобы выполнить команду в **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="116f1-124">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession**.</span></span> <span data-ttu-id="116f1-125">Чтобы выполнить команду в отключенном сеансе, используйте параметр **InDisconnectedSession**.</span><span class="sxs-lookup"><span data-stu-id="116f1-125">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="116f1-126">Чтобы выполнить команду в фоновом задании, используйте параметр **AsJob**.</span><span class="sxs-lookup"><span data-stu-id="116f1-126">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="116f1-127">Можно также использовать `Invoke-Command` на локальном компьютере в качестве команды в блоке сценария.</span><span class="sxs-lookup"><span data-stu-id="116f1-127">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="116f1-128">PowerShell сразу же выполняет блок сценария в дочерней области текущей области.</span><span class="sxs-lookup"><span data-stu-id="116f1-128">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="116f1-129">Прежде чем использовать `Invoke-Command` для запуска команд на удаленном компьютере, прочитайте [about_Remote](./About/about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-129">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="116f1-130">В некоторых примерах кода для уменьшения длины строки используется Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="116f1-130">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="116f1-131">Дополнительные сведения см. в разделе [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-131">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="116f1-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="116f1-132">EXAMPLES</span></span>

### <span data-ttu-id="116f1-133">Пример 1. Запуск скрипта на сервере</span><span class="sxs-lookup"><span data-stu-id="116f1-133">Example 1: Run a script on a server</span></span>

<span data-ttu-id="116f1-134">В этом примере `Test.ps1` сценарий выполняется на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="116f1-134">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="116f1-135">Параметр **FilePath** указывает скрипт, расположенный на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-135">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="116f1-136">Скрипт выполняется на удаленном компьютере, и результаты возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-136">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="116f1-137">Пример 2. выполнение команды на удаленном сервере</span><span class="sxs-lookup"><span data-stu-id="116f1-137">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="116f1-138">В этом примере выполняется `Get-Culture` команда на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="116f1-138">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="116f1-139">Параметр **ComputerName** задает имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="116f1-139">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="116f1-140">Параметр **Credential** используется для выполнения команды в контексте безопасности Domain01\User01 — пользователя, имеющего разрешение на выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="116f1-140">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="116f1-141">Параметр **ScriptBlock** указывает команду, выполняемую на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-141">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="116f1-142">В ответ PowerShell запрашивает пароль и метод проверки подлинности для учетной записи User01.</span><span class="sxs-lookup"><span data-stu-id="116f1-142">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="116f1-143">Затем на компьютере Server01 запускается команда и возвращается результат.</span><span class="sxs-lookup"><span data-stu-id="116f1-143">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="116f1-144">Пример 3. выполнение команды в постоянном подключении</span><span class="sxs-lookup"><span data-stu-id="116f1-144">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="116f1-145">В этом примере выполняется та же `Get-Culture` команда в сеансе с использованием постоянного подключения на удаленном компьютере с именем Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-145">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="116f1-146">`New-PSSession`Командлет создает сеанс на удаленном компьютере Server02 и сохраняет его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-146">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="116f1-147">Как правило, сеанс создается только при выполнении ряда команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-147">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="116f1-148">`Invoke-Command`Командлет выполняет `Get-Culture` команду в Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-148">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="116f1-149">Параметр **Session** указывает сеанс, сохраненный в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-149">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="116f1-150">В ответ PowerShell выполняет команду в сеансе на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-150">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="116f1-151">Пример 4. Использование сеанса для выполнения ряда команд, которые совместно используют данные</span><span class="sxs-lookup"><span data-stu-id="116f1-151">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="116f1-152">В этом примере сравниваются последствия использования **ComputerName** и параметров **сеанса** `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="116f1-152">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="116f1-153">В нем показано, как использовать сеанс для запуска ряда команд с общими данными.</span><span class="sxs-lookup"><span data-stu-id="116f1-153">It shows how to use a session to run a series of commands that share the same data.</span></span>

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

<span data-ttu-id="116f1-154">Первые две команды используют параметр **ComputerName** `Invoke-Command` команды для выполнения команд на удаленном компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-154">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="116f1-155">Первая команда использует командлет, `Get-Process` чтобы получить процесс PowerShell на удаленном компьютере и сохранить его в `$p` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-155">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="116f1-156">Вторая команда получает значение свойства **VirtualMemorySize** процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="116f1-156">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="116f1-157">При использовании параметра **ComputerName** PowerShell создает новый сеанс для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-157">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="116f1-158">Сеанс закрывается после завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-158">The session is closed when the command completes.</span></span> <span data-ttu-id="116f1-159">`$p`Переменная была создана в одном соединении, но не существует в соединении, созданном для второй команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-159">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="116f1-160">Проблему можно решить, создав постоянный сеанс на удаленном компьютере, а затем выполнив обе команды в том же сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-160">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="116f1-161">`New-PSSession`Командлет создает постоянный сеанс на компьютере Server02 и сохраняет сеанс в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-161">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="116f1-162">`Invoke-Command`Следующие строки используют параметр **Session** для выполнения обеих команд в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-162">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="116f1-163">Так как обе команды выполняются в одном сеансе, `$p` значение остается активным.</span><span class="sxs-lookup"><span data-stu-id="116f1-163">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="116f1-164">Пример 5. Ввод команды, хранящейся в локальной переменной</span><span class="sxs-lookup"><span data-stu-id="116f1-164">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="116f1-165">В этом примере показано, как создать команду, которая хранится в виде блока скрипта в локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-165">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="116f1-166">При сохранении блока скрипта в локальной переменной можно указать переменную в качестве значения параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="116f1-166">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-EventLog -LogName "Windows PowerShell" |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="116f1-167">`$command`Переменная хранит `Get-EventLog` команду, отформатированную в виде блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-167">The `$command` variable stores the `Get-EventLog` command that's formatted as a script block.</span></span> <span data-ttu-id="116f1-168">`Invoke-Command`Запускает команду, сохраненную в `$command` на удаленных компьютерах S1 и S2.</span><span class="sxs-lookup"><span data-stu-id="116f1-168">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="116f1-169">Пример 6. выполнение одной команды на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="116f1-169">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="116f1-170">В этом примере демонстрируется использование `Invoke-Command` для выполнения одной команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-170">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-EventLog "Windows PowerShell" }
}
Invoke-Command @parameters
```

<span data-ttu-id="116f1-171">Параметр **ComputerName** задает разделенный запятыми список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-171">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="116f1-172">Список компьютеров содержит значение localhost, которое представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-172">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="116f1-173">Параметр **configurationName** задает альтернативную конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-173">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="116f1-174">Параметр **ScriptBlock** запускается `Get-EventLog` для получения журналов событий Windows PowerShell с каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="116f1-174">The **ScriptBlock** parameter runs `Get-EventLog` to get the Windows PowerShell event logs from each computer.</span></span>

### <span data-ttu-id="116f1-175">Пример 7. Получение версии основной программы на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="116f1-175">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="116f1-176">В этом примере получается версия программы PowerShell Host, работающей на 200 удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-176">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="116f1-177">Поскольку выполняется только одна команда, не нужно создавать постоянные подключения к каждому из этих компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-177">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="116f1-178">Вместо этого команда использует параметр **ComputerName** для указания компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-178">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="116f1-179">Чтобы указать компьютеры, он использует `Get-Content` командлет для получения содержимого файла Machine.txt, файла имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-179">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="116f1-180">`Invoke-Command`Командлет выполняет `Get-Host` команду на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-180">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="116f1-181">Он использует точечную нотацию для получения свойства **Version** узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="116f1-181">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="116f1-182">Эти команды выполняются по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="116f1-182">These commands run one at a time.</span></span> <span data-ttu-id="116f1-183">После выполнения команд выходные данные команд из всех компьютеров сохраняются в `$version` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-183">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="116f1-184">В выходные данные включается имя компьютера, с которого были получены данные.</span><span class="sxs-lookup"><span data-stu-id="116f1-184">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="116f1-185">Пример 8. Выполнение фонового задания на нескольких удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="116f1-185">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="116f1-186">В этом примере выполняется команда на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-186">This example runs a command on two remote computers.</span></span> <span data-ttu-id="116f1-187">`Invoke-Command`Команда использует параметр **AsJob** , чтобы команда выполнялась как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="116f1-187">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="116f1-188">Команды выполняются на удаленных компьютерах, но задание существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-188">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="116f1-189">Результаты передаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-189">The results are transmitted to the local computer.</span></span>

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

<span data-ttu-id="116f1-190">`New-PSSession`Командлет создает сеансы на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-190">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="116f1-191">`Invoke-Command`Командлет запускает фоновое задание в каждом сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-191">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="116f1-192">Команда с помощью параметра **AsJob** выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="116f1-192">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="116f1-193">Эта команда возвращает объект задания, который содержит два дочерних объекта задания: один для каждого из заданий, запущенных на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-193">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="116f1-194">`Get-Job`Команда сохраняет объект задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-194">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="116f1-195">`$j`Затем переменная передается в `Format-List` командлет для вывода всех свойств объекта Job в списке.</span><span class="sxs-lookup"><span data-stu-id="116f1-195">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="116f1-196">Последняя команда возвращает результаты заданий.</span><span class="sxs-lookup"><span data-stu-id="116f1-196">The last command gets the results of the jobs.</span></span> <span data-ttu-id="116f1-197">Он передает объект задания в `$j` `Receive-Job` командлет и сохраняет результаты в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-197">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="116f1-198">Пример 9. Включение локальных переменных в команде, выполняемой на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="116f1-198">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="116f1-199">В этом примере показано, как включить значения локальных переменных в команду, запущенную на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-199">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="116f1-200">Команда использует `Using` Модификатор области для определения локальной переменной в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-200">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="116f1-201">По умолчанию предполагается, что все переменные определяются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-201">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="116f1-202">`Using`Модификатор области появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="116f1-202">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="116f1-203">Дополнительные сведения об `Using` модификаторе области см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md) и [about_Scopes](./about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-203">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "Windows PowerShell"
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-EventLog -LogName $Using:Log -Newest 10 }
```

<span data-ttu-id="116f1-204">`$Log`Переменная хранит имя журнала событий, Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="116f1-204">The `$Log` variable stores the name of the event log, Windows PowerShell.</span></span> <span data-ttu-id="116f1-205">`Invoke-Command`Командлет выполняется `Get-EventLog` в Server01 для получения десяти самых новых событий из журнала событий.</span><span class="sxs-lookup"><span data-stu-id="116f1-205">The `Invoke-Command` cmdlet runs `Get-EventLog` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="116f1-206">Значением параметра "параметр **задания" является** `$Log` переменная, которая предваряется `Using` модификатором области, чтобы указать, что она была создана в локальном сеансе, а не в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-206">The value of the **LogName** parameter is the `$Log` variable, which is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="116f1-207">Пример 10. Скрытие имени компьютера</span><span class="sxs-lookup"><span data-stu-id="116f1-207">Example 10: Hide the computer name</span></span>

<span data-ttu-id="116f1-208">В этом примере показан результат использования параметра **хидекомпутернаме** метода `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="116f1-208">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="116f1-209">**Хидекомпутернаме** не изменяет объект, возвращаемый этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="116f1-209">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="116f1-210">Он изменяет только отображение.</span><span class="sxs-lookup"><span data-stu-id="116f1-210">It changes only the display.</span></span> <span data-ttu-id="116f1-211">Вы по-прежнему можете использовать командлеты **Format** для вывода свойства **PSComputerName** любого из затронутых объектов.</span><span class="sxs-lookup"><span data-stu-id="116f1-211">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

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

<span data-ttu-id="116f1-212">Первые две команды используют `Invoke-Command` для выполнения `Get-Process` команды для процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="116f1-212">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="116f1-213">В выходных данных первой команды содержится свойство **PsComputerName** с именем компьютера, на котором запущена команда.</span><span class="sxs-lookup"><span data-stu-id="116f1-213">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="116f1-214">Выходные данные второй команды, в которой используется **хидекомпутернаме** , не включают столбец **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="116f1-214">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="116f1-215">Пример 11. Использование ключевого слова param в блоке script</span><span class="sxs-lookup"><span data-stu-id="116f1-215">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="116f1-216">`Param`Ключевое слово и параметр **ArgumentList** используются для передачи значений переменных в именованные параметры в блоке script.</span><span class="sxs-lookup"><span data-stu-id="116f1-216">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="116f1-217">В этом примере отображаются имена файлов, которые начинаются с буквы `a` и имеют `.pdf` расширение.</span><span class="sxs-lookup"><span data-stu-id="116f1-217">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="116f1-218">Дополнительные сведения о `Param` ключевом слове см. в разделе [about_Language_Keywords](./about/about_language_keywords.md#param).</span><span class="sxs-lookup"><span data-stu-id="116f1-218">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

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

<span data-ttu-id="116f1-219">`Invoke-Command` использует параметр **ScriptBlock** , определяющий две переменные: `$param1` и `$param2` .</span><span class="sxs-lookup"><span data-stu-id="116f1-219">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="116f1-220">`Get-ChildItem` использует именованные параметры, **Name** и **include** с именами переменных.</span><span class="sxs-lookup"><span data-stu-id="116f1-220">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="116f1-221">**ArgumentList** передает значения переменным.</span><span class="sxs-lookup"><span data-stu-id="116f1-221">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="116f1-222">Пример 12. Использование автоматической переменной $args в блоке сценария</span><span class="sxs-lookup"><span data-stu-id="116f1-222">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="116f1-223">`$args`Автоматическая переменная и параметр **ArgumentList** используются для передачи значений массива позициям параметров в блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-223">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="116f1-224">В этом примере отображается содержимое файлов каталога сервера `.txt` .</span><span class="sxs-lookup"><span data-stu-id="116f1-224">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="116f1-225">Параметр `Get-ChildItem` **path** имеет значение расположения 0, а параметр **фильтра** — "расположение"</span><span class="sxs-lookup"><span data-stu-id="116f1-225">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="116f1-226">Дополнительные сведения о `$args` переменной см. в разделе [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="116f1-226">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

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

<span data-ttu-id="116f1-227">`Invoke-Command` использует параметр **ScriptBlock** и `Get-ChildItem` задает `$args[0]` `$args[1]` значения массива и.</span><span class="sxs-lookup"><span data-stu-id="116f1-227">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="116f1-228">**ArgumentList** передает `$args` значения массива на `Get-ChildItem` позиции параметров для **path** и **Filter**.</span><span class="sxs-lookup"><span data-stu-id="116f1-228">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter**.</span></span>

### <span data-ttu-id="116f1-229">Пример 13. выполнение сценария на всех компьютерах, перечисленных в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="116f1-229">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="116f1-230">В этом примере используется `Invoke-Command` командлет для выполнения `Sample.ps1` скрипта на всех компьютерах, перечисленных в `Servers.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="116f1-230">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="116f1-231">Команда использует параметр **FilePath** , чтобы указать файл скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-231">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="116f1-232">Эта команда позволяет запустить сценарий на удаленных компьютерах, даже если файл скрипта недоступен для удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-232">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="116f1-233">При отправке команды содержимое `Sample.ps1` файла копируется в блок скрипта, а блок сценария выполняется на каждом удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-233">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="116f1-234">Эта процедура эквивалентна использованию параметра **ScriptBlock** для отправки содержимого скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-234">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="116f1-235">Пример 14. выполнение команды на удаленном компьютере с помощью URI</span><span class="sxs-lookup"><span data-stu-id="116f1-235">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="116f1-236">В этом примере показано, как выполнить команду на удаленном компьютере, идентифицируемом по универсальному идентификатору ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="116f1-236">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="116f1-237">В этом конкретном примере выполняется `Set-Mailbox` команда на удаленном сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="116f1-237">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

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

<span data-ttu-id="116f1-238">В первой строке используется `Get-Credential` командлет для хранения учетных данных Windows Live ID в `$LiveCred` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-238">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="116f1-239">PowerShell предлагает пользователю ввести учетные данные Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="116f1-239">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="116f1-240">`$parameters`Переменная является хэш-таблицей, содержащей параметры, передаваемые в `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="116f1-240">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="116f1-241">`Invoke-Command`Командлет выполняет `Set-Mailbox` команду, используя конфигурацию сеанса **Microsoft. Exchange** .</span><span class="sxs-lookup"><span data-stu-id="116f1-241">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="116f1-242">Параметр **ConnectionURI** указывает URL-адрес конечной точки сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="116f1-242">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="116f1-243">Параметр **Credential** указывает учетные данные, хранящиеся в `$LiveCred` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-243">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="116f1-244">Параметр **AuthenticationMechanism** указывает способ использования обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="116f1-244">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="116f1-245">Параметр **ScriptBlock** указывает блок скрипта, который содержит команду.</span><span class="sxs-lookup"><span data-stu-id="116f1-245">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="116f1-246">Пример 15. Использование параметра Session</span><span class="sxs-lookup"><span data-stu-id="116f1-246">Example 15: Use a session option</span></span>

<span data-ttu-id="116f1-247">В этом примере показано, как создать и использовать параметр **SessionOption** .</span><span class="sxs-lookup"><span data-stu-id="116f1-247">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="116f1-248">`New-PSSessionOption`Командлет создает объект параметра сеанса, который заставляет удаленный элемент не проверять центр сертификации, каноническое имя и списки отзыва при оценке ВХОДЯЩЕГО HTTPS-подключения.</span><span class="sxs-lookup"><span data-stu-id="116f1-248">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="116f1-249">Объект **SessionOption** сохраняется в `$so` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-249">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="116f1-250">Отключение этих проверок удобно для устранения неполадок, но очевидно небезопасно.</span><span class="sxs-lookup"><span data-stu-id="116f1-250">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="116f1-251">`Invoke-Command`Командлет запускает `Get-HotFix` команду удаленно.</span><span class="sxs-lookup"><span data-stu-id="116f1-251">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="116f1-252">Параметр **SessionOption** получает `$so` переменную.</span><span class="sxs-lookup"><span data-stu-id="116f1-252">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="116f1-253">Пример 16. Управление перенаправлением URI в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="116f1-253">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="116f1-254">В этом примере показано, как использовать параметры **AllowRedirection** и **SessionOption** для управления перенаправлением URI в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-254">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

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

<span data-ttu-id="116f1-255">`New-PSSessionOption`Командлет создает объект **PSSessionOption** , который сохраняется в `$max` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-255">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="116f1-256">Команда использует параметр **MaximumRedirection** , чтобы задать для свойства **MaximumConnectionRedirectionCount** объекта **PSSessionOption** значение 1.</span><span class="sxs-lookup"><span data-stu-id="116f1-256">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="116f1-257">`Invoke-Command`Командлет выполняет `Get-Mailbox` команду на удаленном сервере Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="116f1-257">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="116f1-258">Параметр **AllowRedirection** предоставляет явное разрешение для перенаправления подключения к альтернативной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="116f1-258">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="116f1-259">Параметр **SessionOption** использует объект Session, хранящийся в `$max` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-259">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="116f1-260">В результате, если удаленный компьютер, указанный параметром **ConnectionURI** , возвращает сообщение о перенаправлении, то PowerShell перенаправляет соединение, но если новое назначение возвращает другое сообщение перенаправления, то превышено значение счетчика перенаправления, равное 1, и `Invoke-Command` возвращает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="116f1-260">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="116f1-261">Пример 17. доступ к сетевой папке в удаленном сеансе</span><span class="sxs-lookup"><span data-stu-id="116f1-261">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="116f1-262">В этом примере показано, как получить доступ к сетевой папке из удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-262">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="116f1-263">Для демонстрации примера используются три компьютера.</span><span class="sxs-lookup"><span data-stu-id="116f1-263">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="116f1-264">Server01 — локальный компьютер, Server02 — удаленный компьютер, а Net03 содержит сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="116f1-264">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="116f1-265">Server01 подключается к Server02, а затем Server02 выполняет второй прыжок к Net03 для доступа к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="116f1-265">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="116f1-266">Дополнительные сведения о том, как удаленное взаимодействие PowerShell поддерживает переходы между компьютерами, см. [в статье Создание второго прыжка в удаленном взаимодействии PowerShell](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span><span class="sxs-lookup"><span data-stu-id="116f1-266">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="116f1-267">Требуемое делегирование поставщика поддержки безопасности учетных данных (CredSSP) включено в параметрах клиента на локальном компьютере и в параметрах службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-267">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="116f1-268">Для выполнения команд в этом примере необходимо быть членом группы " **Администраторы** " на локальном компьютере и удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-268">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

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

<span data-ttu-id="116f1-269">`Enable-WSManCredSSP`Командлет включает делегирование CredSSP с локального компьютера Server01 на удаленный компьютер Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-269">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="116f1-270">Параметр **Role** указывает **клиент** для настройки параметра клиента CredSSP на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-270">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="116f1-271">`New-PSSession` Создает объект **PSSession** для Server02 и сохраняет объект в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="116f1-271">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="116f1-272">`Invoke-Command`Командлет использует `$s` переменную для подключения к удаленному компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="116f1-272">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="116f1-273">Параметр **ScriptBlock** выполняется `Enable-WSManCredSSP` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-273">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="116f1-274">Параметр **Role** указывает **сервер** для настройки параметра сервера CredSSP на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-274">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="116f1-275">`$parameters`Переменная содержит значения параметров для подключения к сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="116f1-275">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="116f1-276">`Invoke-Command`Командлет выполняет `Get-Item` команду в сеансе в `$s` .</span><span class="sxs-lookup"><span data-stu-id="116f1-276">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="116f1-277">Эта команда возвращает скрипт из `\\Net03\Scripts` общей сетевой папки.</span><span class="sxs-lookup"><span data-stu-id="116f1-277">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="116f1-278">Команда использует параметр **authentication** со значением **CredSSP** и параметром **Credential** со значением **Domain01\Admin01**.</span><span class="sxs-lookup"><span data-stu-id="116f1-278">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01**.</span></span>

### <span data-ttu-id="116f1-279">Пример 18. Запуск сценариев на многих удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="116f1-279">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="116f1-280">В этом примере сценарий выполняется на более чем сотни компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-280">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="116f1-281">Чтобы свести к минимуму влияние на локальный компьютер, она подключается к каждому компьютеру, запускает скрипт, а затем отключается.</span><span class="sxs-lookup"><span data-stu-id="116f1-281">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="116f1-282">Скрипт продолжает выполняться в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="116f1-282">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="116f1-283">Команда использует `Invoke-Command` для запуска скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-283">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="116f1-284">Значение параметра **ComputerName** — это `Get-Content` команда, которая получает имена удаленных компьютеров из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="116f1-284">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="116f1-285">Параметр **InDisconnectedSession** отключает сеансы сразу при запуске команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-285">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="116f1-286">Значение параметра **FilePath** — это скрипт, который `Invoke-Command` выполняется на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-286">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="116f1-287">Значение **SessionOption** является хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="116f1-287">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="116f1-288">Для параметра **аутпутбуфферингмоде** устанавливается значение **Drop** , а для параметра **IdleTimeout** — значение **43200000** миллисекунд (12 часов).</span><span class="sxs-lookup"><span data-stu-id="116f1-288">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="116f1-289">Чтобы получить результаты выполнения команд и сценариев в отключенных сеансах, используйте `Receive-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="116f1-289">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

## <span data-ttu-id="116f1-290">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="116f1-290">PARAMETERS</span></span>

### <span data-ttu-id="116f1-291">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="116f1-291">-AllowRedirection</span></span>

<span data-ttu-id="116f1-292">Разрешает перенаправление данного соединения на альтернативный URI.</span><span class="sxs-lookup"><span data-stu-id="116f1-292">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="116f1-293">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="116f1-293">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="116f1-294">По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.</span><span class="sxs-lookup"><span data-stu-id="116f1-294">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="116f1-295">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="116f1-295">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="116f1-296">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="116f1-296">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="116f1-297">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="116f1-297">The default value is 5.</span></span>

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

### <span data-ttu-id="116f1-298">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="116f1-298">-ApplicationName</span></span>

<span data-ttu-id="116f1-299">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="116f1-299">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="116f1-300">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="116f1-300">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="116f1-301">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-301">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="116f1-302">Если эта переменная предпочтений не определена, по умолчанию используется значение WSMAN.</span><span class="sxs-lookup"><span data-stu-id="116f1-302">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="116f1-303">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="116f1-303">This value is appropriate for most uses.</span></span> <span data-ttu-id="116f1-304">Дополнительные сведения см. в разделе [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-304">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="116f1-305">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="116f1-305">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="116f1-306">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-306">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-307">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="116f1-307">-ArgumentList</span></span>

<span data-ttu-id="116f1-308">Предоставляет значения локальных переменных в команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-308">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="116f1-309">Переменные в команде заменяются этими значениями до выполнения команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-309">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="116f1-310">Введите значения в список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="116f1-310">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="116f1-311">Значения связаны с переменными в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="116f1-311">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="116f1-312">Псевдоним для **ArgumentList** — args.</span><span class="sxs-lookup"><span data-stu-id="116f1-312">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="116f1-313">Значения в параметре **ArgumentList** могут быть фактическими значениями, например 1024, или ссылками на локальные переменные, например `$max` .</span><span class="sxs-lookup"><span data-stu-id="116f1-313">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="116f1-314">Чтобы использовать локальные переменные в команде, воспользуйтесь следующим форматом команды:</span><span class="sxs-lookup"><span data-stu-id="116f1-314">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="116f1-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -или- `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="116f1-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="116f1-316">Ключевое слово **param** перечисляет локальные переменные, используемые в команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-316">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="116f1-317">**ArgumentList** предоставляет значения переменных в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="116f1-317">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="116f1-318">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="116f1-318">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="116f1-319">-AsJob</span><span class="sxs-lookup"><span data-stu-id="116f1-319">-AsJob</span></span>

<span data-ttu-id="116f1-320">Указывает, что этот командлет выполняет команду в качестве фонового задания на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-320">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="116f1-321">Этот параметр используется для выполнения команд, выполнение которых занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="116f1-321">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="116f1-322">При использовании параметра **AsJob** команда возвращает объект, представляющий задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="116f1-322">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="116f1-323">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="116f1-323">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="116f1-324">Для управления заданием используйте `*-Job` командлеты.</span><span class="sxs-lookup"><span data-stu-id="116f1-324">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="116f1-325">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="116f1-325">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="116f1-326">Параметр **AsJob** напоминает использование `Invoke-Command` командлета для `Start-Job` удаленного выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="116f1-326">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="116f1-327">Однако при использовании **AsJob** задание создается на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-327">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="116f1-328">Результаты удаленного задания автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-328">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="116f1-329">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-329">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-330">-Authentication</span><span class="sxs-lookup"><span data-stu-id="116f1-330">-Authentication</span></span>

<span data-ttu-id="116f1-331">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="116f1-331">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="116f1-332">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="116f1-332">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="116f1-333">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="116f1-333">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="116f1-334">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="116f1-334">Default</span></span>
- <span data-ttu-id="116f1-335">Базовый</span><span class="sxs-lookup"><span data-stu-id="116f1-335">Basic</span></span>
- <span data-ttu-id="116f1-336">CredSSP</span><span class="sxs-lookup"><span data-stu-id="116f1-336">Credssp</span></span>
- <span data-ttu-id="116f1-337">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="116f1-337">Digest</span></span>
- <span data-ttu-id="116f1-338">Kerberos</span><span class="sxs-lookup"><span data-stu-id="116f1-338">Kerberos</span></span>
- <span data-ttu-id="116f1-339">Согласование</span><span class="sxs-lookup"><span data-stu-id="116f1-339">Negotiate</span></span>
- <span data-ttu-id="116f1-340">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="116f1-340">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="116f1-341">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="116f1-341">The default value is Default.</span></span>

<span data-ttu-id="116f1-342">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="116f1-342">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="116f1-343">Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="116f1-343">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="116f1-344">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="116f1-344">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="116f1-345">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="116f1-345">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="116f1-346">Дополнительные сведения см. в разделе [поставщик поддержки безопасности учетных данных](/windows/win32/secauthn/credential-security-support-provider).</span><span class="sxs-lookup"><span data-stu-id="116f1-346">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-347">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="116f1-347">-CertificateThumbprint</span></span>

<span data-ttu-id="116f1-348">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="116f1-348">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="116f1-349">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="116f1-349">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="116f1-350">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="116f1-350">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="116f1-351">Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="116f1-351">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="116f1-352">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="116f1-352">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="116f1-353">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="116f1-353">-ComputerName</span></span>

<span data-ttu-id="116f1-354">Указывает компьютеры, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="116f1-354">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="116f1-355">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-355">The default is the local computer.</span></span>

<span data-ttu-id="116f1-356">При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется только для выполнения указанной команды и затем закрывается.</span><span class="sxs-lookup"><span data-stu-id="116f1-356">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="116f1-357">Если требуется постоянное подключение, используйте параметр **Session** .</span><span class="sxs-lookup"><span data-stu-id="116f1-357">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="116f1-358">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="116f1-358">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="116f1-359">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="116f1-359">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="116f1-360">Чтобы использовать IP-адрес в значении **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="116f1-360">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="116f1-361">Компьютер должен быть настроен для транспорта HTTPS, или IP-адрес удаленного компьютера должен быть включен в список **TrustedHosts** для WinRM локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="116f1-361">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="116f1-362">Инструкции по добавлению имени компьютера в список **TrustedHosts** см. в разделе [Добавление компьютера в список надежных узлов](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span><span class="sxs-lookup"><span data-stu-id="116f1-362">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="116f1-363">В Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение **ComputerName** необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="116f1-363">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-364">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="116f1-364">-ConfigurationName</span></span>

<span data-ttu-id="116f1-365">Указывает конфигурацию сеанса, используемую для нового **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="116f1-365">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="116f1-366">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-366">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="116f1-367">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="116f1-367">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="116f1-368">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-368">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="116f1-369">Если на удаленном компьютере не существует указанной конфигурации сеанса, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="116f1-369">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="116f1-370">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-370">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="116f1-371">Если эта переменная предпочтений не задана, по умолчанию используется **Microsoft. PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="116f1-371">If this preference variable isn't set, the default is **Microsoft.PowerShell**.</span></span> <span data-ttu-id="116f1-372">Дополнительные сведения см. в разделе [about_Preference_Variables](about/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-372">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-373">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="116f1-373">-ConnectionUri</span></span>

<span data-ttu-id="116f1-374">Задает универсальный код ресурса (URI), который определяет конечную точку подключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-374">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="116f1-375">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="116f1-375">The URI must be fully qualified.</span></span>

<span data-ttu-id="116f1-376">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="116f1-376">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="116f1-377">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="116f1-377">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="116f1-378">Если не указать URI соединения, можно использовать параметры **UseSSL** и **Port** , чтобы указать значения универсального кода ресурса (URI) соединения.</span><span class="sxs-lookup"><span data-stu-id="116f1-378">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="116f1-379">Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="116f1-379">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="116f1-380">Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс будет создан с использованием стандартов ports: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="116f1-380">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="116f1-381">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="116f1-381">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="116f1-382">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="116f1-382">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="116f1-383">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="116f1-383">-ContainerId</span></span>

<span data-ttu-id="116f1-384">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-384">Specifies an array of container IDs.</span></span>

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

### <span data-ttu-id="116f1-385">-Credential</span><span class="sxs-lookup"><span data-stu-id="116f1-385">-Credential</span></span>

<span data-ttu-id="116f1-386">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="116f1-386">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="116f1-387">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="116f1-387">The default is the current user.</span></span>

<span data-ttu-id="116f1-388">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="116f1-388">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="116f1-389">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="116f1-389">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="116f1-390">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="116f1-390">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="116f1-391">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="116f1-391">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="116f1-392">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="116f1-392">-EnableNetworkAccess</span></span>

<span data-ttu-id="116f1-393">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="116f1-393">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="116f1-394">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-394">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="116f1-395">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="116f1-395">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="116f1-396">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-396">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="116f1-397">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot ( `.` ), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="116f1-397">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="116f1-398">По умолчанию, сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-398">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="116f1-399">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="116f1-399">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="116f1-400">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="116f1-400">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="116f1-401">Можно разрешить удаленный доступ в сеансе замыкания на себя, используя значение **CredSSP** параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.</span><span class="sxs-lookup"><span data-stu-id="116f1-401">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="116f1-402">Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="116f1-402">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="116f1-403">Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="116f1-403">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="116f1-404">Для получения дополнительной информации см. `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="116f1-404">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="116f1-405">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="116f1-405">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-406">-FilePath</span><span class="sxs-lookup"><span data-stu-id="116f1-406">-FilePath</span></span>

<span data-ttu-id="116f1-407">Задает локальный скрипт, выполняемый этим командлетом на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-407">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="116f1-408">Введите путь и имя файла скрипта или передайте путь к сценарию `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="116f1-408">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="116f1-409">Сценарий должен существовать на локальном компьютере или в каталоге, к которому может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="116f1-409">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="116f1-410">Используйте **ArgumentList** , чтобы указать значения параметров в скрипте.</span><span class="sxs-lookup"><span data-stu-id="116f1-410">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="116f1-411">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта, передает блок сценария на удаленный компьютер и запускает его на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-411">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-412">-Хидекомпутернаме</span><span class="sxs-lookup"><span data-stu-id="116f1-412">-HideComputerName</span></span>

<span data-ttu-id="116f1-413">Указывает, что этот командлет опускает имя компьютера для каждого объекта, отображаемого в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="116f1-413">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="116f1-414">По умолчанию имя компьютера, создавшего объект, отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="116f1-414">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="116f1-415">Этот параметр влияет только на отображение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="116f1-415">This parameter affects only the output display.</span></span> <span data-ttu-id="116f1-416">Он не изменяет объект.</span><span class="sxs-lookup"><span data-stu-id="116f1-416">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases: HCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-417">-InDisconnectedSession</span><span class="sxs-lookup"><span data-stu-id="116f1-417">-InDisconnectedSession</span></span>

<span data-ttu-id="116f1-418">Указывает, что этот командлет запускает команду или сценарий в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="116f1-418">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="116f1-419">При использовании параметра **InDisconnectedSession** `Invoke-Command` создает постоянный сеанс на каждом удаленном компьютере, запускает команду, указанную параметром **ScriptBlock** или **FilePath** , а затем отключается от сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-419">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="116f1-420">Команды продолжают выполняться в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="116f1-420">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="116f1-421">**InDisconnectedSession** позволяет выполнять команды без подключения к удаленным сеансам.</span><span class="sxs-lookup"><span data-stu-id="116f1-421">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="116f1-422">И, поскольку сеанс отключается перед возвратом результатов, **InDisconnectedSession** гарантирует, что все результаты команды возвращаются к повторно подключенному сеансу, а не распределяются между сеансами.</span><span class="sxs-lookup"><span data-stu-id="116f1-422">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="116f1-423">Нельзя использовать **InDisconnectedSession** с параметром **Session** или **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="116f1-423">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="116f1-424">Команды, использующие **InDisconnectedSession** , возвращают объект **PSSession** , представляющий отключенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="116f1-424">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="116f1-425">Они не возвращают выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-425">They don't return the command output.</span></span> <span data-ttu-id="116f1-426">Чтобы подключиться к отключенному сеансу, используйте `Connect-PSSession` `Receive-PSSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="116f1-426">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="116f1-427">Чтобы получить результаты команд, которые выполнялись в сеансе, используйте `Receive-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="116f1-427">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="116f1-428">Чтобы выполнить команды, создающие выходные данные в отключенном сеансе, установите для параметра сеанса **аутпутбуфферингмоде** значение **Drop**.</span><span class="sxs-lookup"><span data-stu-id="116f1-428">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop**.</span></span> <span data-ttu-id="116f1-429">Если вы планируете подключиться к отключенному сеансу, установите время ожидания простоя в сеансе, чтобы обеспечить достаточное время для подключения перед удалением сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-429">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="116f1-430">Можно задать режим буферизации вывода и время ожидания простоя в параметре **SessionOption** или в `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="116f1-430">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="116f1-431">Дополнительные сведения о параметрах сеанса см. в статьях `New-PSSessionOption` и [about_Preference_Variables](./about/about_preference_variables.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-431">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="116f1-432">Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-432">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="116f1-433">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="116f1-433">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-434">-InputObject</span><span class="sxs-lookup"><span data-stu-id="116f1-434">-InputObject</span></span>

<span data-ttu-id="116f1-435">Указывает входные данные команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-435">Specifies input to the command.</span></span> <span data-ttu-id="116f1-436">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="116f1-436">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="116f1-437">При использовании параметра **InputObject** используйте `$Input` автоматическую переменную в значении параметра **ScriptBlock** для представления входных объектов.</span><span class="sxs-lookup"><span data-stu-id="116f1-437">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

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

### <span data-ttu-id="116f1-438">-JobName</span><span class="sxs-lookup"><span data-stu-id="116f1-438">-JobName</span></span>

<span data-ttu-id="116f1-439">Указывает понятное имя для фонового задания.</span><span class="sxs-lookup"><span data-stu-id="116f1-439">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="116f1-440">По умолчанию задания именуются `Job<n>` , где `<n>` — порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="116f1-440">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="116f1-441">Если в команде используется параметр **JobName** , команда выполняется как задание и `Invoke-Command` возвращает объект задания, даже если в команде не включена функция **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="116f1-441">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="116f1-442">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-442">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-443">-Ноневскопе</span><span class="sxs-lookup"><span data-stu-id="116f1-443">-NoNewScope</span></span>

<span data-ttu-id="116f1-444">Указывает, что этот командлет выполняет указанную команду в текущей области.</span><span class="sxs-lookup"><span data-stu-id="116f1-444">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="116f1-445">По умолчанию `Invoke-Command` выполняет команды в своей собственной области.</span><span class="sxs-lookup"><span data-stu-id="116f1-445">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="116f1-446">Этот параметр допустим только в командах, которые выполняются в текущем сеансе, т. е. в командах, которые пропускают как параметр **ComputerName** , так и параметр **Session**.</span><span class="sxs-lookup"><span data-stu-id="116f1-446">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="116f1-447">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="116f1-447">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="116f1-448">-Port</span><span class="sxs-lookup"><span data-stu-id="116f1-448">-Port</span></span>

<span data-ttu-id="116f1-449">Указывает сетевой порт на удаленном компьютере, используемый для этой команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-449">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="116f1-450">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="116f1-450">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="116f1-451">Порты по умолчанию: 5985 (порт WinRM для HTTP) и 5986 (порт WinRM для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="116f1-451">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="116f1-452">Перед использованием другого порта настройте прослушиватель WinRM на удаленном компьютере для прослушивания порта.</span><span class="sxs-lookup"><span data-stu-id="116f1-452">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="116f1-453">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="116f1-453">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="116f1-454">Не используйте параметр **Port** , если не требуется.</span><span class="sxs-lookup"><span data-stu-id="116f1-454">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="116f1-455">Порт, который задается в команде, применяется ко всем компьютерам или сеансам, в которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="116f1-455">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="116f1-456">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="116f1-456">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-457">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="116f1-457">-RunAsAdministrator</span></span>

<span data-ttu-id="116f1-458">Указывает, что этот командлет вызывает команду от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="116f1-458">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

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

### <span data-ttu-id="116f1-459">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="116f1-459">-ScriptBlock</span></span>

<span data-ttu-id="116f1-460">Указывает выполняющиеся команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-460">Specifies the commands to run.</span></span> <span data-ttu-id="116f1-461">Заключите команды в фигурные скобки, `{ }` чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="116f1-461">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="116f1-462">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="116f1-462">This parameter is required.</span></span>

<span data-ttu-id="116f1-463">По умолчанию все переменные в команде вычисляются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-463">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="116f1-464">Чтобы включить локальные переменные в команду, используйте **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="116f1-464">To include local variables in the command, use **ArgumentList**.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, ContainerId
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-465">-Session</span><span class="sxs-lookup"><span data-stu-id="116f1-465">-Session</span></span>

<span data-ttu-id="116f1-466">Указывает массив сеансов, в которых этот командлет выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="116f1-466">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="116f1-467">Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` команда или `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="116f1-467">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="116f1-468">При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="116f1-468">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="116f1-469">Используйте **PSSession** для выполнения ряда связанных команд, которые совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="116f1-469">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="116f1-470">Чтобы выполнить одну команду или ряд несвязанных команд, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="116f1-470">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="116f1-471">Дополнительные сведения см. в разделе [about_PSSessions](./About/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-471">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session, FilePathRunspace
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-472">-SessionName</span><span class="sxs-lookup"><span data-stu-id="116f1-472">-SessionName</span></span>

<span data-ttu-id="116f1-473">Задает понятное имя для отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-473">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="116f1-474">Имя можно использовать для ссылки на сеанс в последующих командах, таких как `Get-PSSession` команда.</span><span class="sxs-lookup"><span data-stu-id="116f1-474">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="116f1-475">Этот параметр допустим только при использовании с параметром **InDisconnectedSession**.</span><span class="sxs-lookup"><span data-stu-id="116f1-475">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="116f1-476">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="116f1-476">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-477">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="116f1-477">-SessionOption</span></span>

<span data-ttu-id="116f1-478">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-478">Specifies advanced options for the session.</span></span> <span data-ttu-id="116f1-479">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-479">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="116f1-480">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="116f1-480">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="116f1-481">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-481">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="116f1-482">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-482">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="116f1-483">Однако они не имеют приоритета над максимальными значениями, квотами или ограничениями, установленными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="116f1-483">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="116f1-484">Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="116f1-484">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="116f1-485">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-485">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="116f1-486">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="116f1-486">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-487">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="116f1-487">-ThrottleLimit</span></span>

<span data-ttu-id="116f1-488">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-488">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="116f1-489">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="116f1-489">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="116f1-490">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="116f1-490">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-491">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="116f1-491">-UseSSL</span></span>

<span data-ttu-id="116f1-492">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="116f1-492">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="116f1-493">По умолчанию протокол SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="116f1-493">By default, SSL isn't used.</span></span>

<span data-ttu-id="116f1-494">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="116f1-494">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="116f1-495">Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по протоколу HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="116f1-495">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="116f1-496">Если вы используете этот параметр, но протокол SSL недоступен в порте, используемом для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="116f1-496">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116f1-497">— VMId</span><span class="sxs-lookup"><span data-stu-id="116f1-497">-VMId</span></span>

<span data-ttu-id="116f1-498">Указывает массив идентификаторов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="116f1-498">Specifies an array of IDs of virtual machines.</span></span>

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

### <span data-ttu-id="116f1-499">-VMName</span><span class="sxs-lookup"><span data-stu-id="116f1-499">-VMName</span></span>

<span data-ttu-id="116f1-500">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="116f1-500">Specifies an array of names of virtual machines.</span></span>

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

### <span data-ttu-id="116f1-501">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="116f1-501">CommonParameters</span></span>

<span data-ttu-id="116f1-502">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="116f1-502">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="116f1-503">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="116f1-503">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="116f1-504">Входные данные</span><span class="sxs-lookup"><span data-stu-id="116f1-504">INPUTS</span></span>

### <span data-ttu-id="116f1-505">System. Management. Automation. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="116f1-505">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="116f1-506">Команду можно передать в блок скрипта в `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="116f1-506">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="116f1-507">Используйте `$Input` автоматическую переменную для представления входных объектов в команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-507">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="116f1-508">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="116f1-508">OUTPUTS</span></span>

### <span data-ttu-id="116f1-509">System. Management. Automation. Псремотингжоб, System. Management. Automation. пространства выполнения PSSession или выходные данные вызываемой команды</span><span class="sxs-lookup"><span data-stu-id="116f1-509">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="116f1-510">Этот командлет возвращает объект задания, если используется параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="116f1-510">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="116f1-511">Если указан параметр **InDisconnectedSession** , `Invoke-Command` возвращает объект **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="116f1-511">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="116f1-512">В противном случае он возвращает выходные данные вызванной команды, которая является значением параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="116f1-512">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="116f1-513">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="116f1-513">NOTES</span></span>

<span data-ttu-id="116f1-514">В Windows Vista и более поздних версиях операционной системы Windows для использования параметра **ComputerName** `Invoke-Command` функции для выполнения команды на локальном компьютере необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="116f1-514">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="116f1-515">При выполнении команд на нескольких компьютерах PowerShell подключается к компьютерам в том порядке, в котором они отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="116f1-515">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="116f1-516">Однако выходные данные команды отображаются в порядке их получения с удаленных компьютеров, которые могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="116f1-516">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="116f1-517">Ошибки, возникающие в результате выполнения команды, `Invoke-Command` включаются в результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="116f1-517">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="116f1-518">Ошибки, являющиеся неустранимыми в локальной команде, рассматриваются как устранимые в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="116f1-518">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="116f1-519">Эта стратегия гарантирует, что завершающие ошибки на одном компьютере не закрывают команду на всех компьютерах, на которых он выполняется.</span><span class="sxs-lookup"><span data-stu-id="116f1-519">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="116f1-520">Такой подход используется, даже если удаленная команда выполняется на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="116f1-520">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="116f1-521">Если удаленный компьютер не входит в домен, которому доверяет локальный компьютер, возможно, компьютер не сможет проверить подлинность учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="116f1-521">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="116f1-522">Чтобы добавить удаленный компьютер в список надежных узлов в службе WS-Management, используйте следующую команду в `WSMAN` поставщике, где `<Remote-Computer-Name>` — имя удаленного компьютера:</span><span class="sxs-lookup"><span data-stu-id="116f1-522">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="116f1-523">При отключении **PSSession** с помощью параметра **InDisconnectedSession** состояние сеанса **отключается** , а доступность — **нет**.</span><span class="sxs-lookup"><span data-stu-id="116f1-523">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None**.</span></span> <span data-ttu-id="116f1-524">Значение свойства **State** определяется текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="116f1-524">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="116f1-525">Значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="116f1-525">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="116f1-526">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="116f1-526">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="116f1-527">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="116f1-527">It might be connected to a different session.</span></span> <span data-ttu-id="116f1-528">Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.</span><span class="sxs-lookup"><span data-stu-id="116f1-528">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="116f1-529">Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="116f1-529">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="116f1-530">Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="116f1-530">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="116f1-531">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="116f1-531">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="116f1-532">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="116f1-532">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="116f1-533">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="116f1-533">RELATED LINKS</span></span>

[<span data-ttu-id="116f1-534">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="116f1-534">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="116f1-535">about_Remote</span><span class="sxs-lookup"><span data-stu-id="116f1-535">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="116f1-536">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="116f1-536">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="116f1-537">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="116f1-537">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="116f1-538">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="116f1-538">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="116f1-539">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="116f1-539">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="116f1-540">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="116f1-540">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="116f1-541">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="116f1-541">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="116f1-542">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="116f1-542">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="116f1-543">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="116f1-543">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="116f1-544">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="116f1-544">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="116f1-545">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="116f1-545">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="116f1-546">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="116f1-546">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
