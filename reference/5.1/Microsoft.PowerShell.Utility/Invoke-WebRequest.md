---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 25da6262e93be3e3749aabaf4950e2fbcd91ff5c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230278"
---
# <span data-ttu-id="b47cb-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="b47cb-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="b47cb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b47cb-104">SYNOPSIS</span></span>
<span data-ttu-id="b47cb-105">Получает содержимое с веб-страницы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b47cb-105">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="b47cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b47cb-106">SYNTAX</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="b47cb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b47cb-107">DESCRIPTION</span></span>

<span data-ttu-id="b47cb-108">`Invoke-WebRequest`Командлет отправляет запросы HTTP, HTTPS, FTP и файлы на веб-страницу или веб-службу.</span><span class="sxs-lookup"><span data-stu-id="b47cb-108">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="b47cb-109">Он анализирует ответ и возвращает коллекции форм, ссылок, изображений и других значимых HTML-элементов.</span><span class="sxs-lookup"><span data-stu-id="b47cb-109">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="b47cb-110">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b47cb-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="b47cb-111">По умолчанию код сценария на веб-странице может выполняться при синтаксическом анализе страницы для заполнения `ParsedHtml` Свойства.</span><span class="sxs-lookup"><span data-stu-id="b47cb-111">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span>
> <span data-ttu-id="b47cb-112">`-UseBasicParsing`Чтобы отключить это действие, используйте параметр.</span><span class="sxs-lookup"><span data-stu-id="b47cb-112">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="b47cb-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b47cb-113">EXAMPLES</span></span>

### <span data-ttu-id="b47cb-114">Пример 1. Отправка веб-запроса</span><span class="sxs-lookup"><span data-stu-id="b47cb-114">Example 1: Send a web request</span></span>

<span data-ttu-id="b47cb-115">Эта команда использует `Invoke-WebRequest` командлет для отправки веб-запроса на сайт Bing.com.</span><span class="sxs-lookup"><span data-stu-id="b47cb-115">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

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

<span data-ttu-id="b47cb-116">Первая команда выдает запрос и сохраняет ответ в `$R` переменной.</span><span class="sxs-lookup"><span data-stu-id="b47cb-116">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="b47cb-117">Вторая команда фильтрует объекты в свойстве **аллелементс** , где свойство **Name** имеет значение "\* value", а **TagName** — "input".</span><span class="sxs-lookup"><span data-stu-id="b47cb-117">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="b47cb-118">Отфильтрованные результаты передаются в, `Select-Object` чтобы выбрать свойства " **имя** " и " **значение** ".</span><span class="sxs-lookup"><span data-stu-id="b47cb-118">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="b47cb-119">Пример 2. Использование веб-службы с отслеживанием состояния</span><span class="sxs-lookup"><span data-stu-id="b47cb-119">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="b47cb-120">В этом примере показано, как использовать `Invoke-WebRequest` командлет с веб-службой с отслеживанием состояния, например Facebook.</span><span class="sxs-lookup"><span data-stu-id="b47cb-120">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

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

<span data-ttu-id="b47cb-121">Первая команда использует `Invoke-WebRequest` командлет для отправки запроса на вход.</span><span class="sxs-lookup"><span data-stu-id="b47cb-121">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="b47cb-122">Команда задает значение "FB" в качестве значения параметра **сессионвариабле** и сохраняет результат в `$R` переменной.</span><span class="sxs-lookup"><span data-stu-id="b47cb-122">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="b47cb-123">После выполнения команды `$R` переменная содержит **хтмлвебреспонсеобжект** , а `$FB` переменная содержит объект **вебрекуестсессион** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-123">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="b47cb-124">После того как `Invoke-WebRequest` командлет войдет в Facebook, свойство **StatusDescription** объекта веб-ответа в `$R` переменной указывает, что пользователь успешно выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="b47cb-124">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="b47cb-125">Пример 3. получение ссылок с веб-страницы</span><span class="sxs-lookup"><span data-stu-id="b47cb-125">Example 3: Get links from a web page</span></span>

