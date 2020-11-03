---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 40d9da7d2e7e3233608b893b026c2b89c7155ab1
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "93230133"
---
# <span data-ttu-id="95650-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-103">Enter-PSSession</span></span>

## <span data-ttu-id="95650-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="95650-104">SYNOPSIS</span></span>
<span data-ttu-id="95650-105">Запускает интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="95650-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95650-106">SYNTAX</span></span>

### <span data-ttu-id="95650-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="95650-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="95650-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="95650-108">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="95650-109">URI</span><span class="sxs-lookup"><span data-stu-id="95650-109">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="95650-110">InstanceId</span><span class="sxs-lookup"><span data-stu-id="95650-110">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="95650-111">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="95650-111">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="95650-112">Имя</span><span class="sxs-lookup"><span data-stu-id="95650-112">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="95650-113">VMId</span><span class="sxs-lookup"><span data-stu-id="95650-113">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> -Credential <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="95650-114">VMName</span><span class="sxs-lookup"><span data-stu-id="95650-114">VMName</span></span>

```
Enter-PSSession [-VMName] <String> -Credential <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="95650-115">ContainerId</span><span class="sxs-lookup"><span data-stu-id="95650-115">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="95650-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95650-116">DESCRIPTION</span></span>

<span data-ttu-id="95650-117">`Enter-PSSession`Командлет запускает интерактивный сеанс с одним удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-117">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span> <span data-ttu-id="95650-118">Во время сеанса вводимые команды выполняются на удаленном компьютере, точно так же, как при вводе непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-118">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="95650-119">В любой момент времени может использоваться только один интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="95650-119">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="95650-120">Как правило имя удаленного компьютера указывается с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="95650-120">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="95650-121">Однако можно также использовать сеанс, созданный с помощью `New-PSSession` командлета для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-121">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="95650-122">Однако нельзя использовать `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` командлеты, или для отключения или повторного подключения к интерактивному сеансу.</span><span class="sxs-lookup"><span data-stu-id="95650-122">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="95650-123">Чтобы завершить интерактивный сеанс и отключиться от удаленного компьютера, используйте `Exit-PSSession` командлет или введите `exit` .</span><span class="sxs-lookup"><span data-stu-id="95650-123">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="95650-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="95650-124">EXAMPLES</span></span>

### <span data-ttu-id="95650-125">Пример 1. Запуск интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="95650-125">Example 1: Start an interactive session</span></span>

```
PS C:\> Enter-PSSession
[localhost]: PS C:\>
```

<span data-ttu-id="95650-126">Эта команда запускает интерактивный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-126">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="95650-127">Командная строка изменяется, показывая, что команды выполняются в рамках другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-127">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="95650-128">Вводимые команды выполняются в рамках нового сеанса, а результаты возвращаются в сеанс по умолчанию в виде текста.</span><span class="sxs-lookup"><span data-stu-id="95650-128">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="95650-129">Пример 2. Работа с интерактивным сеансом</span><span class="sxs-lookup"><span data-stu-id="95650-129">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="95650-130">Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с Server01, удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-130">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="95650-131">При запуске сеанса в командную строку включается имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="95650-131">When the session starts, the command prompt changes to include the computer name.</span></span>
<span data-ttu-id="95650-132">Вторая команда получает процесс Windows PowerShell и перенаправляет выходные данные в файл Process.txt.</span><span class="sxs-lookup"><span data-stu-id="95650-132">The second command gets the Windows PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="95650-133">Команда передается на удаленный компьютер, и файл сохраняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-133">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>
<span data-ttu-id="95650-134">Третья команда использует ключевое слово **Exit** для завершения интерактивного сеанса и закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="95650-134">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="95650-135">Четвертая команда позволяет убедиться в том, что файл Process.txt сохранен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-135">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="95650-136">`Get-ChildItem`Команда ("Dir") на локальном компьютере не может найти файл.</span><span class="sxs-lookup"><span data-stu-id="95650-136">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="95650-137">Эта команда демонстрирует работу в интерактивном сеансе с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-137">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="95650-138">Пример 3. Использование параметра Session</span><span class="sxs-lookup"><span data-stu-id="95650-138">Example 3: Use the Session parameter</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
[Server01]: PS C:\>
```

