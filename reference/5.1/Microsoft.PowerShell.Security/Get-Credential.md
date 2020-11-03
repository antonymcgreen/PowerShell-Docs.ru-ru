---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "93233266"
---
# <span data-ttu-id="1d5c0-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="1d5c0-103">Get-Credential</span></span>

## <span data-ttu-id="1d5c0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1d5c0-104">SYNOPSIS</span></span>
<span data-ttu-id="1d5c0-105">Возвращает объект учетных данных на основе имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="1d5c0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d5c0-106">SYNTAX</span></span>

### <span data-ttu-id="1d5c0-107">CredentialSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1d5c0-107">CredentialSet (Default)</span></span>

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### <span data-ttu-id="1d5c0-108">MessageSet</span><span class="sxs-lookup"><span data-stu-id="1d5c0-108">MessageSet</span></span>

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="1d5c0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d5c0-109">DESCRIPTION</span></span>

<span data-ttu-id="1d5c0-110">`Get-Credential`Командлет создает объект учетных данных для указанного имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="1d5c0-111">Объект учетных данных можно использовать в операциях безопасности.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="1d5c0-112">Начиная с PowerShell 3,0 можно использовать параметр **Message** , чтобы указать настраиваемое сообщение в диалоговом окне, предлагающее пользователю ввести имя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-112">Beginning in PowerShell 3.0, you can use the **Message** parameter to specify a customized message on the dialog box that prompts the user for their name and password.</span></span>

<span data-ttu-id="1d5c0-113">`Get-Credential`Командлет запрашивает у пользователя пароль или имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-113">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="1d5c0-114">По умолчанию появляется диалоговое окно проверки подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-114">By default, an authentication dialog box appears to prompt the user.</span></span> <span data-ttu-id="1d5c0-115">Однако в некоторых ведущих программах, таких как консоль PowerShell, можно запросить пользователя в командной строке, изменив параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-115">However, in some host programs, such as the PowerShell console, you can prompt the user at the command line by changing a registry entry.</span></span> <span data-ttu-id="1d5c0-116">Дополнительные сведения об этой записи реестра см. в примечаниях и примерах.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-116">For more information about this registry entry, see the notes and examples.</span></span>

## <span data-ttu-id="1d5c0-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d5c0-117">EXAMPLES</span></span>

### <span data-ttu-id="1d5c0-118">Пример 1</span><span class="sxs-lookup"><span data-stu-id="1d5c0-118">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="1d5c0-119">Эта команда возвращает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-119">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="1d5c0-120">При вводе команды появляется диалоговое окно, запрашивающее имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-120">When you enter the command, a dialog box appears requesting a user name and password.</span></span> <span data-ttu-id="1d5c0-121">При вводе запрошенной информации командлет создает объект **PSCredential** , представляющий учетные данные пользователя, и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-121">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="1d5c0-122">Вы можете использовать этот объект в качестве входных данных в командлетах, запрашивающих проверку подлинности пользователя, например командлеты с параметром **Credential**.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-122">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="1d5c0-123">Однако некоторые поставщики, установленные с помощью PowerShell, не поддерживают параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="1d5c0-123">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="1d5c0-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="1d5c0-124">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="1d5c0-125">Эти команды используют объект учетных данных, `Get-Credential` возвращаемый командлетом для проверки подлинности пользователя на удаленном компьютере, чтобы он мог использовать инструментарий управления Windows (WMI) (WMI) для управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-125">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="1d5c0-126">Первая команда получает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-126">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="1d5c0-127">Вторая команда использует объект Credential в `Get-CimInstance` команде.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-127">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="1d5c0-128">Эта команда получает сведения о дисках на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-128">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="1d5c0-129">Пример 3</span><span class="sxs-lookup"><span data-stu-id="1d5c0-129">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="1d5c0-130">Эта команда показывает, как включить `Get-Credential` команду в  `Get-CimInstance` команду.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-130">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="1d5c0-131">Эта команда использует `Get-CimInstance` командлет для получения сведений о BIOS на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-131">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="1d5c0-132">Он использует параметр **Credential** для проверки подлинности пользователя, Domain01\User01 и `Get-Credential` команды в качестве значения параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="1d5c0-132">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="1d5c0-133">Пример 4</span><span class="sxs-lookup"><span data-stu-id="1d5c0-133">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="1d5c0-134">В этом примере создаются учетные данные, в которые входит имя пользователя без доменного имени.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-134">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="1d5c0-135">Первая команда получает учетные данные с именем пользователя USER01 и сохраняет их в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-135">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="1d5c0-136">Вторая команда отображает значение свойства **Username** полученного объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-136">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="1d5c0-137">Пример 5</span><span class="sxs-lookup"><span data-stu-id="1d5c0-137">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="1d5c0-138">Эта команда использует метод **PromptForCredential** , чтобы запросить у пользователя его имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-138">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="1d5c0-139">Команда сохраняет итоговые учетные данные в `$Credential` переменной.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-139">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="1d5c0-140">Метод **PromptForCredential** является альтернативой использованию `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-140">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1d5c0-141">При использовании **PromptForCredential** можно указать заголовок, сообщения и имя пользователя, которые отображаются в окне сообщений.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-141">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the message box.</span></span>

