---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: f3545065d4879830a5051ef687f210c7fbd1251e
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860667"
---
# <span data-ttu-id="82280-102">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="82280-102">Invoke-WebRequest</span></span>

## <span data-ttu-id="82280-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="82280-103">SYNOPSIS</span></span>
<span data-ttu-id="82280-104">Получает содержимое с веб-страницы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="82280-104">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="82280-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82280-105">SYNTAX</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="82280-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="82280-106">DESCRIPTION</span></span>

<span data-ttu-id="82280-107">`Invoke-WebRequest`Командлет отправляет запросы HTTP, HTTPS, FTP и файлы на веб-страницу или веб-службу.</span><span class="sxs-lookup"><span data-stu-id="82280-107">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="82280-108">Он анализирует ответ и возвращает коллекции форм, ссылок, изображений и других значимых HTML-элементов.</span><span class="sxs-lookup"><span data-stu-id="82280-108">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="82280-109">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="82280-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="82280-110">По умолчанию код сценария на веб-странице может выполняться при синтаксическом анализе страницы для заполнения `ParsedHtml` Свойства.</span><span class="sxs-lookup"><span data-stu-id="82280-110">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span>
> <span data-ttu-id="82280-111">`-UseBasicParsing`Чтобы отключить это действие, используйте параметр.</span><span class="sxs-lookup"><span data-stu-id="82280-111">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="82280-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="82280-112">EXAMPLES</span></span>

### <span data-ttu-id="82280-113">Пример 1. Отправка веб-запроса</span><span class="sxs-lookup"><span data-stu-id="82280-113">Example 1: Send a web request</span></span>

<span data-ttu-id="82280-114">Эта команда использует `Invoke-WebRequest` командлет для отправки веб-запроса на сайт Bing.com.</span><span class="sxs-lookup"><span data-stu-id="82280-114">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$R = Invoke-WebRequest -URI https://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | Where-Object {
    $_.name -like "* Value" -and $_.tagName -eq "INPUT"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="82280-115">Первая команда выдает запрос и сохраняет ответ в `$R` переменной.</span><span class="sxs-lookup"><span data-stu-id="82280-115">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="82280-116">Вторая команда фильтрует объекты в свойстве **аллелементс** , где свойство **Name** имеет значение "\* value", а **TagName** — "input".</span><span class="sxs-lookup"><span data-stu-id="82280-116">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="82280-117">Отфильтрованные результаты передаются в, `Select-Object` чтобы выбрать свойства " **имя** " и " **значение** ".</span><span class="sxs-lookup"><span data-stu-id="82280-117">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="82280-118">Пример 2. Использование веб-службы с отслеживанием состояния</span><span class="sxs-lookup"><span data-stu-id="82280-118">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="82280-119">В этом примере показано, как использовать `Invoke-WebRequest` командлет с веб-службой с отслеживанием состояния, например Facebook.</span><span class="sxs-lookup"><span data-stu-id="82280-119">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

```powershell
$R = Invoke-WebRequest https://www.facebook.com/login.php -SessionVariable fb
# This command stores the first form in the Forms property of the $R variable in the $Form variable.
$Form = $R.Forms[0]
# This command shows the fields available in the Form.
$Form.fields
```

```Output
Key                     Value
---                     -----
...
email
pass
...
```

```powershell
# These commands populate the username and password of the respective Form fields.
$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
# This command creates the Uri that will be used to log in to facebook.
# The value of the Uri parameter is the value of the Action property of the form.
$Uri = "https://www.facebook.com" + $Form.Action
# Now the Invoke-WebRequest cmdlet is used to sign into the Facebook web service.
# The WebRequestSession object in the $FB variable is passed as the value of the WebSession parameter.
# The value of the Body parameter is the hash table in the Fields property of the form.
# The value of the *Method* parameter is POST. The command saves the output in the $R variable.
$R = Invoke-WebRequest -Uri $Uri -WebSession $FB -Method POST -Body $Form.Fields
$R.StatusDescription
```