<span data-ttu-id="95650-139">Эти команды используют параметр **сеанса** `Enter-PSSession` для выполнения интерактивного сеанса в существующем сеансе Windows PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="95650-139">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing Windows PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="95650-140">Пример 4. Запуск интерактивного сеанса и указание параметров порта и учетных данных</span><span class="sxs-lookup"><span data-stu-id="95650-140">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS C:\>
```

<span data-ttu-id="95650-141">Эта команда запускает интерактивный сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="95650-141">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="95650-142">Он использует параметр **Port** , чтобы указать порт, а параметр **Credential** — учетную запись пользователя, имеющего разрешение на подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="95650-142">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="95650-143">Пример 5. Завершение интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="95650-143">Example 5: Stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\> Exit-PSSession
PS C:\>
```

<span data-ttu-id="95650-144">В этом примере показано, как запускать и останавливать интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="95650-144">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="95650-145">Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="95650-145">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="95650-146">Вторая команда использует `Exit-PSSession` командлет для завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-146">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="95650-147">Можно также использовать ключевое слово **Exit** для завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-147">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="95650-148">`Exit-PSSession` и **Exit** имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="95650-148">`Exit-PSSession` and **Exit** have the same effect.</span></span>

## <span data-ttu-id="95650-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95650-149">PARAMETERS</span></span>

### <span data-ttu-id="95650-150">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="95650-150">-AllowRedirection</span></span>

<span data-ttu-id="95650-151">Разрешает перенаправление данного соединения на альтернативный URI.</span><span class="sxs-lookup"><span data-stu-id="95650-151">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="95650-152">По умолчанию перенаправление не допускается.</span><span class="sxs-lookup"><span data-stu-id="95650-152">By default, redirection is not allowed.</span></span>

<span data-ttu-id="95650-153">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="95650-153">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="95650-154">По умолчанию Windows PowerShell не перенаправляет соединения, но можно воспользоваться этим параметром и разрешить перенаправление соединений.</span><span class="sxs-lookup"><span data-stu-id="95650-154">By default, Windows PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="95650-155">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="95650-155">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="95650-156">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="95650-156">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="95650-157">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="95650-157">The default value is 5.</span></span>

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

### <span data-ttu-id="95650-158">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="95650-158">-ApplicationName</span></span>

<span data-ttu-id="95650-159">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="95650-159">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="95650-160">Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="95650-160">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="95650-161">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-161">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="95650-162">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="95650-162">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="95650-163">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="95650-163">This value is appropriate for most uses.</span></span> <span data-ttu-id="95650-164">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="95650-164">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="95650-165">Служба **WinRM** использует имя приложения для выбора прослушивателя, который будет обслуживать запрос на подключение.</span><span class="sxs-lookup"><span data-stu-id="95650-165">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="95650-166">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-166">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="95650-167">-Authentication</span><span class="sxs-lookup"><span data-stu-id="95650-167">-Authentication</span></span>

<span data-ttu-id="95650-168">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="95650-168">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="95650-169">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="95650-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="95650-170">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="95650-170">Default</span></span>
- <span data-ttu-id="95650-171">Базовый</span><span class="sxs-lookup"><span data-stu-id="95650-171">Basic</span></span>
- <span data-ttu-id="95650-172">CredSSP</span><span class="sxs-lookup"><span data-stu-id="95650-172">Credssp</span></span>
- <span data-ttu-id="95650-173">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="95650-173">Digest</span></span>
- <span data-ttu-id="95650-174">Kerberos</span><span class="sxs-lookup"><span data-stu-id="95650-174">Kerberos</span></span>
- <span data-ttu-id="95650-175">Согласование</span><span class="sxs-lookup"><span data-stu-id="95650-175">Negotiate</span></span>
- <span data-ttu-id="95650-176">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="95650-176">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="95650-177">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="95650-177">The default value is Default.</span></span>

<span data-ttu-id="95650-178">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="95650-178">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="95650-179">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="95650-179">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="95650-180">Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="95650-180">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="95650-181">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="95650-181">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="95650-182">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="95650-182">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="95650-183">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="95650-183">-CertificateThumbprint</span></span>

