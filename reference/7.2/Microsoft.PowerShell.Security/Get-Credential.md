---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 5630c4d09a2806eb117d005466d4925c1740d3a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604558"
---
# <span data-ttu-id="aa16e-102">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="aa16e-102">Get-Credential</span></span>

## <span data-ttu-id="aa16e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aa16e-103">SYNOPSIS</span></span>
<span data-ttu-id="aa16e-104">Возвращает объект учетных данных на основе имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="aa16e-104">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="aa16e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa16e-105">SYNTAX</span></span>

### <span data-ttu-id="aa16e-106">CredentialSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="aa16e-106">CredentialSet (Default)</span></span>

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="aa16e-107">MessageSet</span><span class="sxs-lookup"><span data-stu-id="aa16e-107">MessageSet</span></span>

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## <span data-ttu-id="aa16e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa16e-108">DESCRIPTION</span></span>

<span data-ttu-id="aa16e-109">`Get-Credential`Командлет создает объект учетных данных для указанного имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="aa16e-109">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="aa16e-110">Объект учетных данных можно использовать в операциях безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa16e-110">You can use the credential object in security operations.</span></span>

<span data-ttu-id="aa16e-111">`Get-Credential`Командлет запрашивает у пользователя пароль или имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-111">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="aa16e-112">С помощью параметра **Message** можно указать настраиваемое сообщение в командной строке командной строки.</span><span class="sxs-lookup"><span data-stu-id="aa16e-112">You can use the **Message** parameter to specify a customized message in the command line prompt.</span></span>

## <span data-ttu-id="aa16e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa16e-113">EXAMPLES</span></span>

### <span data-ttu-id="aa16e-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="aa16e-114">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="aa16e-115">Эта команда возвращает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="aa16e-115">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="aa16e-116">При вводе команды вам будет предложено ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-116">When you enter the command, you are prompted for a user name and password.</span></span> <span data-ttu-id="aa16e-117">При вводе запрошенной информации командлет создает объект **PSCredential** , представляющий учетные данные пользователя, и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="aa16e-117">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="aa16e-118">Вы можете использовать этот объект в качестве входных данных в командлетах, запрашивающих проверку подлинности пользователя, например командлеты с параметром **Credential**.</span><span class="sxs-lookup"><span data-stu-id="aa16e-118">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="aa16e-119">Однако некоторые поставщики, установленные с помощью PowerShell, не поддерживают параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="aa16e-119">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="aa16e-120">Пример 2</span><span class="sxs-lookup"><span data-stu-id="aa16e-120">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="aa16e-121">Эти команды используют объект учетных данных, `Get-Credential` возвращаемый командлетом для проверки подлинности пользователя на удаленном компьютере, чтобы он мог использовать инструментарий управления Windows (WMI) (WMI) для управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="aa16e-121">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="aa16e-122">Первая команда получает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="aa16e-122">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="aa16e-123">Вторая команда использует объект Credential в `Get-CimInstance` команде.</span><span class="sxs-lookup"><span data-stu-id="aa16e-123">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="aa16e-124">Эта команда получает сведения о дисках на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="aa16e-124">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="aa16e-125">Пример 3</span><span class="sxs-lookup"><span data-stu-id="aa16e-125">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="aa16e-126">Эта команда показывает, как включить `Get-Credential` команду в  `Get-CimInstance` команду.</span><span class="sxs-lookup"><span data-stu-id="aa16e-126">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="aa16e-127">Эта команда использует `Get-CimInstance` командлет для получения сведений о BIOS на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="aa16e-127">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="aa16e-128">Он использует параметр **Credential** для проверки подлинности пользователя, Domain01\User01 и `Get-Credential` команды в качестве значения параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="aa16e-128">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="aa16e-129">Пример 4</span><span class="sxs-lookup"><span data-stu-id="aa16e-129">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="aa16e-130">В этом примере создаются учетные данные, в которые входит имя пользователя без доменного имени.</span><span class="sxs-lookup"><span data-stu-id="aa16e-130">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="aa16e-131">Первая команда получает учетные данные с именем пользователя USER01 и сохраняет их в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="aa16e-131">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="aa16e-132">Вторая команда отображает значение свойства **Username** полученного объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="aa16e-132">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="aa16e-133">Пример 5</span><span class="sxs-lookup"><span data-stu-id="aa16e-133">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="aa16e-134">Эта команда использует метод **PromptForCredential**, чтобы запросить у пользователя его имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-134">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="aa16e-135">Команда сохраняет итоговые учетные данные в `$Credential` переменной.</span><span class="sxs-lookup"><span data-stu-id="aa16e-135">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="aa16e-136">Метод **PromptForCredential** является альтернативой использованию `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="aa16e-136">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="aa16e-137">При использовании **PromptForCredential** можно указать заголовок, сообщения и имя пользователя, которые отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aa16e-137">When you use **PromptForCredential**, you can specify the caption, messages, and user name that appear in the prompt.</span></span>

<span data-ttu-id="aa16e-138">Дополнительные сведения см. в документации по [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) в пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="aa16e-138">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="aa16e-139">Пример 6</span><span class="sxs-lookup"><span data-stu-id="aa16e-139">Example 6</span></span>