<span data-ttu-id="82280-120">Первая команда использует `Invoke-WebRequest` командлет для отправки запроса на вход.</span><span class="sxs-lookup"><span data-stu-id="82280-120">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="82280-121">Команда задает значение "FB" в качестве значения параметра **сессионвариабле** и сохраняет результат в `$R` переменной.</span><span class="sxs-lookup"><span data-stu-id="82280-121">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="82280-122">После выполнения команды `$R` переменная содержит **хтмлвебреспонсеобжект** , а `$FB` переменная содержит объект **вебрекуестсессион** .</span><span class="sxs-lookup"><span data-stu-id="82280-122">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="82280-123">После того как `Invoke-WebRequest` командлет войдет в Facebook, свойство **StatusDescription** объекта веб-ответа в `$R` переменной указывает, что пользователь успешно выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="82280-123">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="82280-124">Пример 3. получение ссылок с веб-страницы</span><span class="sxs-lookup"><span data-stu-id="82280-124">Example 3: Get links from a web page</span></span>

<span data-ttu-id="82280-125">Эта команда возвращает ссылки с веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="82280-125">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="82280-126">`Invoke-WebRequest`Командлет возвращает содержимое веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="82280-126">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="82280-127">Затем свойство **Links** возвращаемого **хтмлвебреспонсеобжект** используется для вывода свойства **href** каждой ссылки.</span><span class="sxs-lookup"><span data-stu-id="82280-127">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="82280-128">Пример 4. перехват сообщений без успешности Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="82280-128">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="82280-129">При `Invoke-WebRequest` обнаружении сообщения HTTP, не являющегося успешным (404, 500 и т. д.), оно не возвращает выходные данные и вызывает ошибку, которая завершается.</span><span class="sxs-lookup"><span data-stu-id="82280-129">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="82280-130">Чтобы перехватить ошибку и просмотреть **StatusCode** , можно заключить выполнение в `try/catch` блок.</span><span class="sxs-lookup"><span data-stu-id="82280-130">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="82280-131">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="82280-131">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost"
    # This will only execute if the Invoke-WebRequest is successful.
    $StatusCode = $Response.StatusCode
}
catch
{
    $StatusCode = $_.Exception.Response.StatusCode.value__
}
$StatusCode
```

```Output
404
```

<span data-ttu-id="82280-132">Завершающая ошибка перехвачена `catch` блоком, который извлекает **StatusCode** из объекта **исключения** .</span><span class="sxs-lookup"><span data-stu-id="82280-132">The terminating error is caught by the `catch` block, which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="82280-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82280-133">PARAMETERS</span></span>

### <span data-ttu-id="82280-134">-Body</span><span class="sxs-lookup"><span data-stu-id="82280-134">-Body</span></span>

<span data-ttu-id="82280-135">Задает основной текст запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-135">Specifies the body of the request.</span></span>
<span data-ttu-id="82280-136">Основной текст — это содержимое запроса, идущее после заголовков.</span><span class="sxs-lookup"><span data-stu-id="82280-136">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="82280-137">Можно также передать значение текста по конвейеру в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="82280-137">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="82280-138">Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.</span><span class="sxs-lookup"><span data-stu-id="82280-138">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="82280-139">Если входные данные являются запросом GET, а тело является **IDictionary** (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-139">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="82280-140">Для других запросов GET текст задается как значение текста запроса в стандартном `name=value` формате.</span><span class="sxs-lookup"><span data-stu-id="82280-140">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="82280-141">Если тело является формой или является выходным результатом `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.</span><span class="sxs-lookup"><span data-stu-id="82280-141">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="82280-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="82280-142">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="82280-143">или</span><span class="sxs-lookup"><span data-stu-id="82280-143">or -</span></span>

`Invoke-RestMethod https://website.com/service.aspx -Body $r.Forms\[0\]`

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="82280-144">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="82280-144">-Certificate</span></span>

<span data-ttu-id="82280-145">Задает сертификат клиента, который используется для выполнения защищенного веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-145">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="82280-146">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="82280-146">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="82280-147">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске **Certificate** ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="82280-147">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="82280-148">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="82280-148">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="82280-149">-CertificateThumbprint</span></span>