<span data-ttu-id="95650-184">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="95650-184">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="95650-185">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="95650-185">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="95650-186">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="95650-186">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="95650-187">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="95650-187">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="95650-188">Чтобы получить сертификат, используйте `Get-Item` `Get-ChildItem` команду или на диске Windows PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="95650-188">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="95650-189">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="95650-189">-ComputerName</span></span>

<span data-ttu-id="95650-190">Указывает имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="95650-190">Specifies a computer name.</span></span> <span data-ttu-id="95650-191">Этот командлет запускает интерактивный сеанс с указанным удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-191">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="95650-192">Введите имя одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="95650-192">Enter only one computer name.</span></span> <span data-ttu-id="95650-193">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="95650-193">The default is the local computer.</span></span>

<span data-ttu-id="95650-194">Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="95650-194">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="95650-195">Можно также передать имя компьютера в `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="95650-195">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="95650-196">Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="95650-196">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="95650-197">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-197">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="95650-198">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="95650-198">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="95650-199">Примечание. в Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение параметра **ComputerName** необходимо запустить Windows PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="95650-199">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start Windows PowerShell with the Run as administrator option.</span></span>

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

### <span data-ttu-id="95650-200">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="95650-200">-ConfigurationName</span></span>

<span data-ttu-id="95650-201">Задает конфигурацию сеанса, используемого для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-201">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="95650-202">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-202">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="95650-203">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="95650-203">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="95650-204">Конфигурация сеанса для сеанса размещается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-204">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="95650-205">Если указанной конфигурации сеанса нет на удаленном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="95650-205">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="95650-206">Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-206">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="95650-207">Если эта привилегированная переменная не определена, значением по умолчанию является Microsoft.PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95650-207">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="95650-208">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="95650-208">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="95650-209">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="95650-209">-ConnectionUri</span></span>

<span data-ttu-id="95650-210">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-210">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="95650-211">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="95650-211">The URI must be fully qualified.</span></span> <span data-ttu-id="95650-212">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="95650-212">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="95650-213">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="95650-213">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="95650-214">Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="95650-214">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="95650-215">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95650-215">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="95650-216">Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс создается с использованием стандартных портов: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95650-216">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="95650-217">Чтобы использовать порты по умолчанию для удаленного взаимодействия Windows PowerShell, укажите порт 5985 для протокола HTTP и 5986 для протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95650-217">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="95650-218">Если конечный компьютер перенаправляет соединение на другой URI, Windows PowerShell предотвращает перенаправление, если в команде не указать параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="95650-218">If the destination computer redirects the connection to a different URI, Windows PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="95650-219">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="95650-219">-ContainerId</span></span>

<span data-ttu-id="95650-220">Указывает идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="95650-220">Specifies the ID of a container.</span></span>

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

### <span data-ttu-id="95650-221">-Credential</span><span class="sxs-lookup"><span data-stu-id="95650-221">-Credential</span></span>

<span data-ttu-id="95650-222">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="95650-222">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="95650-223">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="95650-223">The default is the current user.</span></span>

<span data-ttu-id="95650-224">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="95650-224">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="95650-225">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="95650-225">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="95650-226">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="95650-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="95650-227">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="95650-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="95650-228">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="95650-228">-EnableNetworkAccess</span></span>

<span data-ttu-id="95650-229">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="95650-229">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="95650-230">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="95650-230">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="95650-231">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="95650-231">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="95650-232">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-232">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="95650-233">Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение.</span><span class="sxs-lookup"><span data-stu-id="95650-233">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="95650-234">(точка), localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="95650-234">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="95650-235">По умолчанию сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="95650-235">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="95650-236">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="95650-236">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="95650-237">Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="95650-237">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="95650-238">Удаленный доступ в петлевом сеансе также можно разрешить с помощью значения **CredSSP** параметра **Authentication** , который делегирует учетные данные сеанса на другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="95650-238">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="95650-239">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="95650-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="95650-240">-Id</span><span class="sxs-lookup"><span data-stu-id="95650-240">-Id</span></span>

<span data-ttu-id="95650-241">Указывает идентификатор существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-241">Specifies the ID of an existing session.</span></span> <span data-ttu-id="95650-242">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-242">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="95650-243">Чтобы найти идентификатор сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="95650-243">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="95650-244">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="95650-244">-InstanceId</span></span>

<span data-ttu-id="95650-245">Указывает идентификатор экземпляра существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-245">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="95650-246">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-246">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="95650-247">Значение идентификатора экземпляра представляет собой GUID.</span><span class="sxs-lookup"><span data-stu-id="95650-247">The instance ID is a GUID.</span></span> <span data-ttu-id="95650-248">Чтобы найти идентификатор экземпляра сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="95650-248">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="95650-249">Можно также использовать параметры **Session** , **Name** или **ID** , чтобы указать существующий сеанс.</span><span class="sxs-lookup"><span data-stu-id="95650-249">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="95650-250">Можно также использовать параметр **ComputerName** для запуска временного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-250">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

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

### <span data-ttu-id="95650-251">-Name</span><span class="sxs-lookup"><span data-stu-id="95650-251">-Name</span></span>

<span data-ttu-id="95650-252">Указывает понятное имя существующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-252">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="95650-253">`Enter-PSSession` использует указанный сеанс для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-253">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="95650-254">Если указанное имя соответствует сразу нескольким сеансам, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="95650-254">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="95650-255">Можно также использовать параметры **Session** , **InstanceId** или **ID** , чтобы указать существующий сеанс.</span><span class="sxs-lookup"><span data-stu-id="95650-255">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="95650-256">Можно также использовать параметр **ComputerName** для запуска временного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-256">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="95650-257">Чтобы установить понятное имя для сеанса, используйте параметр **Name** `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="95650-257">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="95650-258">-Port</span><span class="sxs-lookup"><span data-stu-id="95650-258">-Port</span></span>

