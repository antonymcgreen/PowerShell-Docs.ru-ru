---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 3b087eb53fa575b2af7b18ec17823f9197e719d6
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "93230134"
---
# <span data-ttu-id="8631f-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-103">Enter-PSSession</span></span>

## <span data-ttu-id="8631f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8631f-104">SYNOPSIS</span></span>
<span data-ttu-id="8631f-105">Запускает интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="8631f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8631f-106">SYNTAX</span></span>

### <span data-ttu-id="8631f-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8631f-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-108">сшхост</span><span class="sxs-lookup"><span data-stu-id="8631f-108">SSHHost</span></span>

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### <span data-ttu-id="8631f-109">Сеанс</span><span class="sxs-lookup"><span data-stu-id="8631f-109">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-110">URI</span><span class="sxs-lookup"><span data-stu-id="8631f-110">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8631f-111">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-112">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8631f-112">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-113">Имя</span><span class="sxs-lookup"><span data-stu-id="8631f-113">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-114">VMId</span><span class="sxs-lookup"><span data-stu-id="8631f-114">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="8631f-115">VMName</span><span class="sxs-lookup"><span data-stu-id="8631f-115">VMName</span></span>

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="8631f-116">ContainerId</span><span class="sxs-lookup"><span data-stu-id="8631f-116">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="8631f-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8631f-117">DESCRIPTION</span></span>

<span data-ttu-id="8631f-118">`Enter-PSSession`Командлет запускает интерактивный сеанс с одним удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-118">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span>
<span data-ttu-id="8631f-119">Во время сеанса вводимые команды выполняются на удаленном компьютере, точно так же, как при вводе непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-119">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="8631f-120">В любой момент времени может использоваться только один интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="8631f-120">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="8631f-121">Как правило имя удаленного компьютера указывается с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="8631f-121">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="8631f-122">Однако можно также использовать сеанс, созданный с помощью `New-PSSession` командлета для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-122">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="8631f-123">Однако нельзя использовать `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` командлеты, или для отключения или повторного подключения к интерактивному сеансу.</span><span class="sxs-lookup"><span data-stu-id="8631f-123">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="8631f-124">Начиная с PowerShell 6,0 можно использовать Secure Shell (SSH) для установления подключения к удаленному компьютеру, если SSH доступен на локальном компьютере, а удаленный компьютер настроен с помощью конечной точки SSH PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8631f-124">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="8631f-125">Преимуществом удаленного сеанса PowerShell на основе SSH является то, что он работает на нескольких платформах (Windows, Linux, macOS).</span><span class="sxs-lookup"><span data-stu-id="8631f-125">The benefit an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="8631f-126">При удаленном взаимодействии на основе SSH используется параметр **HostName** , заданный для указания удаленного компьютера и соответствующих сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="8631f-126">For SSH based remoting you use the **HostName** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="8631f-127">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="8631f-127">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="8631f-128">Чтобы завершить интерактивный сеанс и отключиться от удаленного компьютера, используйте `Exit-PSSession` командлет или введите `exit` .</span><span class="sxs-lookup"><span data-stu-id="8631f-128">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="8631f-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="8631f-129">EXAMPLES</span></span>

### <span data-ttu-id="8631f-130">Пример 1. Запуск интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="8631f-130">Example 1: Start an interactive session</span></span>

```
PS> Enter-PSSession
[localhost]: PS>
```

<span data-ttu-id="8631f-131">Эта команда запускает интерактивный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-131">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="8631f-132">Командная строка изменяется, показывая, что команды выполняются в рамках другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-132">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="8631f-133">Вводимые команды выполняются в рамках нового сеанса, а результаты возвращаются в сеанс по умолчанию в виде текста.</span><span class="sxs-lookup"><span data-stu-id="8631f-133">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="8631f-134">Пример 2. Работа с интерактивным сеансом</span><span class="sxs-lookup"><span data-stu-id="8631f-134">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="8631f-135">Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с Server01, удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-135">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="8631f-136">При запуске сеанса в командную строку включается имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="8631f-136">When the session starts, the command prompt changes to include the computer name.</span></span>

<span data-ttu-id="8631f-137">Вторая команда получает процесс PowerShell и перенаправляет выходные данные в файл Process.txt.</span><span class="sxs-lookup"><span data-stu-id="8631f-137">The second command gets the PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="8631f-138">Команда передается на удаленный компьютер, и файл сохраняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-138">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>