<span data-ttu-id="82280-150">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-150">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="82280-151">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="82280-151">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="82280-152">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="82280-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="82280-153">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="82280-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="82280-154">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="82280-154">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-155">-ContentType</span><span class="sxs-lookup"><span data-stu-id="82280-155">-ContentType</span></span>

<span data-ttu-id="82280-156">Задает тип содержимого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-156">Specifies the content type of the web request.</span></span>

<span data-ttu-id="82280-157">Если этот параметр пропущен и метод Request является POST, `Invoke-WebRequest` устанавливает тип содержимого application/x-www-Form-UrlEncoded.</span><span class="sxs-lookup"><span data-stu-id="82280-157">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="82280-158">В противном случае тип содержимого в вызове не указывается.</span><span class="sxs-lookup"><span data-stu-id="82280-158">Otherwise, the content type is not specified in the call.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="82280-159">-Credential</span></span>

<span data-ttu-id="82280-160">Указывает учетную запись пользователя, обладающую разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-160">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="82280-161">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="82280-161">The default is the current user.</span></span>

<span data-ttu-id="82280-162">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="82280-162">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="82280-163">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="82280-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="82280-164">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="82280-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-165">-Дисаблекипаливе</span><span class="sxs-lookup"><span data-stu-id="82280-165">-DisableKeepAlive</span></span>

<span data-ttu-id="82280-166">Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение **false**.</span><span class="sxs-lookup"><span data-stu-id="82280-166">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="82280-167">По умолчанию **KeepAlive** имеет **значение true**.</span><span class="sxs-lookup"><span data-stu-id="82280-167">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="82280-168">**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="82280-168">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="82280-169">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="82280-169">-Headers</span></span>

<span data-ttu-id="82280-170">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-170">Specifies the headers of the web request.</span></span> <span data-ttu-id="82280-171">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="82280-171">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="82280-172">Чтобы задать заголовки **UserAgent** , используйте параметр **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="82280-172">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="82280-173">Этот параметр нельзя использовать для указания заголовков **UserAgent** или cookie.</span><span class="sxs-lookup"><span data-stu-id="82280-173">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-174">-Файл</span><span class="sxs-lookup"><span data-stu-id="82280-174">-InFile</span></span>

<span data-ttu-id="82280-175">Получает содержимое веб-запроса из файла.</span><span class="sxs-lookup"><span data-stu-id="82280-175">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="82280-176">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="82280-176">Enter a path and file name.</span></span> <span data-ttu-id="82280-177">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="82280-177">If you omit the path, the default is the current location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-178">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="82280-178">-MaximumRedirection</span></span>

<span data-ttu-id="82280-179">Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="82280-179">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="82280-180">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="82280-180">The default value is 5.</span></span> <span data-ttu-id="82280-181">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="82280-181">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-182">-Method</span><span class="sxs-lookup"><span data-stu-id="82280-182">-Method</span></span>

<span data-ttu-id="82280-183">Задает метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-183">Specifies the method used for the web request.</span></span> <span data-ttu-id="82280-184">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="82280-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="82280-185">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="82280-185">Default</span></span>
- <span data-ttu-id="82280-186">DELETE</span><span class="sxs-lookup"><span data-stu-id="82280-186">Delete</span></span>
- <span data-ttu-id="82280-187">Получить</span><span class="sxs-lookup"><span data-stu-id="82280-187">Get</span></span>
- <span data-ttu-id="82280-188">Head</span><span class="sxs-lookup"><span data-stu-id="82280-188">Head</span></span>
- <span data-ttu-id="82280-189">Объединить</span><span class="sxs-lookup"><span data-stu-id="82280-189">Merge</span></span>
- <span data-ttu-id="82280-190">Варианты</span><span class="sxs-lookup"><span data-stu-id="82280-190">Options</span></span>
- <span data-ttu-id="82280-191">Обновление</span><span class="sxs-lookup"><span data-stu-id="82280-191">Patch</span></span>
- <span data-ttu-id="82280-192">Опубликовать</span><span class="sxs-lookup"><span data-stu-id="82280-192">Post</span></span>
- <span data-ttu-id="82280-193">Put</span><span class="sxs-lookup"><span data-stu-id="82280-193">Put</span></span>
- <span data-ttu-id="82280-194">Трассировка</span><span class="sxs-lookup"><span data-stu-id="82280-194">Trace</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-195">-Файл</span><span class="sxs-lookup"><span data-stu-id="82280-195">-OutFile</span></span>