<span data-ttu-id="b47cb-126">Эта команда возвращает ссылки с веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="b47cb-126">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="b47cb-127">`Invoke-WebRequest`Командлет возвращает содержимое веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="b47cb-127">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="b47cb-128">Затем свойство **Links** возвращаемого **хтмлвебреспонсеобжект** используется для вывода свойства **href** каждой ссылки.</span><span class="sxs-lookup"><span data-stu-id="b47cb-128">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="b47cb-129">Пример 4. перехват сообщений без успешности Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="b47cb-129">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="b47cb-130">При `Invoke-WebRequest` обнаружении сообщения HTTP, не являющегося успешным (404, 500 и т. д.), оно не возвращает выходные данные и вызывает ошибку, которая завершается.</span><span class="sxs-lookup"><span data-stu-id="b47cb-130">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="b47cb-131">Чтобы перехватить ошибку и просмотреть **StatusCode** , можно заключить выполнение в `try/catch` блок.</span><span class="sxs-lookup"><span data-stu-id="b47cb-131">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="b47cb-132">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="b47cb-132">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
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

<span data-ttu-id="b47cb-133">Первая команда вызывает `Invoke-WebRequest` с параметром **ErrorAction** **остановки** , который заставляет `Invoke-WebRequest` вызывать завершающую ошибку для всех неудачных запросов.</span><span class="sxs-lookup"><span data-stu-id="b47cb-133">The first command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="b47cb-134">Завершающая ошибка перехвачена `catch` блоком, который извлекает **StatusCode** из объекта **исключения** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-134">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="b47cb-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b47cb-135">PARAMETERS</span></span>

### <span data-ttu-id="b47cb-136">-Body</span><span class="sxs-lookup"><span data-stu-id="b47cb-136">-Body</span></span>