<span data-ttu-id="8631f-139">Третья команда использует ключевое слово **Exit** для завершения интерактивного сеанса и закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="8631f-139">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="8631f-140">Четвертая команда позволяет убедиться в том, что файл Process.txt сохранен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-140">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="8631f-141">`Get-ChildItem`Команда ("Dir") на локальном компьютере не может найти файл.</span><span class="sxs-lookup"><span data-stu-id="8631f-141">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="8631f-142">Эта команда демонстрирует работу в интерактивном сеансе с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-142">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="8631f-143">Пример 3. Использование параметра Session</span><span class="sxs-lookup"><span data-stu-id="8631f-143">Example 3: Use the Session parameter</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

<span data-ttu-id="8631f-144">Эти команды используют параметр **сеанса** `Enter-PSSession` для запуска интерактивного сеанса в существующем сеансе PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="8631f-144">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="8631f-145">Пример 4. Запуск интерактивного сеанса и указание параметров порта и учетных данных</span><span class="sxs-lookup"><span data-stu-id="8631f-145">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

<span data-ttu-id="8631f-146">Эта команда запускает интерактивный сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="8631f-146">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="8631f-147">Он использует параметр **Port** , чтобы указать порт, а параметр **Credential** — учетную запись пользователя, имеющего разрешение на подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="8631f-147">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="8631f-148">Пример 5. Завершение интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="8631f-148">Example 5: Stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

<span data-ttu-id="8631f-149">В этом примере показано, как запускать и останавливать интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="8631f-149">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="8631f-150">Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="8631f-150">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="8631f-151">Вторая команда использует `Exit-PSSession` командлет для завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-151">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="8631f-152">Можно также использовать ключевое слово **Exit** для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-152">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="8631f-153">`Exit-PSSession` и **Exit** имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="8631f-153">`Exit-PSSession` and **Exit** have the same effect.</span></span>

### <span data-ttu-id="8631f-154">Пример 6. Запуск интерактивного сеанса с помощью SSH</span><span class="sxs-lookup"><span data-stu-id="8631f-154">Example 6: Start an interactive session using SSH</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="8631f-155">В этом примере показано, как запустить интерактивный сеанс с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="8631f-155">This example shows how to start an interactive session using Secure Shell (SSH).</span></span> <span data-ttu-id="8631f-156">Если на удаленном компьютере настроен протокол SSH для запроса паролей, вы получите запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="8631f-156">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span>
<span data-ttu-id="8631f-157">В противном случае необходимо будет использовать проверку подлинности пользователя на основе ключа SSH.</span><span class="sxs-lookup"><span data-stu-id="8631f-157">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="8631f-158">Пример 7. Запуск интерактивного сеанса с помощью SSH и указание ключа проверки подлинности порта и пользователя</span><span class="sxs-lookup"><span data-stu-id="8631f-158">Example 7: Start an interactive session using SSH and specify the Port and user authentication key</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="8631f-159">В этом примере показано, как запустить интерактивный сеанс с помощью SSH.</span><span class="sxs-lookup"><span data-stu-id="8631f-159">This example shows how to start an interactive session using SSH.</span></span> <span data-ttu-id="8631f-160">В нем используется параметр **Port** для указания используемого порта и параметр **KeyFilePath** для указания ключа RSA, используемого для проверки подлинности пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-160">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to authenticate the user on the remote computer.</span></span>

## <span data-ttu-id="8631f-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8631f-161">PARAMETERS</span></span>

### <span data-ttu-id="8631f-162">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="8631f-162">-AllowRedirection</span></span>

<span data-ttu-id="8631f-163">Разрешает перенаправление данного соединения на альтернативный URI.</span><span class="sxs-lookup"><span data-stu-id="8631f-163">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="8631f-164">По умолчанию перенаправление не допускается.</span><span class="sxs-lookup"><span data-stu-id="8631f-164">By default, redirection is not allowed.</span></span>

<span data-ttu-id="8631f-165">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="8631f-165">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="8631f-166">По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.</span><span class="sxs-lookup"><span data-stu-id="8631f-166">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="8631f-167">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="8631f-167">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="8631f-168">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="8631f-168">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="8631f-169">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="8631f-169">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-170">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="8631f-170">-ApplicationName</span></span>

