---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 2ff87c8d4b714be3b5be3bfe8f384b4c89c25272
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "93233282"
---
# <span data-ttu-id="ed934-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="ed934-103">Get-Credential</span></span>

## <span data-ttu-id="ed934-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ed934-104">SYNOPSIS</span></span>
<span data-ttu-id="ed934-105">Возвращает объект учетных данных на основе имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="ed934-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="ed934-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed934-106">SYNTAX</span></span>

### <span data-ttu-id="ed934-107">CredentialSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ed934-107">CredentialSet (Default)</span></span>

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="ed934-108">MessageSet</span><span class="sxs-lookup"><span data-stu-id="ed934-108">MessageSet</span></span>

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## <span data-ttu-id="ed934-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed934-109">DESCRIPTION</span></span>

<span data-ttu-id="ed934-110">`Get-Credential`Командлет создает объект учетных данных для указанного имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="ed934-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="ed934-111">Объект учетных данных можно использовать в операциях безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed934-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="ed934-112">`Get-Credential`Командлет запрашивает у пользователя пароль или имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-112">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="ed934-113">С помощью параметра **Message** можно указать настраиваемое сообщение в командной строке командной строки.</span><span class="sxs-lookup"><span data-stu-id="ed934-113">You can use the **Message** parameter to specify a customized message in the command line prompt.</span></span>

## <span data-ttu-id="ed934-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="ed934-114">EXAMPLES</span></span>

### <span data-ttu-id="ed934-115">Пример 1</span><span class="sxs-lookup"><span data-stu-id="ed934-115">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="ed934-116">Эта команда возвращает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed934-116">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="ed934-117">При вводе команды вам будет предложено ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-117">When you enter the command, you are prompted for a user name and password.</span></span> <span data-ttu-id="ed934-118">При вводе запрошенной информации командлет создает объект **PSCredential** , представляющий учетные данные пользователя, и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed934-118">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="ed934-119">Вы можете использовать этот объект в качестве входных данных в командлетах, запрашивающих проверку подлинности пользователя, например командлеты с параметром **Credential**.</span><span class="sxs-lookup"><span data-stu-id="ed934-119">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="ed934-120">Однако некоторые поставщики, установленные с помощью PowerShell, не поддерживают параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="ed934-120">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="ed934-121">Пример 2</span><span class="sxs-lookup"><span data-stu-id="ed934-121">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="ed934-122">Эти команды используют объект учетных данных, `Get-Credential` возвращаемый командлетом для проверки подлинности пользователя на удаленном компьютере, чтобы он мог использовать инструментарий управления Windows (WMI) (WMI) для управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="ed934-122">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="ed934-123">Первая команда получает объект учетных данных и сохраняет его в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed934-123">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="ed934-124">Вторая команда использует объект Credential в `Get-CimInstance` команде.</span><span class="sxs-lookup"><span data-stu-id="ed934-124">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="ed934-125">Эта команда получает сведения о дисках на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ed934-125">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="ed934-126">Пример 3</span><span class="sxs-lookup"><span data-stu-id="ed934-126">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="ed934-127">Эта команда показывает, как включить `Get-Credential` команду в  `Get-CimInstance` команду.</span><span class="sxs-lookup"><span data-stu-id="ed934-127">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="ed934-128">Эта команда использует `Get-CimInstance` командлет для получения сведений о BIOS на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ed934-128">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="ed934-129">Он использует параметр **Credential** для проверки подлинности пользователя, Domain01\User01 и `Get-Credential` команды в качестве значения параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="ed934-129">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="ed934-130">Пример 4</span><span class="sxs-lookup"><span data-stu-id="ed934-130">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="ed934-131">В этом примере создаются учетные данные, в которые входит имя пользователя без доменного имени.</span><span class="sxs-lookup"><span data-stu-id="ed934-131">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="ed934-132">Первая команда получает учетные данные с именем пользователя USER01 и сохраняет их в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed934-132">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="ed934-133">Вторая команда отображает значение свойства **Username** полученного объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ed934-133">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="ed934-134">Пример 5</span><span class="sxs-lookup"><span data-stu-id="ed934-134">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="ed934-135">Эта команда использует метод **PromptForCredential** , чтобы запросить у пользователя его имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-135">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="ed934-136">Команда сохраняет итоговые учетные данные в `$Credential` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed934-136">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="ed934-137">Метод **PromptForCredential** является альтернативой использованию `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="ed934-137">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ed934-138">При использовании **PromptForCredential** можно указать заголовок, сообщения и имя пользователя, которые отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ed934-138">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the prompt.</span></span>

<span data-ttu-id="ed934-139">Дополнительные сведения см. в документации по [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) в пакете SDK.</span><span class="sxs-lookup"><span data-stu-id="ed934-139">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="ed934-140">Пример 6</span><span class="sxs-lookup"><span data-stu-id="ed934-140">Example 6</span></span>