<span data-ttu-id="b47cb-137">Задает основной текст запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-137">Specifies the body of the request.</span></span>
<span data-ttu-id="b47cb-138">Основной текст — это содержимое запроса, идущее после заголовков.</span><span class="sxs-lookup"><span data-stu-id="b47cb-138">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="b47cb-139">Можно также передать значение текста по конвейеру в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="b47cb-139">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="b47cb-140">Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.</span><span class="sxs-lookup"><span data-stu-id="b47cb-140">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="b47cb-141">Если входные данные являются запросом GET, а тело является **IDictionary** (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-141">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="b47cb-142">Для других запросов GET текст задается как значение текста запроса в стандартном `name=value` формате.</span><span class="sxs-lookup"><span data-stu-id="b47cb-142">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="b47cb-143">Если тело является формой или является выходным результатом `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.</span><span class="sxs-lookup"><span data-stu-id="b47cb-143">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="b47cb-144">Пример:</span><span class="sxs-lookup"><span data-stu-id="b47cb-144">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="b47cb-145">или</span><span class="sxs-lookup"><span data-stu-id="b47cb-145">or -</span></span>

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

### <span data-ttu-id="b47cb-146">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="b47cb-146">-Certificate</span></span>

<span data-ttu-id="b47cb-147">Задает сертификат клиента, который используется для выполнения защищенного веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-147">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="b47cb-148">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="b47cb-148">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="b47cb-149">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске **Certificate** ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="b47cb-149">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="b47cb-150">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b47cb-150">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="b47cb-151">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="b47cb-151">-CertificateThumbprint</span></span>

<span data-ttu-id="b47cb-152">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-152">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="b47cb-153">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="b47cb-153">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="b47cb-154">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="b47cb-154">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="b47cb-155">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="b47cb-155">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="b47cb-156">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="b47cb-156">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="b47cb-157">-ContentType</span><span class="sxs-lookup"><span data-stu-id="b47cb-157">-ContentType</span></span>

<span data-ttu-id="b47cb-158">Задает тип содержимого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-158">Specifies the content type of the web request.</span></span>

<span data-ttu-id="b47cb-159">Если этот параметр пропущен и метод Request является POST, `Invoke-WebRequest` устанавливает тип содержимого application/x-www-Form-UrlEncoded.</span><span class="sxs-lookup"><span data-stu-id="b47cb-159">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="b47cb-160">В противном случае тип содержимого в вызове не указывается.</span><span class="sxs-lookup"><span data-stu-id="b47cb-160">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="b47cb-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="b47cb-161">-Credential</span></span>

<span data-ttu-id="b47cb-162">Указывает учетную запись пользователя, обладающую разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-162">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="b47cb-163">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b47cb-163">The default is the current user.</span></span>

<span data-ttu-id="b47cb-164">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="b47cb-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="b47cb-165">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="b47cb-165">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b47cb-166">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="b47cb-166">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="b47cb-167">-Дисаблекипаливе</span><span class="sxs-lookup"><span data-stu-id="b47cb-167">-DisableKeepAlive</span></span>

<span data-ttu-id="b47cb-168">Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение **false** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-168">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False** .</span></span> <span data-ttu-id="b47cb-169">По умолчанию **KeepAlive** имеет **значение true** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-169">By default, **KeepAlive** is **True** .</span></span> <span data-ttu-id="b47cb-170">**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="b47cb-170">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="b47cb-171">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="b47cb-171">-Headers</span></span>

<span data-ttu-id="b47cb-172">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-172">Specifies the headers of the web request.</span></span> <span data-ttu-id="b47cb-173">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="b47cb-173">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="b47cb-174">Чтобы задать заголовки **UserAgent** , используйте параметр **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-174">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="b47cb-175">Этот параметр нельзя использовать для указания заголовков **UserAgent** или cookie.</span><span class="sxs-lookup"><span data-stu-id="b47cb-175">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="b47cb-176">-Файл</span><span class="sxs-lookup"><span data-stu-id="b47cb-176">-InFile</span></span>

<span data-ttu-id="b47cb-177">Получает содержимое веб-запроса из файла.</span><span class="sxs-lookup"><span data-stu-id="b47cb-177">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="b47cb-178">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="b47cb-178">Enter a path and file name.</span></span> <span data-ttu-id="b47cb-179">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="b47cb-179">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="b47cb-180">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="b47cb-180">-MaximumRedirection</span></span>

<span data-ttu-id="b47cb-181">Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="b47cb-181">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="b47cb-182">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="b47cb-182">The default value is 5.</span></span> <span data-ttu-id="b47cb-183">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="b47cb-183">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="b47cb-184">-Method</span><span class="sxs-lookup"><span data-stu-id="b47cb-184">-Method</span></span>

<span data-ttu-id="b47cb-185">Задает метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-185">Specifies the method used for the web request.</span></span> <span data-ttu-id="b47cb-186">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b47cb-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b47cb-187">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b47cb-187">Default</span></span>
- <span data-ttu-id="b47cb-188">DELETE</span><span class="sxs-lookup"><span data-stu-id="b47cb-188">Delete</span></span>
- <span data-ttu-id="b47cb-189">Получить</span><span class="sxs-lookup"><span data-stu-id="b47cb-189">Get</span></span>
- <span data-ttu-id="b47cb-190">Head</span><span class="sxs-lookup"><span data-stu-id="b47cb-190">Head</span></span>
- <span data-ttu-id="b47cb-191">Объединить</span><span class="sxs-lookup"><span data-stu-id="b47cb-191">Merge</span></span>
- <span data-ttu-id="b47cb-192">Параметры</span><span class="sxs-lookup"><span data-stu-id="b47cb-192">Options</span></span>
- <span data-ttu-id="b47cb-193">Обновление</span><span class="sxs-lookup"><span data-stu-id="b47cb-193">Patch</span></span>
- <span data-ttu-id="b47cb-194">Опубликовать</span><span class="sxs-lookup"><span data-stu-id="b47cb-194">Post</span></span>
- <span data-ttu-id="b47cb-195">Put</span><span class="sxs-lookup"><span data-stu-id="b47cb-195">Put</span></span>
- <span data-ttu-id="b47cb-196">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b47cb-196">Trace</span></span>

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

### <span data-ttu-id="b47cb-197">-Файл</span><span class="sxs-lookup"><span data-stu-id="b47cb-197">-OutFile</span></span>

<span data-ttu-id="b47cb-198">Указывает выходной файл, для которого этот командлет сохраняет текст ответа.</span><span class="sxs-lookup"><span data-stu-id="b47cb-198">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="b47cb-199">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="b47cb-199">Enter a path and file name.</span></span>
<span data-ttu-id="b47cb-200">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="b47cb-200">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="b47cb-201">По умолчанию `Invoke-WebRequest` возвращает результаты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b47cb-201">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="b47cb-202">Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-202">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="b47cb-203">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b47cb-203">-PassThru</span></span>

<span data-ttu-id="b47cb-204">Указывает, что командлет возвращает результаты в дополнение к записи в файл.</span><span class="sxs-lookup"><span data-stu-id="b47cb-204">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="b47cb-205">Этот параметр активен, если в команде также используется параметр **OutFile** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-205">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="b47cb-206">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="b47cb-206">-Proxy</span></span>

<span data-ttu-id="b47cb-207">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b47cb-207">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="b47cb-208">Введите URI сетевого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b47cb-208">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="b47cb-209">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b47cb-209">-ProxyCredential</span></span>

<span data-ttu-id="b47cb-210">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-210">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="b47cb-211">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b47cb-211">The default is the current user.</span></span>

<span data-ttu-id="b47cb-212">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="b47cb-212">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="b47cb-213">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="b47cb-213">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="b47cb-214">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b47cb-214">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="b47cb-215">-Проксюседефаулткредентиалс</span><span class="sxs-lookup"><span data-stu-id="b47cb-215">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="b47cb-216">Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.</span><span class="sxs-lookup"><span data-stu-id="b47cb-216">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="b47cb-217">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="b47cb-217">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="b47cb-218">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b47cb-218">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="b47cb-219">-Сессионвариабле</span><span class="sxs-lookup"><span data-stu-id="b47cb-219">-SessionVariable</span></span>

<span data-ttu-id="b47cb-220">Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.</span><span class="sxs-lookup"><span data-stu-id="b47cb-220">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="b47cb-221">Введите имя переменной без символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="b47cb-221">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="b47cb-222">При указании переменной сеанса `Invoke-WebRequest` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b47cb-222">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="b47cb-223">Переменную в сеансе можно использовать сразу после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b47cb-223">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="b47cb-224">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="b47cb-224">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="b47cb-225">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="b47cb-225">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="b47cb-226">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="b47cb-226">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="b47cb-227">Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-227">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="b47cb-228">При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-228">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="b47cb-229">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-229">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="b47cb-230">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-230">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="b47cb-231">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-231">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="b47cb-232">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="b47cb-232">-TimeoutSec</span></span>

<span data-ttu-id="b47cb-233">Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="b47cb-233">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="b47cb-234">Значение по умолчанию, равное 0, указывает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="b47cb-234">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="b47cb-235">Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде **чем будет создано исключение,** а время ожидания запроса истечет.</span><span class="sxs-lookup"><span data-stu-id="b47cb-235">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="b47cb-236">-Трансференкодинг</span><span class="sxs-lookup"><span data-stu-id="b47cb-236">-TransferEncoding</span></span>

<span data-ttu-id="b47cb-237">Задает значение для заголовка transfer-encoding ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="b47cb-237">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="b47cb-238">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b47cb-238">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b47cb-239">Chunked</span><span class="sxs-lookup"><span data-stu-id="b47cb-239">Chunked</span></span>
- <span data-ttu-id="b47cb-240">Сжать</span><span class="sxs-lookup"><span data-stu-id="b47cb-240">Compress</span></span>
- <span data-ttu-id="b47cb-241">Deflate</span><span class="sxs-lookup"><span data-stu-id="b47cb-241">Deflate</span></span>
- <span data-ttu-id="b47cb-242">GZip</span><span class="sxs-lookup"><span data-stu-id="b47cb-242">GZip</span></span>
- <span data-ttu-id="b47cb-243">Идентификация</span><span class="sxs-lookup"><span data-stu-id="b47cb-243">Identity</span></span>

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

### <span data-ttu-id="b47cb-244">— URI</span><span class="sxs-lookup"><span data-stu-id="b47cb-244">-Uri</span></span>

<span data-ttu-id="b47cb-245">Указывает URI интернет-ресурса, на который отправляется веб-запрос.</span><span class="sxs-lookup"><span data-stu-id="b47cb-245">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="b47cb-246">Введите URI.</span><span class="sxs-lookup"><span data-stu-id="b47cb-246">Enter a URI.</span></span> <span data-ttu-id="b47cb-247">Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.</span><span class="sxs-lookup"><span data-stu-id="b47cb-247">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="b47cb-248">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="b47cb-248">This parameter is required.</span></span>

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

### <span data-ttu-id="b47cb-249">-Усебасикпарсинг</span><span class="sxs-lookup"><span data-stu-id="b47cb-249">-UseBasicParsing</span></span>

<span data-ttu-id="b47cb-250">Указывает, что командлет использует объект Response для HTML-содержимого без синтаксического анализа модель DOM (DOM).</span><span class="sxs-lookup"><span data-stu-id="b47cb-250">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="b47cb-251">Этот параметр является обязательным, если на компьютерах не установлен Internet Explorer, например, в случае установки основных серверных компонентов операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b47cb-251">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="b47cb-252">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="b47cb-252">-UseDefaultCredentials</span></span>

<span data-ttu-id="b47cb-253">Указывает, что кмдет использует учетные данные текущего пользователя для отправки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-253">Indicates that the cmdet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="b47cb-254">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="b47cb-254">-UserAgent</span></span>

<span data-ttu-id="b47cb-255">Указывает строку агента пользователя для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-255">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="b47cb-256">Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` небольшому варианту для каждой операционной системы и платформы.</span><span class="sxs-lookup"><span data-stu-id="b47cb-256">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="b47cb-257">Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari.</span><span class="sxs-lookup"><span data-stu-id="b47cb-257">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="b47cb-258">Например, следующая команда использует строку агента пользователя для Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b47cb-258">For example, the following command uses the user agent string for Internet Explorer</span></span>

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

### <span data-ttu-id="b47cb-259">-Семинар</span><span class="sxs-lookup"><span data-stu-id="b47cb-259">-WebSession</span></span>

<span data-ttu-id="b47cb-260">Указывает сеанс веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-260">Specifies a web request session.</span></span> <span data-ttu-id="b47cb-261">Введите имя переменной, включая знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="b47cb-261">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="b47cb-262">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-262">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="b47cb-263">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b47cb-263">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="b47cb-264">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="b47cb-264">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="b47cb-265">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="b47cb-265">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="b47cb-266">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="b47cb-266">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="b47cb-267">Чтобы создать сеанс веб-запроса, введите имя переменной (без знака доллара) в качестве значения параметра **сессионвариабле** `Invoke-WebRequest` команды.</span><span class="sxs-lookup"><span data-stu-id="b47cb-267">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="b47cb-268">`Invoke-WebRequest` создает сеанс и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="b47cb-268">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="b47cb-269">В последующих командах используйте переменную в качестве значения параметра **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-269">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="b47cb-270">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="b47cb-270">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="b47cb-271">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b47cb-271">CommonParameters</span></span>

<span data-ttu-id="b47cb-272">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b47cb-272">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b47cb-273">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b47cb-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b47cb-274">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b47cb-274">INPUTS</span></span>

### <span data-ttu-id="b47cb-275">System.Object</span><span class="sxs-lookup"><span data-stu-id="b47cb-275">System.Object</span></span>

<span data-ttu-id="b47cb-276">Текст веб-запроса можно передать в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="b47cb-276">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="b47cb-277">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b47cb-277">OUTPUTS</span></span>

### <span data-ttu-id="b47cb-278">Microsoft.PowerShell.Commands.HtmЛвебреспонсеобжект</span><span class="sxs-lookup"><span data-stu-id="b47cb-278">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="b47cb-279">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b47cb-279">NOTES</span></span>

## <span data-ttu-id="b47cb-280">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b47cb-280">RELATED LINKS</span></span>

[<span data-ttu-id="b47cb-281">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="b47cb-281">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="b47cb-282">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="b47cb-282">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="b47cb-283">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="b47cb-283">ConvertTo-Json</span></span>](ConvertTo-Json.md)