<span data-ttu-id="8631f-171">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="8631f-171">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="8631f-172">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="8631f-172">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="8631f-173">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-173">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="8631f-174">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="8631f-174">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="8631f-175">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="8631f-175">This value is appropriate for most uses.</span></span> <span data-ttu-id="8631f-176">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8631f-176">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="8631f-177">Служба **WinRM** использует имя приложения для выбора прослушивателя, который будет обслуживать запрос на подключение.</span><span class="sxs-lookup"><span data-stu-id="8631f-177">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="8631f-178">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-178">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-179">-Authentication</span><span class="sxs-lookup"><span data-stu-id="8631f-179">-Authentication</span></span>

<span data-ttu-id="8631f-180">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="8631f-180">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="8631f-181">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8631f-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8631f-182">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8631f-182">Default</span></span>
- <span data-ttu-id="8631f-183">Базовый</span><span class="sxs-lookup"><span data-stu-id="8631f-183">Basic</span></span>
- <span data-ttu-id="8631f-184">CredSSP</span><span class="sxs-lookup"><span data-stu-id="8631f-184">Credssp</span></span>
- <span data-ttu-id="8631f-185">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="8631f-185">Digest</span></span>
- <span data-ttu-id="8631f-186">Kerberos</span><span class="sxs-lookup"><span data-stu-id="8631f-186">Kerberos</span></span>
- <span data-ttu-id="8631f-187">Согласование</span><span class="sxs-lookup"><span data-stu-id="8631f-187">Negotiate</span></span>
- <span data-ttu-id="8631f-188">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="8631f-188">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="8631f-189">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="8631f-189">The default value is Default.</span></span>

<span data-ttu-id="8631f-190">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="8631f-190">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="8631f-191">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="8631f-191">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="8631f-192">Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="8631f-192">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="8631f-193">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="8631f-193">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="8631f-194">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="8631f-194">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-195">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="8631f-195">-CertificateThumbprint</span></span>

<span data-ttu-id="8631f-196">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="8631f-196">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="8631f-197">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="8631f-197">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="8631f-198">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="8631f-198">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="8631f-199">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="8631f-199">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="8631f-200">Чтобы получить сертификат, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="8631f-200">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="8631f-201">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8631f-201">-ComputerName</span></span>

<span data-ttu-id="8631f-202">Указывает имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="8631f-202">Specifies a computer name.</span></span> <span data-ttu-id="8631f-203">Этот командлет запускает интерактивный сеанс с указанным удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-203">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="8631f-204">Введите имя одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="8631f-204">Enter only one computer name.</span></span> <span data-ttu-id="8631f-205">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8631f-205">The default is the local computer.</span></span>