<span data-ttu-id="95650-259">Указывает сетевой порт на удаленном компьютере, используемый для этой команды.</span><span class="sxs-lookup"><span data-stu-id="95650-259">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="95650-260">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="95650-260">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="95650-261">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95650-261">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="95650-262">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="95650-262">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="95650-263">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="95650-263">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="95650-264">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="95650-264">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="95650-265">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="95650-265">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="95650-266">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="95650-266">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95650-267">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="95650-267">-RunAsAdministrator</span></span>

<span data-ttu-id="95650-268">Указывает, что **сеанс PSSession** запускается от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="95650-268">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="95650-269">-Session</span><span class="sxs-lookup"><span data-stu-id="95650-269">-Session</span></span>

<span data-ttu-id="95650-270">Указывает сеанс Windows PowerShell ( **PSSession** ), используемый для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-270">Specifies a Windows PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="95650-271">Этот параметр принимает объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-271">This parameter takes a session object.</span></span> <span data-ttu-id="95650-272">Для указания **PSSession** можно также использовать параметры **Name** , **InstanceId** или **ID** .</span><span class="sxs-lookup"><span data-stu-id="95650-272">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession** .</span></span>

<span data-ttu-id="95650-273">Введите переменную, содержащую объект сеанса, или команду, которая создает или получает объект сеанса, например `New-PSSession` `Get-PSSession` команду или.</span><span class="sxs-lookup"><span data-stu-id="95650-273">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="95650-274">Можно также передать объект сеанса в `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="95650-274">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="95650-275">С помощью этого параметра можно отправить только один **сеанс PSSession** .</span><span class="sxs-lookup"><span data-stu-id="95650-275">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="95650-276">Если ввести переменную, содержащую более одного **сеанса PSSession** , команда завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="95650-276">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="95650-277">При использовании `Exit-PSSession` или ключевого слова **Exit** интерактивный сеанс завершается, но созданный **сеанс PSSession** остается открытым и доступным для использования.</span><span class="sxs-lookup"><span data-stu-id="95650-277">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

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

### <span data-ttu-id="95650-278">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="95650-278">-SessionOption</span></span>

<span data-ttu-id="95650-279">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-279">Sets advanced options for the session.</span></span> <span data-ttu-id="95650-280">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-280">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="95650-281">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="95650-281">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="95650-282">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-282">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="95650-283">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-283">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="95650-284">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-284">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="95650-285">Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="95650-285">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="95650-286">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="95650-286">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="95650-287">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="95650-287">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="95650-288">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="95650-288">-UseSSL</span></span>

<span data-ttu-id="95650-289">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="95650-289">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="95650-290">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="95650-290">By default, SSL is not used.</span></span>

<span data-ttu-id="95650-291">Протокол WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="95650-291">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="95650-292">Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="95650-292">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="95650-293">Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="95650-293">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="95650-294">— VMId</span><span class="sxs-lookup"><span data-stu-id="95650-294">-VMId</span></span>

<span data-ttu-id="95650-295">Указывает идентификатор виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="95650-295">Specifies the ID of a virtual machine.</span></span>

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

### <span data-ttu-id="95650-296">-VMName</span><span class="sxs-lookup"><span data-stu-id="95650-296">-VMName</span></span>

<span data-ttu-id="95650-297">Указывает имя виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="95650-297">Specifies the name of a virtual machine.</span></span>

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

### <span data-ttu-id="95650-298">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="95650-298">CommonParameters</span></span>

<span data-ttu-id="95650-299">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95650-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95650-300">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="95650-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95650-301">Входные данные</span><span class="sxs-lookup"><span data-stu-id="95650-301">INPUTS</span></span>

### <span data-ttu-id="95650-302">System. String, System. Management. Automation. пространства выполнения PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-302">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="95650-303">В этот командлет можно передать по конвейеру имя компьютера в виде строки или объекта сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-303">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="95650-304">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="95650-304">OUTPUTS</span></span>

### <span data-ttu-id="95650-305">Нет</span><span class="sxs-lookup"><span data-stu-id="95650-305">None</span></span>

<span data-ttu-id="95650-306">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="95650-306">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="95650-307">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="95650-307">NOTES</span></span>

<span data-ttu-id="95650-308">Чтобы подключиться к удаленному компьютеру, необходимо быть членом группы администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-308">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="95650-309">Чтобы запустить интерактивный сеанс на локальном компьютере, необходимо запустить PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="95650-309">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="95650-310">При использовании `Enter-PSSession` для интерактивного сеанса используется профиль пользователя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95650-310">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="95650-311">Команды в профиле удаленного пользователя, включая команды для добавления модулей PowerShell и изменения командной строки, выполняются перед отображением удаленного запроса.</span><span class="sxs-lookup"><span data-stu-id="95650-311">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="95650-312">`Enter-PSSession` использует параметр языка и региональных параметров пользовательского интерфейса на локальном компьютере для интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="95650-312">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="95650-313">Чтобы найти язык и региональные параметры локального пользовательского интерфейса, используйте `$UICulture` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="95650-313">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="95650-314">`Enter-PSSession` требуются `Get-Command` `Out-Default` командлеты, и `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="95650-314">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="95650-315">Если эти командлеты не включены в конфигурацию сеанса на удаленном компьютере, команды не будут `Enter-PSSession` работать.</span><span class="sxs-lookup"><span data-stu-id="95650-315">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="95650-316">В отличие от `Invoke-Command` , который анализирует и интерпретирует команды перед их отправкой на удаленный компьютер, `Enter-PSSession` отправляет команды непосредственно на удаленный компьютер без интерпретации.</span><span class="sxs-lookup"><span data-stu-id="95650-316">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="95650-317">Если сеанс, который вы хотите ввести, занят обработкой команды, может возникнуть задержка, прежде чем PowerShell ответит на `Enter-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="95650-317">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="95650-318">Вы подключены сразу после того, как сеанс будет доступен.</span><span class="sxs-lookup"><span data-stu-id="95650-318">You are connected as soon as the session is available.</span></span> <span data-ttu-id="95650-319">Чтобы отменить `Enter-PSSession` команду, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="95650-319">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

## <span data-ttu-id="95650-320">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="95650-320">RELATED LINKS</span></span>

[<span data-ttu-id="95650-321">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="95650-321">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="95650-322">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-322">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="95650-323">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="95650-323">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="95650-324">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-324">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="95650-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-325">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="95650-326">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-326">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="95650-327">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-327">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="95650-328">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="95650-328">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="95650-329">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="95650-329">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="95650-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="95650-330">about_Remote</span></span>](About/about_Remote.md)