<span data-ttu-id="ed934-141">В этом примере показано, как создать объект учетных данных, идентичный объекту, который `Get-Credential` возвращает данные без запроса пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed934-141">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="ed934-142">Для этого метода требуется незашифрованный пароль, который может нарушать стандарты безопасности в некоторых организациях.</span><span class="sxs-lookup"><span data-stu-id="ed934-142">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="ed934-143">Первая команда сохраняет имя учетной записи пользователя в `$User` параметре.</span><span class="sxs-lookup"><span data-stu-id="ed934-143">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="ed934-144">Значение должно иметь формат "домен\пользователь" или "имя компьютера\пользователь".</span><span class="sxs-lookup"><span data-stu-id="ed934-144">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="ed934-145">Вторая команда использует `ConvertTo-SecureString` командлет для создания защищенной строки из текстового пароля.</span><span class="sxs-lookup"><span data-stu-id="ed934-145">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="ed934-146">Параметр **AsPlainText** команды указывает, что строка является обычным текстом, а параметр **Force** подтверждает, что вы понимаете риски использования обычного текста.</span><span class="sxs-lookup"><span data-stu-id="ed934-146">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="ed934-147">Третья команда использует `New-Object` командлет для создания объекта **PSCredential** на основе значений в `$User` `$PWord` переменных и.</span><span class="sxs-lookup"><span data-stu-id="ed934-147">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="ed934-148">Пример 7</span><span class="sxs-lookup"><span data-stu-id="ed934-148">Example 7</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="ed934-149">Эта команда использует параметры **Message** и **username** `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="ed934-149">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ed934-150">Этот формат команды предназначен для общих скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="ed934-150">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="ed934-151">В этом случае в сообщении пользователю указывается причина необходимости учетных данных и подтверждается санкционированность запроса.</span><span class="sxs-lookup"><span data-stu-id="ed934-151">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="ed934-152">Пример 8</span><span class="sxs-lookup"><span data-stu-id="ed934-152">Example 8</span></span>

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

<span data-ttu-id="ed934-153">Эта команда получает учетные данные с удаленного компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="ed934-153">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="ed934-154">Команда использует `Invoke-Command` командлет для выполнения `Get-Credential` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed934-154">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="ed934-155">В выходных данных отображается удаленное сообщение безопасности, которое `Get-Credential` включается в запрос проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ed934-155">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="ed934-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed934-156">PARAMETERS</span></span>

### <span data-ttu-id="ed934-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="ed934-157">-Credential</span></span>

<span data-ttu-id="ed934-158">Указывает имя пользователя для учетных данных, например **User01** или **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="ed934-158">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="ed934-159">Имя параметра `-Credential` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ed934-159">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="ed934-160">Когда вы отправляете команду и указываете имя пользователя, вам будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-160">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="ed934-161">Если опустить этот параметр, будет предложено ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-161">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="ed934-162">Начиная с PowerShell 3,0, если ввести имя пользователя без домена, `Get-Credential` перед именем не будет вставляться обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="ed934-162">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="ed934-163">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="ed934-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ed934-164">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ed934-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="ed934-165">-Message</span><span class="sxs-lookup"><span data-stu-id="ed934-165">-Message</span></span>

<span data-ttu-id="ed934-166">Указывает сообщение, которое отображается в запросе проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ed934-166">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="ed934-167">Этот параметр предназначен для использования в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="ed934-167">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="ed934-168">В сообщении можно объяснить пользователю причину запроса учетных данных и способ их использования.</span><span class="sxs-lookup"><span data-stu-id="ed934-168">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="ed934-169">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed934-169">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed934-170">-Title</span><span class="sxs-lookup"><span data-stu-id="ed934-170">-Title</span></span>

<span data-ttu-id="ed934-171">Задает текст строки заголовка для запроса проверки подлинности в консоли.</span><span class="sxs-lookup"><span data-stu-id="ed934-171">Sets the text of the title line for the authentication prompt in the console.</span></span>

<span data-ttu-id="ed934-172">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="ed934-172">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="ed934-173">-UserName</span><span class="sxs-lookup"><span data-stu-id="ed934-173">-UserName</span></span>

<span data-ttu-id="ed934-174">Указывает имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed934-174">Specifies a user name.</span></span> <span data-ttu-id="ed934-175">В запросе проверки подлинности необходимо указать пароль для имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed934-175">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="ed934-176">По умолчанию имя пользователя является пустым, а в запросе проверки подлинности требуется указать как имя пользователя, так и пароль.</span><span class="sxs-lookup"><span data-stu-id="ed934-176">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="ed934-177">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed934-177">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ed934-178">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ed934-178">CommonParameters</span></span>

<span data-ttu-id="ed934-179">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed934-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed934-180">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed934-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed934-181">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ed934-181">INPUTS</span></span>

### <span data-ttu-id="ed934-182">Нет</span><span class="sxs-lookup"><span data-stu-id="ed934-182">None</span></span>

<span data-ttu-id="ed934-183">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="ed934-183">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ed934-184">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ed934-184">OUTPUTS</span></span>

### <span data-ttu-id="ed934-185">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="ed934-185">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="ed934-186">`Get-Credential` Возвращает объект учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ed934-186">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="ed934-187">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ed934-187">NOTES</span></span>

<span data-ttu-id="ed934-188">Можно использовать объект **PSCredential** , который `Get-Credential` создает в командлетах, запрашивающих проверку подлинности пользователя, например, с помощью параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="ed934-188">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="ed934-189">Параметр **Credential** не поддерживается всеми поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed934-189">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="ed934-190">Начиная с PowerShell 3,0, он поддерживается для командлетов SELECT, таких как `Get-Content` `New-PSDrive` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="ed934-190">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="ed934-191">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ed934-191">RELATED LINKS</span></span>

[<span data-ttu-id="ed934-192">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="ed934-192">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