<span data-ttu-id="8631f-206">Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="8631f-206">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="8631f-207">Можно также передать имя компьютера в `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="8631f-207">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="8631f-208">Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="8631f-208">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="8631f-209">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-209">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="8631f-210">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="8631f-210">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="8631f-211">Примечание. в Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение параметра **ComputerName** необходимо запустить PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="8631f-211">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start PowerShell with the Run as administrator option.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-212">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="8631f-212">-ConfigurationName</span></span>

<span data-ttu-id="8631f-213">Задает конфигурацию сеанса, используемого для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-213">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="8631f-214">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-214">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="8631f-215">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="8631f-215">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="8631f-216">При использовании с SSH указывает подсистему для использования в целевом объекте, как определено в sshd_config.</span><span class="sxs-lookup"><span data-stu-id="8631f-216">When used with SSH, this specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="8631f-217">Значение по умолчанию для SSH — `powershell` подсистема.</span><span class="sxs-lookup"><span data-stu-id="8631f-217">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="8631f-218">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-218">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="8631f-219">Если указанной конфигурации сеанса нет на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8631f-219">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="8631f-220">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-220">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="8631f-221">Если эта привилегированная переменная не определена, значением по умолчанию является Microsoft.PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8631f-221">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="8631f-222">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8631f-222">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-223">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="8631f-223">-ConnectionUri</span></span>

<span data-ttu-id="8631f-224">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-224">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="8631f-225">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="8631f-225">The URI must be fully qualified.</span></span> <span data-ttu-id="8631f-226">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="8631f-226">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="8631f-227">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8631f-227">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="8631f-228">Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="8631f-228">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="8631f-229">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8631f-229">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="8631f-230">Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс создается с использованием стандартных портов: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8631f-230">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="8631f-231">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8631f-231">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="8631f-232">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="8631f-232">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-233">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="8631f-233">-ContainerId</span></span>

<span data-ttu-id="8631f-234">Указывает идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="8631f-234">Specifies the ID of a container.</span></span>

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-235">-Credential</span><span class="sxs-lookup"><span data-stu-id="8631f-235">-Credential</span></span>

<span data-ttu-id="8631f-236">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="8631f-236">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="8631f-237">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="8631f-237">The default is the current user.</span></span>

<span data-ttu-id="8631f-238">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="8631f-238">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8631f-239">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="8631f-239">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="8631f-240">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="8631f-240">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="8631f-241">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="8631f-241">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-242">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="8631f-242">-EnableNetworkAccess</span></span>

<span data-ttu-id="8631f-243">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="8631f-243">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="8631f-244">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8631f-244">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="8631f-245">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="8631f-245">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="8631f-246">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-246">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="8631f-247">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение.</span><span class="sxs-lookup"><span data-stu-id="8631f-247">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="8631f-248">(точка), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="8631f-248">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="8631f-249">По умолчанию сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8631f-249">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="8631f-250">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="8631f-250">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="8631f-251">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="8631f-251">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="8631f-252">Удаленный доступ в петлевом сеансе также можно разрешить с помощью значения **CredSSP** параметра **Authentication** , который делегирует учетные данные сеанса на другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="8631f-252">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="8631f-253">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8631f-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-254">-HostName</span><span class="sxs-lookup"><span data-stu-id="8631f-254">-HostName</span></span>

<span data-ttu-id="8631f-255">Указывает имя компьютера для подключения на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="8631f-255">Specifies a computer name for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="8631f-256">Это похоже на параметр **ComputerName** , за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.</span><span class="sxs-lookup"><span data-stu-id="8631f-256">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span> <span data-ttu-id="8631f-257">Этот параметр поддерживает указание имени пользователя и/или порта в качестве части значения параметра имени узла с помощью формы `user@hostname:port` .</span><span class="sxs-lookup"><span data-stu-id="8631f-257">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span> <span data-ttu-id="8631f-258">Имя пользователя и (или) порт, указанный как часть имени узла, имеет приоритет над `-UserName` параметрами и `-Port` , если они заданы.</span><span class="sxs-lookup"><span data-stu-id="8631f-258">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span> <span data-ttu-id="8631f-259">Это позволяет передавать этому параметру несколько имен компьютеров, где некоторые имеют определенные имена пользователей и (или) порты, а другие используют имя пользователя и (или) порт `-UserName` из `-Port` параметров и.</span><span class="sxs-lookup"><span data-stu-id="8631f-259">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="8631f-260">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8631f-260">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-261">-Id</span><span class="sxs-lookup"><span data-stu-id="8631f-261">-Id</span></span>

<span data-ttu-id="8631f-262">Указывает идентификатор существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-262">Specifies the ID of an existing session.</span></span> <span data-ttu-id="8631f-263">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-263">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="8631f-264">Чтобы найти идентификатор сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="8631f-264">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-265">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8631f-265">-InstanceId</span></span>

<span data-ttu-id="8631f-266">Указывает идентификатор экземпляра существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-266">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="8631f-267">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-267">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="8631f-268">Значение идентификатора экземпляра представляет собой GUID.</span><span class="sxs-lookup"><span data-stu-id="8631f-268">The instance ID is a GUID.</span></span> <span data-ttu-id="8631f-269">Чтобы найти идентификатор экземпляра сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="8631f-269">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="8631f-270">Можно также использовать параметры **Session** , **Name** или **ID** , чтобы указать существующий сеанс.</span><span class="sxs-lookup"><span data-stu-id="8631f-270">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="8631f-271">Можно также использовать параметр **ComputerName** для запуска временного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-271">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-272">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="8631f-272">-KeyFilePath</span></span>

<span data-ttu-id="8631f-273">Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-273">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="8631f-274">SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля.</span><span class="sxs-lookup"><span data-stu-id="8631f-274">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="8631f-275">Если на удаленном компьютере настроена проверка подлинности с помощью ключа, этот параметр можно использовать для предоставления ключа, определяющего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8631f-275">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="8631f-276">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8631f-276">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-277">-Name</span><span class="sxs-lookup"><span data-stu-id="8631f-277">-Name</span></span>

<span data-ttu-id="8631f-278">Указывает понятное имя существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-278">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="8631f-279">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-279">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="8631f-280">Если указанное имя соответствует сразу нескольким сеансам, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8631f-280">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="8631f-281">Можно также использовать параметры **Session** , **InstanceId** или **ID** , чтобы указать существующий сеанс.</span><span class="sxs-lookup"><span data-stu-id="8631f-281">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="8631f-282">Можно также использовать параметр **ComputerName** для запуска временного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-282">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="8631f-283">Чтобы установить понятное имя для сеанса, используйте параметр **Name** `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="8631f-283">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-284">-Port</span><span class="sxs-lookup"><span data-stu-id="8631f-284">-Port</span></span>