<span data-ttu-id="aa16e-140">В этом примере показано, как создать объект учетных данных, идентичный объекту, который `Get-Credential` возвращает данные без запроса пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa16e-140">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="aa16e-141">Для этого метода требуется незашифрованный пароль, который может нарушать стандарты безопасности в некоторых организациях.</span><span class="sxs-lookup"><span data-stu-id="aa16e-141">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="aa16e-142">Первая команда сохраняет имя учетной записи пользователя в `$User` параметре.</span><span class="sxs-lookup"><span data-stu-id="aa16e-142">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="aa16e-143">Значение должно иметь формат "домен\пользователь" или "имя компьютера\пользователь".</span><span class="sxs-lookup"><span data-stu-id="aa16e-143">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="aa16e-144">Вторая команда использует `ConvertTo-SecureString` командлет для создания защищенной строки из текстового пароля.</span><span class="sxs-lookup"><span data-stu-id="aa16e-144">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="aa16e-145">Параметр **AsPlainText** команды указывает, что строка является обычным текстом, а параметр **Force** подтверждает, что вы понимаете риски использования обычного текста.</span><span class="sxs-lookup"><span data-stu-id="aa16e-145">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="aa16e-146">Третья команда использует `New-Object` командлет для создания объекта **PSCredential** на основе значений в `$User` `$PWord` переменных и.</span><span class="sxs-lookup"><span data-stu-id="aa16e-146">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="aa16e-147">Пример 7</span><span class="sxs-lookup"><span data-stu-id="aa16e-147">Example 7</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="aa16e-148">Эта команда использует параметры **Message** и **username** `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="aa16e-148">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="aa16e-149">Этот формат команды предназначен для общих скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="aa16e-149">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="aa16e-150">В этом случае в сообщении пользователю указывается причина необходимости учетных данных и подтверждается санкционированность запроса.</span><span class="sxs-lookup"><span data-stu-id="aa16e-150">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="aa16e-151">Пример 8</span><span class="sxs-lookup"><span data-stu-id="aa16e-151">Example 8</span></span>

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

<span data-ttu-id="aa16e-152">Эта команда получает учетные данные с удаленного компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="aa16e-152">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="aa16e-153">Команда использует `Invoke-Command` командлет для выполнения `Get-Credential` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="aa16e-153">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="aa16e-154">В выходных данных отображается удаленное сообщение безопасности, которое `Get-Credential` включается в запрос проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="aa16e-154">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="aa16e-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa16e-155">PARAMETERS</span></span>

### <span data-ttu-id="aa16e-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="aa16e-156">-Credential</span></span>

<span data-ttu-id="aa16e-157">Указывает имя пользователя для учетных данных, например **User01** или **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="aa16e-157">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="aa16e-158">Имя параметра `-Credential` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="aa16e-158">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="aa16e-159">Когда вы отправляете команду и указываете имя пользователя, вам будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-159">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="aa16e-160">Если опустить этот параметр, будет предложено ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-160">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="aa16e-161">Начиная с PowerShell 3,0, если ввести имя пользователя без домена, `Get-Credential` перед именем не будет вставляться обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="aa16e-161">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="aa16e-162">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="aa16e-162">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="aa16e-163">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="aa16e-163">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa16e-164">-Message</span><span class="sxs-lookup"><span data-stu-id="aa16e-164">-Message</span></span>

<span data-ttu-id="aa16e-165">Указывает сообщение, которое отображается в запросе проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="aa16e-165">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="aa16e-166">Этот параметр предназначен для использования в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="aa16e-166">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="aa16e-167">В сообщении можно объяснить пользователю причину запроса учетных данных и способ их использования.</span><span class="sxs-lookup"><span data-stu-id="aa16e-167">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="aa16e-168">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="aa16e-168">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa16e-169">-Title</span><span class="sxs-lookup"><span data-stu-id="aa16e-169">-Title</span></span>

<span data-ttu-id="aa16e-170">Задает текст строки заголовка для запроса проверки подлинности в консоли.</span><span class="sxs-lookup"><span data-stu-id="aa16e-170">Sets the text of the title line for the authentication prompt in the console.</span></span>

<span data-ttu-id="aa16e-171">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="aa16e-171">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa16e-172">-UserName</span><span class="sxs-lookup"><span data-stu-id="aa16e-172">-UserName</span></span>

<span data-ttu-id="aa16e-173">Указывает имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa16e-173">Specifies a user name.</span></span> <span data-ttu-id="aa16e-174">В запросе проверки подлинности необходимо указать пароль для имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa16e-174">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="aa16e-175">По умолчанию имя пользователя является пустым, а в запросе проверки подлинности требуется указать как имя пользователя, так и пароль.</span><span class="sxs-lookup"><span data-stu-id="aa16e-175">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="aa16e-176">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="aa16e-176">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="aa16e-177">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aa16e-177">CommonParameters</span></span>

<span data-ttu-id="aa16e-178">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa16e-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa16e-179">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa16e-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa16e-180">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aa16e-180">INPUTS</span></span>

### <span data-ttu-id="aa16e-181">None</span><span class="sxs-lookup"><span data-stu-id="aa16e-181">None</span></span>

<span data-ttu-id="aa16e-182">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="aa16e-182">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="aa16e-183">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aa16e-183">OUTPUTS</span></span>

### <span data-ttu-id="aa16e-184">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="aa16e-184">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="aa16e-185">`Get-Credential` Возвращает объект учетных данных.</span><span class="sxs-lookup"><span data-stu-id="aa16e-185">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="aa16e-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aa16e-186">NOTES</span></span>

<span data-ttu-id="aa16e-187">Можно использовать объект **PSCredential** , который `Get-Credential` создает в командлетах, запрашивающих проверку подлинности пользователя, например, с помощью параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="aa16e-187">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="aa16e-188">Параметр **Credential** не поддерживается всеми поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa16e-188">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="aa16e-189">Начиная с PowerShell 3,0, он поддерживается для командлетов SELECT, таких как `Get-Content` `New-PSDrive` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="aa16e-189">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="aa16e-190">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aa16e-190">RELATED LINKS</span></span>

[<span data-ttu-id="aa16e-191">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="aa16e-191">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