<span data-ttu-id="82280-196">Указывает выходной файл, для которого этот командлет сохраняет текст ответа.</span><span class="sxs-lookup"><span data-stu-id="82280-196">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="82280-197">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="82280-197">Enter a path and file name.</span></span>
<span data-ttu-id="82280-198">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="82280-198">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="82280-199">По умолчанию `Invoke-WebRequest` возвращает результаты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="82280-199">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="82280-200">Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="82280-200">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="82280-201">-PassThru</span></span>

<span data-ttu-id="82280-202">Указывает, что командлет возвращает результаты в дополнение к записи в файл.</span><span class="sxs-lookup"><span data-stu-id="82280-202">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="82280-203">Этот параметр активен, если в команде также используется параметр **OutFile**.</span><span class="sxs-lookup"><span data-stu-id="82280-203">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="82280-204">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="82280-204">-Proxy</span></span>

<span data-ttu-id="82280-205">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="82280-205">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="82280-206">Введите URI сетевого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="82280-206">Enter the URI of a network proxy server.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-207">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="82280-207">-ProxyCredential</span></span>

<span data-ttu-id="82280-208">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="82280-208">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="82280-209">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="82280-209">The default is the current user.</span></span>

<span data-ttu-id="82280-210">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="82280-210">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="82280-211">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="82280-211">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="82280-212">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="82280-212">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-213">-Проксюседефаулткредентиалс</span><span class="sxs-lookup"><span data-stu-id="82280-213">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="82280-214">Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.</span><span class="sxs-lookup"><span data-stu-id="82280-214">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="82280-215">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="82280-215">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="82280-216">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="82280-216">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="82280-217">-Сессионвариабле</span><span class="sxs-lookup"><span data-stu-id="82280-217">-SessionVariable</span></span>

<span data-ttu-id="82280-218">Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.</span><span class="sxs-lookup"><span data-stu-id="82280-218">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="82280-219">Введите имя переменной без символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="82280-219">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="82280-220">При указании переменной сеанса `Invoke-WebRequest` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82280-220">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="82280-221">Переменную в сеансе можно использовать сразу после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="82280-221">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="82280-222">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="82280-222">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="82280-223">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="82280-223">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="82280-224">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="82280-224">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="82280-225">Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="82280-225">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="82280-226">При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-226">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="82280-227">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="82280-227">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="82280-228">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-228">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="82280-229">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="82280-229">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-230">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="82280-230">-TimeoutSec</span></span>

<span data-ttu-id="82280-231">Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="82280-231">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="82280-232">Значение по умолчанию, равное 0, указывает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="82280-232">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="82280-233">Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде **чем будет создано исключение,** а время ожидания запроса истечет.</span><span class="sxs-lookup"><span data-stu-id="82280-233">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-234">-Трансференкодинг</span><span class="sxs-lookup"><span data-stu-id="82280-234">-TransferEncoding</span></span>

<span data-ttu-id="82280-235">Задает значение для заголовка transfer-encoding ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="82280-235">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="82280-236">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="82280-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="82280-237">Chunked</span><span class="sxs-lookup"><span data-stu-id="82280-237">Chunked</span></span>
- <span data-ttu-id="82280-238">Сжать</span><span class="sxs-lookup"><span data-stu-id="82280-238">Compress</span></span>
- <span data-ttu-id="82280-239">Deflate</span><span class="sxs-lookup"><span data-stu-id="82280-239">Deflate</span></span>
- <span data-ttu-id="82280-240">GZip</span><span class="sxs-lookup"><span data-stu-id="82280-240">GZip</span></span>
- <span data-ttu-id="82280-241">Идентификация</span><span class="sxs-lookup"><span data-stu-id="82280-241">Identity</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-242">— URI</span><span class="sxs-lookup"><span data-stu-id="82280-242">-Uri</span></span>