<span data-ttu-id="8631f-285">Указывает сетевой порт на удаленном компьютере, используемый для этой команды.</span><span class="sxs-lookup"><span data-stu-id="8631f-285">Specifies the network port on the remote computer that is used for this command.</span></span>

<span data-ttu-id="8631f-286">В PowerShell 6,0 этот параметр был включено в наборе параметров **HostName** , который поддерживает подключения Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="8631f-286">In PowerShell 6.0 this parameter was inlcuded in the **HostName** parameter set which supports Secure Shell (SSH) connections.</span></span>

<span data-ttu-id="8631f-287">**WinRM (набор параметров ComputerName)**</span><span class="sxs-lookup"><span data-stu-id="8631f-287">**WinRM (ComputerName parameter set)**</span></span>

<span data-ttu-id="8631f-288">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="8631f-288">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="8631f-289">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8631f-289">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="8631f-290">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="8631f-290">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="8631f-291">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="8631f-291">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="8631f-292">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="8631f-292">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="8631f-293">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="8631f-293">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="8631f-294">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8631f-294">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="8631f-295">**SSH (набор параметров HostName)**</span><span class="sxs-lookup"><span data-stu-id="8631f-295">**SSH (HostName parameter set)**</span></span>

<span data-ttu-id="8631f-296">Для подключения к удаленному компьютеру на удаленном компьютере должна быть настроена служба SSH (SSHD) и он должен прослушивать порт, используемый подключением.</span><span class="sxs-lookup"><span data-stu-id="8631f-296">To connect to a remote computer, the remote computer must be configured with the SSH service (SSHD) and must be listening on the port that the connection uses.</span></span> <span data-ttu-id="8631f-297">По умолчанию для SSH используется порт 22.</span><span class="sxs-lookup"><span data-stu-id="8631f-297">The default port for SSH is 22.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-298">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="8631f-298">-RunAsAdministrator</span></span>

<span data-ttu-id="8631f-299">Указывает, что **сеанс PSSession** запускается от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="8631f-299">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-300">-Session</span><span class="sxs-lookup"><span data-stu-id="8631f-300">-Session</span></span>

<span data-ttu-id="8631f-301">Указывает сеанс PowerShell ( **PSSession** ), используемый для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-301">Specifies a PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="8631f-302">Этот параметр принимает объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-302">This parameter takes a session object.</span></span> <span data-ttu-id="8631f-303">Для указания **PSSession** можно также использовать параметры **Name** , **InstanceId** или **ID** .</span><span class="sxs-lookup"><span data-stu-id="8631f-303">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession** .</span></span>