<span data-ttu-id="1d5c0-142">Дополнительные сведения см. в документации по [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) в пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-142">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="1d5c0-143">Пример 6</span><span class="sxs-lookup"><span data-stu-id="1d5c0-143">Example 6</span></span>

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

<span data-ttu-id="1d5c0-144">В этом примере показано, как изменить реестр так, чтобы пользователь получал запрос в командной строке вместо диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-144">This example shows how to modify the registry so that the user is prompted at the command line, instead of by using a dialog box.</span></span>

<span data-ttu-id="1d5c0-145">Команда создает запись реестра **ConsolePrompting** и указывает для нее значение True.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-145">The command creates the **ConsolePrompting** registry entry and sets its value to True.</span></span> <span data-ttu-id="1d5c0-146">Чтобы выполнить эту команду, запустите PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="1d5c0-146">To run this command, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="1d5c0-147">Чтобы использовать диалоговое окно для запроса, установите для параметра ConsolePrompting значение false ($false) или используйте `Remove-ItemProperty` командлет, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-147">To use a dialog box for prompting, set the value of the ConsolePrompting to false ($false) or use the `Remove-ItemProperty` cmdlet to delete it.</span></span>

<span data-ttu-id="1d5c0-148">Запись реестра ConsolePrompting работает в некоторых ведущих программах, например в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-148">The ConsolePrompting registry entry works in some host programs, such as the PowerShell console.</span></span> <span data-ttu-id="1d5c0-149">Она может работать не во всех основных программах.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-149">It might not work in all host programs.</span></span>

### <span data-ttu-id="1d5c0-150">Пример 7</span><span class="sxs-lookup"><span data-stu-id="1d5c0-150">Example 7</span></span>