<span data-ttu-id="82280-243">Указывает URI интернет-ресурса, на который отправляется веб-запрос.</span><span class="sxs-lookup"><span data-stu-id="82280-243">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="82280-244">Введите URI.</span><span class="sxs-lookup"><span data-stu-id="82280-244">Enter a URI.</span></span> <span data-ttu-id="82280-245">Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.</span><span class="sxs-lookup"><span data-stu-id="82280-245">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="82280-246">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="82280-246">This parameter is required.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-247">-Усебасикпарсинг</span><span class="sxs-lookup"><span data-stu-id="82280-247">-UseBasicParsing</span></span>

<span data-ttu-id="82280-248">Указывает, что командлет использует объект Response для HTML-содержимого без синтаксического анализа модель DOM (DOM).</span><span class="sxs-lookup"><span data-stu-id="82280-248">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="82280-249">Этот параметр является обязательным, если на компьютерах не установлен Internet Explorer, например, в случае установки основных серверных компонентов операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="82280-249">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="82280-250">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="82280-250">-UseDefaultCredentials</span></span>

<span data-ttu-id="82280-251">Указывает, что кмдет использует учетные данные текущего пользователя для отправки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-251">Indicates that the cmdet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="82280-252">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="82280-252">-UserAgent</span></span>

<span data-ttu-id="82280-253">Указывает строку агента пользователя для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-253">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="82280-254">Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` небольшому варианту для каждой операционной системы и платформы.</span><span class="sxs-lookup"><span data-stu-id="82280-254">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="82280-255">Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari.</span><span class="sxs-lookup"><span data-stu-id="82280-255">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="82280-256">Например, следующая команда использует строку агента пользователя для Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="82280-256">For example, the following command uses the user agent string for Internet Explorer</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-257">-Семинар</span><span class="sxs-lookup"><span data-stu-id="82280-257">-WebSession</span></span>

<span data-ttu-id="82280-258">Указывает сеанс веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-258">Specifies a web request session.</span></span> <span data-ttu-id="82280-259">Введите имя переменной, включая знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="82280-259">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="82280-260">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="82280-260">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="82280-261">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="82280-261">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="82280-262">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="82280-262">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="82280-263">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="82280-263">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="82280-264">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="82280-264">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="82280-265">Чтобы создать сеанс веб-запроса, введите имя переменной (без знака доллара) в качестве значения параметра **сессионвариабле** `Invoke-WebRequest` команды.</span><span class="sxs-lookup"><span data-stu-id="82280-265">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="82280-266">`Invoke-WebRequest` создает сеанс и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="82280-266">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="82280-267">В последующих командах используйте переменную в качестве значения параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="82280-267">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="82280-268">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="82280-268">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82280-269">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="82280-269">CommonParameters</span></span>

<span data-ttu-id="82280-270">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="82280-270">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="82280-271">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="82280-271">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="82280-272">Входные данные</span><span class="sxs-lookup"><span data-stu-id="82280-272">INPUTS</span></span>

### <span data-ttu-id="82280-273">System.Object</span><span class="sxs-lookup"><span data-stu-id="82280-273">System.Object</span></span>

<span data-ttu-id="82280-274">Текст веб-запроса можно передать в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="82280-274">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="82280-275">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="82280-275">OUTPUTS</span></span>

### <span data-ttu-id="82280-276">Microsoft.PowerShell.Commands.HtmЛвебреспонсеобжект</span><span class="sxs-lookup"><span data-stu-id="82280-276">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="82280-277">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="82280-277">NOTES</span></span>

## <span data-ttu-id="82280-278">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="82280-278">RELATED LINKS</span></span>

[<span data-ttu-id="82280-279">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="82280-279">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="82280-280">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="82280-280">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="82280-281">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="82280-281">ConvertTo-Json</span></span>](ConvertTo-Json.md)