<span data-ttu-id="8631f-304">Введите переменную, содержащую объект сеанса, или команду, которая создает или получает объект сеанса, например `New-PSSession` `Get-PSSession` команду или.</span><span class="sxs-lookup"><span data-stu-id="8631f-304">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="8631f-305">Можно также передать объект сеанса в `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="8631f-305">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="8631f-306">С помощью этого параметра можно отправить только один **сеанс PSSession** .</span><span class="sxs-lookup"><span data-stu-id="8631f-306">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="8631f-307">Если ввести переменную, содержащую более одного **сеанса PSSession** , команда завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8631f-307">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="8631f-308">При использовании `Exit-PSSession` или ключевого слова **Exit** интерактивный сеанс завершается, но созданный **сеанс PSSession** остается открытым и доступным для использования.</span><span class="sxs-lookup"><span data-stu-id="8631f-308">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-309">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="8631f-309">-SessionOption</span></span>

<span data-ttu-id="8631f-310">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-310">Sets advanced options for the session.</span></span> <span data-ttu-id="8631f-311">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-311">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="8631f-312">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="8631f-312">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="8631f-313">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-313">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="8631f-314">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-314">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="8631f-315">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-315">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="8631f-316">Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="8631f-316">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="8631f-317">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8631f-317">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="8631f-318">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8631f-318">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-319">-Сштранспорт</span><span class="sxs-lookup"><span data-stu-id="8631f-319">-SSHTransport</span></span>

<span data-ttu-id="8631f-320">Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="8631f-320">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="8631f-321">По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="8631f-321">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="8631f-322">Этот параметр заставляет PowerShell использовать набор параметров HostName для установления удаленного подключения на основе SSH.</span><span class="sxs-lookup"><span data-stu-id="8631f-322">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="8631f-323">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8631f-323">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-324">-Подсистема</span><span class="sxs-lookup"><span data-stu-id="8631f-324">-Subsystem</span></span>

<span data-ttu-id="8631f-325">Указывает подсистему SSH, используемую для нового **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="8631f-325">Specifies the SSH subsystem used for the new **PSSession** .</span></span>

<span data-ttu-id="8631f-326">Указывает подсистему для использования в целевом объекте, как определено в sshd_config.</span><span class="sxs-lookup"><span data-stu-id="8631f-326">This specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="8631f-327">Подсистема запускает определенную версию PowerShell с предопределенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8631f-327">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span> <span data-ttu-id="8631f-328">Если указанная подсистема не существует на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8631f-328">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="8631f-329">Если этот параметр не используется, по умолчанию используется подсистема PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8631f-329">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

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

### <span data-ttu-id="8631f-330">-UserName</span><span class="sxs-lookup"><span data-stu-id="8631f-330">-UserName</span></span>

<span data-ttu-id="8631f-331">Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-331">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="8631f-332">Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-332">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="8631f-333">Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="8631f-333">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="8631f-334">Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра **KeyFilePath** . при этом запрос на ввод пароля не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="8631f-334">If SSH is configured for key based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt will occur.</span></span> <span data-ttu-id="8631f-335">Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр **KeyFilePath** не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="8631f-335">Note that if the client user key file is located in an SSH known location then the **KeyFilePath** parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="8631f-336">Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.</span><span class="sxs-lookup"><span data-stu-id="8631f-336">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="8631f-337">Этот параметр не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8631f-337">This is not a required parameter.</span></span> <span data-ttu-id="8631f-338">Если параметр **username** не указан, то для соединения используется текущее имя пользователя для входа.</span><span class="sxs-lookup"><span data-stu-id="8631f-338">If no **UserName** parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="8631f-339">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8631f-339">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-340">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="8631f-340">-UseSSL</span></span>

<span data-ttu-id="8631f-341">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="8631f-341">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="8631f-342">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="8631f-342">By default, SSL is not used.</span></span>

<span data-ttu-id="8631f-343">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="8631f-343">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="8631f-344">Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="8631f-344">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="8631f-345">Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8631f-345">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-346">— VMId</span><span class="sxs-lookup"><span data-stu-id="8631f-346">-VMId</span></span>

<span data-ttu-id="8631f-347">Указывает идентификатор виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="8631f-347">Specifies the ID of a virtual machine.</span></span>

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-348">-VMName</span><span class="sxs-lookup"><span data-stu-id="8631f-348">-VMName</span></span>

<span data-ttu-id="8631f-349">Указывает имя виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="8631f-349">Specifies the name of a virtual machine.</span></span>

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8631f-350">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8631f-350">CommonParameters</span></span>

<span data-ttu-id="8631f-351">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8631f-351">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8631f-352">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8631f-352">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8631f-353">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8631f-353">INPUTS</span></span>

### <span data-ttu-id="8631f-354">System. String, System. Management. Automation. пространства выполнения PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-354">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="8631f-355">В этот командлет можно передать по конвейеру имя компьютера в виде строки или объекта сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-355">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="8631f-356">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8631f-356">OUTPUTS</span></span>

### <span data-ttu-id="8631f-357">Нет</span><span class="sxs-lookup"><span data-stu-id="8631f-357">None</span></span>

<span data-ttu-id="8631f-358">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8631f-358">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="8631f-359">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8631f-359">NOTES</span></span>

<span data-ttu-id="8631f-360">Чтобы подключиться к удаленному компьютеру, необходимо быть членом группы администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-360">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="8631f-361">Чтобы запустить интерактивный сеанс на локальном компьютере, необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="8631f-361">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="8631f-362">При использовании `Enter-PSSession` для интерактивного сеанса используется профиль пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8631f-362">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="8631f-363">Команды в профиле удаленного пользователя, включая команды для добавления модулей PowerShell и изменения командной строки, выполняются перед отображением удаленного запроса.</span><span class="sxs-lookup"><span data-stu-id="8631f-363">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="8631f-364">`Enter-PSSession` использует параметр языка и региональных параметров пользовательского интерфейса на локальном компьютере для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8631f-364">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="8631f-365">Чтобы найти язык и региональные параметры локального пользовательского интерфейса, используйте `$UICulture` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="8631f-365">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="8631f-366">`Enter-PSSession` требуются `Get-Command` `Out-Default` командлеты, и `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="8631f-366">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="8631f-367">Если эти командлеты не включены в конфигурацию сеанса на удаленном компьютере, команды не будут `Enter-PSSession` работать.</span><span class="sxs-lookup"><span data-stu-id="8631f-367">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="8631f-368">В отличие от `Invoke-Command` , который анализирует и интерпретирует команды перед их отправкой на удаленный компьютер, `Enter-PSSession` отправляет команды непосредственно на удаленный компьютер без интерпретации.</span><span class="sxs-lookup"><span data-stu-id="8631f-368">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="8631f-369">Если сеанс, который вы хотите ввести, занят обработкой команды, может возникнуть задержка, прежде чем PowerShell ответит на `Enter-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="8631f-369">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="8631f-370">Вы подключены сразу после того, как сеанс будет доступен.</span><span class="sxs-lookup"><span data-stu-id="8631f-370">You are connected as soon as the session is available.</span></span> <span data-ttu-id="8631f-371">Чтобы отменить `Enter-PSSession` команду, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8631f-371">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="8631f-372">Набор параметров **HostName** был добавлен начиная с PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8631f-372">The **HostName** parameter set was included starting with PowerShell 6.0.</span></span> <span data-ttu-id="8631f-373">Он был добавлен для обеспечения удаленного взаимодействия PowerShell на основе Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="8631f-373">It was added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="8631f-374">SSH и PowerShell поддерживаются на нескольких платформах (Windows, Linux, macOS) и удаленное взаимодействие PowerShell будет работать на этих платформах, где установлены и настроены PowerShell и SSH.</span><span class="sxs-lookup"><span data-stu-id="8631f-374">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="8631f-375">Это отдельно от предыдущего удаленного взаимодействия только в Windows, основанного на WinRM, и многие функции и ограничения WinRM не применяются.</span><span class="sxs-lookup"><span data-stu-id="8631f-375">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="8631f-376">Например, квоты на основе WinRM, параметры сеанса, конфигурация пользовательской конечной точки и функции отключения и повторного подключения сейчас не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8631f-376">For example, WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="8631f-377">Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="8631f-377">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="8631f-378">До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком.</span><span class="sxs-lookup"><span data-stu-id="8631f-378">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="8631f-379">Эта возможность была ограничена сеансами через WinRM.</span><span class="sxs-lookup"><span data-stu-id="8631f-379">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="8631f-380">PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="8631f-380">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="8631f-381">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8631f-381">RELATED LINKS</span></span>

[<span data-ttu-id="8631f-382">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="8631f-382">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="8631f-383">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-383">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="8631f-384">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8631f-384">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="8631f-385">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-385">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="8631f-386">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-386">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="8631f-387">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-387">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="8631f-388">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-388">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="8631f-389">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="8631f-389">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="8631f-390">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="8631f-390">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="8631f-391">about_Remote</span><span class="sxs-lookup"><span data-stu-id="8631f-391">about_Remote</span></span>](About/about_Remote.md)