<span data-ttu-id="1d5c0-151">В этом примере показано, как создать объект учетных данных, идентичный объекту, который `Get-Credential` возвращает данные без запроса пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-151">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="1d5c0-152">Для этого метода требуется незашифрованный пароль, который может нарушать стандарты безопасности в некоторых организациях.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-152">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="1d5c0-153">Первая команда сохраняет имя учетной записи пользователя в `$User` параметре.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-153">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="1d5c0-154">Значение должно иметь формат "домен\пользователь" или "имя компьютера\пользователь".</span><span class="sxs-lookup"><span data-stu-id="1d5c0-154">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="1d5c0-155">Вторая команда использует `ConvertTo-SecureString` командлет для создания защищенной строки из текстового пароля.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-155">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="1d5c0-156">Параметр **AsPlainText** команды указывает, что строка является обычным текстом, а параметр **Force** подтверждает, что вы понимаете риски использования обычного текста.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-156">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="1d5c0-157">Третья команда использует `New-Object` командлет для создания объекта **PSCredential** на основе значений в `$User` `$PWord` переменных и.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-157">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="1d5c0-158">Пример 8</span><span class="sxs-lookup"><span data-stu-id="1d5c0-158">Example 8</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="1d5c0-159">Эта команда использует параметры **Message** и **username** `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-159">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1d5c0-160">Этот формат команды предназначен для общих скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-160">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="1d5c0-161">В этом случае в сообщении пользователю указывается причина необходимости учетных данных и подтверждается санкционированность запроса.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-161">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="1d5c0-162">Пример 9</span><span class="sxs-lookup"><span data-stu-id="1d5c0-162">Example 9</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

<span data-ttu-id="1d5c0-163">Эта команда получает учетные данные с удаленного компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-163">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="1d5c0-164">Команда использует `Invoke-Command` командлет для выполнения `Get-Credential` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-164">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="1d5c0-165">В выходных данных отображается удаленное сообщение безопасности, которое `Get-Credential` включается в запрос проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-165">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="1d5c0-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d5c0-166">PARAMETERS</span></span>

### <span data-ttu-id="1d5c0-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="1d5c0-167">-Credential</span></span>

<span data-ttu-id="1d5c0-168">Указывает имя пользователя для учетных данных, например **User01** или **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-168">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="1d5c0-169">Имя параметра `-Credential` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-169">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="1d5c0-170">Когда вы отправляете команду и указываете имя пользователя, вам будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-170">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="1d5c0-171">Если опустить этот параметр, будет предложено ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-171">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="1d5c0-172">Начиная с PowerShell 3,0, если ввести имя пользователя без домена, `Get-Credential` перед именем не будет вставляться обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-172">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="1d5c0-173">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="1d5c0-173">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1d5c0-174">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1d5c0-174">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5c0-175">-Message</span><span class="sxs-lookup"><span data-stu-id="1d5c0-175">-Message</span></span>

<span data-ttu-id="1d5c0-176">Указывает сообщение, которое отображается в запросе проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-176">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="1d5c0-177">Этот параметр предназначен для использования в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-177">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="1d5c0-178">В сообщении можно объяснить пользователю причину запроса учетных данных и способ их использования.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-178">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="1d5c0-179">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-179">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5c0-180">-UserName</span><span class="sxs-lookup"><span data-stu-id="1d5c0-180">-UserName</span></span>

<span data-ttu-id="1d5c0-181">Указывает имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-181">Specifies a user name.</span></span> <span data-ttu-id="1d5c0-182">В запросе проверки подлинности необходимо указать пароль для имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-182">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="1d5c0-183">По умолчанию имя пользователя является пустым, а в запросе проверки подлинности требуется указать как имя пользователя, так и пароль.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-183">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="1d5c0-184">При появлении в диалоговом окне запроса проверки подлинности пользователь может изменить указанное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-184">When the authentication prompt appears in a dialog box, the user can edit the specified user name.</span></span>
<span data-ttu-id="1d5c0-185">Однако пользователь не может изменить имя пользователя, если запрос отображается в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-185">However, the user cannot change the user name when the prompt appears at the command line.</span></span> <span data-ttu-id="1d5c0-186">При использовании этого параметра в общей функции или скрипте рассмотрите все возможные варианты представления.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-186">When using this parameter in a shared function or script, consider all possible presentations.</span></span>

<span data-ttu-id="1d5c0-187">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-187">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d5c0-188">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1d5c0-188">CommonParameters</span></span>

<span data-ttu-id="1d5c0-189">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d5c0-190">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d5c0-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d5c0-191">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1d5c0-191">INPUTS</span></span>

### <span data-ttu-id="1d5c0-192">Нет</span><span class="sxs-lookup"><span data-stu-id="1d5c0-192">None</span></span>

<span data-ttu-id="1d5c0-193">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-193">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1d5c0-194">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d5c0-194">OUTPUTS</span></span>

### <span data-ttu-id="1d5c0-195">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="1d5c0-195">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="1d5c0-196">`Get-Credential` Возвращает объект учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-196">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="1d5c0-197">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1d5c0-197">NOTES</span></span>

<span data-ttu-id="1d5c0-198">Можно использовать объект **PSCredential** , который `Get-Credential` создает в командлетах, запрашивающих проверку подлинности пользователя, например, с помощью параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="1d5c0-198">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="1d5c0-199">По умолчанию запрос проверки подлинности появляется в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-199">By default, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="1d5c0-200">Чтобы отобразить запрос проверки подлинности в командной строке, добавьте запись реестра **ConsolePrompting** ( `HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting` ) и присвойте ей значение **true**.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-200">To display the authentication prompt at the command line, add the **ConsolePrompting** registry entry (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) and set its value to **True**.</span></span>
<span data-ttu-id="1d5c0-201">Если запись реестра **ConsolePrompting** не существует или имеет значение False, запрос проверки подлинности появляется в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-201">If the **ConsolePrompting** registry entry does not exist or if its value is False, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="1d5c0-202">Инструкции см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-202">For instructions, see the examples.</span></span>

<span data-ttu-id="1d5c0-203">Запись реестра **ConsolePrompting** работает в консоли PowerShell, но не работает во всех ведущих программах.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-203">The **ConsolePrompting** registry entry works in the PowerShell console, but it does not work in all host programs.</span></span>

<span data-ttu-id="1d5c0-204">Например, он не действует в интегрированной среде сценариев (ISE) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-204">For example, it has no effect in the PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="1d5c0-205">Дополнительные сведения о влиянии записи реестра **ConsolePrompting** см. в разделах справки для основной программы.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-205">For information about the effect of the **ConsolePrompting** registry entry, see the help topics for the host program.</span></span>

<span data-ttu-id="1d5c0-206">Параметр **Credential** не поддерживается всеми поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-206">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="1d5c0-207">Начиная с PowerShell 3,0, он поддерживается для командлетов SELECT, таких как `Get-Content` `New-PSDrive` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="1d5c0-207">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="1d5c0-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d5c0-208">RELATED LINKS</span></span>

[<span data-ttu-id="1d5c0-209">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="1d5c0-209">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
