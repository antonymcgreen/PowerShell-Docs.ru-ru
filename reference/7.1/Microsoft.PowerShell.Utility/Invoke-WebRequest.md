---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: bb23f2ed01573a3f67c19f45db495cd86ecefe0c
ms.sourcegitcommit: 69b08b28ee2ef3168065672a23b9b6f0c578c95b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "93230598"
---
# <span data-ttu-id="612ab-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="612ab-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="612ab-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="612ab-104">SYNOPSIS</span></span>
<span data-ttu-id="612ab-105">Получает содержимое с веб-страницы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="612ab-105">Gets content from a web page on the internet.</span></span>

## <span data-ttu-id="612ab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="612ab-106">SYNTAX</span></span>

### <span data-ttu-id="612ab-107">Стандардмесод (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="612ab-107">StandardMethod (Default)</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="612ab-108">стандардмесоднопрокси</span><span class="sxs-lookup"><span data-stu-id="612ab-108">StandardMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>] -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="612ab-109">кустоммесод</span><span class="sxs-lookup"><span data-stu-id="612ab-109">CustomMethod</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="612ab-110">кустоммесоднопрокси</span><span class="sxs-lookup"><span data-stu-id="612ab-110">CustomMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="612ab-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="612ab-111">DESCRIPTION</span></span>

<span data-ttu-id="612ab-112">`Invoke-WebRequest`Командлет отправляет запросы HTTP и HTTPS на веб-страницу или веб-службу.</span><span class="sxs-lookup"><span data-stu-id="612ab-112">The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service.</span></span> <span data-ttu-id="612ab-113">Он анализирует ответ и возвращает коллекции ссылок, изображений и других значащих HTML-элементов.</span><span class="sxs-lookup"><span data-stu-id="612ab-113">It parses the response and returns collections of links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="612ab-114">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="612ab-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="612ab-115">Начиная с PowerShell 7,0, `Invoke-WebRequest` поддерживает настройку прокси-сервера, определяемую переменными среды.</span><span class="sxs-lookup"><span data-stu-id="612ab-115">Beginning in PowerShell 7.0, `Invoke-WebRequest` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="612ab-116">См. раздел " [Примечания](#notes) " этой статьи.</span><span class="sxs-lookup"><span data-stu-id="612ab-116">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="612ab-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="612ab-117">EXAMPLES</span></span>

### <span data-ttu-id="612ab-118">Пример 1. Отправка веб-запроса</span><span class="sxs-lookup"><span data-stu-id="612ab-118">Example 1: Send a web request</span></span>

<span data-ttu-id="612ab-119">В этом примере `Invoke-WebRequest` командлет используется для отправки веб-запроса на сайт Bing.com.</span><span class="sxs-lookup"><span data-stu-id="612ab-119">This example uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$Response = Invoke-WebRequest -URI https://www.bing.com/search?q=how+many+feet+in+a+mile
$Response.InputFields | Where-Object {
    $_.name -like "* Value*"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="612ab-120">Первая команда выдает запрос и сохраняет ответ в `$Response` переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-120">The first command issues the request and saves the response in the `$Response` variable.</span></span>

<span data-ttu-id="612ab-121">Вторая команда получает все **инпутфиелд** , где свойство **Name** имеет значение `"* Value"` .</span><span class="sxs-lookup"><span data-stu-id="612ab-121">The second command gets any **InputField** where the **Name** property is like `"* Value"`.</span></span> <span data-ttu-id="612ab-122">Отфильтрованные результаты передаются в, `Select-Object` чтобы выбрать свойства " **имя** " и " **значение** ".</span><span class="sxs-lookup"><span data-stu-id="612ab-122">The filtered results are piped to `Select-Object` to select the **Name** and **Value** properties.</span></span>

### <span data-ttu-id="612ab-123">Пример 2. Использование веб-службы с отслеживанием состояния</span><span class="sxs-lookup"><span data-stu-id="612ab-123">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="612ab-124">В этом примере показано, как использовать `Invoke-WebRequest` командлет с веб-службой с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="612ab-124">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service.</span></span>

```powershell
$Body = @{
    User = 'jdoe'
    password = 'P@S$w0rd!'
}
$LoginResponse = Invoke-WebRequest 'https://www.contoso.com/login/' -SessionVariable 'Session' -Body $Body -Method 'POST'

$Session

$ProfileResponse = Invoke-WebRequest 'https://www.contoso.com/profile/' -WebSession $Session

$ProfileResponse
```

<span data-ttu-id="612ab-125">Первый вызов для `Invoke-WebRequest` отправки запроса на вход.</span><span class="sxs-lookup"><span data-stu-id="612ab-125">The first call to `Invoke-WebRequest` sends a sign-in request.</span></span> <span data-ttu-id="612ab-126">Команда задает значение "Session" в качестве значения параметра **-сессионвариабле** и сохраняет результат в `$LoginResponse` переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-126">The command specifies a value of "Session" for the value of the **-SessionVariable** parameter, and saves the result in the `$LoginResponse` variable.</span></span> <span data-ttu-id="612ab-127">После выполнения команды переменная содержит переменную, `$LoginResponse` `BasicHtmlWebResponseObject` а `$Session` переменная содержит `WebRequestSession` объект.</span><span class="sxs-lookup"><span data-stu-id="612ab-127">When the command completes, the `$LoginResponse` variable contains an `BasicHtmlWebResponseObject` and the `$Session` variable contains a `WebRequestSession` object.</span></span> <span data-ttu-id="612ab-128">Это записывает пользователя на сайт.</span><span class="sxs-lookup"><span data-stu-id="612ab-128">This logs the user into the site.</span></span>

<span data-ttu-id="612ab-129">Вызов `$Session` сам по себе показывает `WebRequestSession` объект в переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-129">The call to `$Session` by itself shows the `WebRequestSession` object in the variable.</span></span>

<span data-ttu-id="612ab-130">Второй вызов `Invoke-WebRequest` извлекает профиль пользователя, который требует входа пользователя на сайт.</span><span class="sxs-lookup"><span data-stu-id="612ab-130">The second call to `Invoke-WebRequest` fetches the user's profile which requires that the user be logged into the site.</span></span> <span data-ttu-id="612ab-131">Данные сеанса, хранящиеся в `$Session` переменной, используются для предоставления файлов cookie сеанса сайту, созданному во время входа.</span><span class="sxs-lookup"><span data-stu-id="612ab-131">The session data stored in the `$Session` variable is used to provide session cookies to the site created during the login.</span></span> <span data-ttu-id="612ab-132">Результат сохраняется в `$ProfileResponse` переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-132">The result is saved in the `$ProfileResponse` variable.</span></span>

<span data-ttu-id="612ab-133">Вызов `$ProfileResponse` сам по себе показывает `BasicHtmlWebResponseObject` в переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-133">The call to `$ProfileResponse` by itself shows the `BasicHtmlWebResponseObject` in the variable.</span></span>

### <span data-ttu-id="612ab-134">Пример 3. получение ссылок с веб-страницы</span><span class="sxs-lookup"><span data-stu-id="612ab-134">Example 3: Get links from a web page</span></span>

<span data-ttu-id="612ab-135">В этом примере выполняется получение ссылок на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="612ab-135">This example gets the links in a web page.</span></span> <span data-ttu-id="612ab-136">Он использует `Invoke-WebRequest` командлет для получения содержимого веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="612ab-136">It uses the `Invoke-WebRequest` cmdlet to get the web page content.</span></span> <span data-ttu-id="612ab-137">Затем используется свойство **Links** объекта, `BasicHtmlWebResponseObject` которое `Invoke-WebRequest` возвращает, и свойство **href** каждой ссылки.</span><span class="sxs-lookup"><span data-stu-id="612ab-137">Then it uses the **Links** property of the `BasicHtmlWebResponseObject` that `Invoke-WebRequest` returns, and the **Href** property of each link.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### <span data-ttu-id="612ab-138">Пример 4. записывает содержимое ответа в файл, используя кодировку, определенную на запрошенной странице.</span><span class="sxs-lookup"><span data-stu-id="612ab-138">Example 4: Writes the response content to a file using the encoding defined in the requested page.</span></span>

<span data-ttu-id="612ab-139">В этом примере `Invoke-WebRequest` командлет используется для получения содержимого веб-страницы для страницы документации по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="612ab-139">This example uses the `Invoke-WebRequest` cmdlet to retrieve the web page content of a PowerShell documentation page.</span></span>

```powershell
$Response = Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs"
$Stream = [System.IO.StreamWriter]::new('.\docspage.html', $false, $Response.Encoding)
try {
    $Stream.Write($Response.Content)
}
finally {
    $Stream.Dispose()
}
```

<span data-ttu-id="612ab-140">Первая команда извлекает страницу и сохраняет объект ответа в `$Response` переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-140">The first command retrieves the page and saves the response object in the `$Response` variable.</span></span>

<span data-ttu-id="612ab-141">Вторая команда создает объект `StreamWriter` для использования при записи содержимого ответа в файл.</span><span class="sxs-lookup"><span data-stu-id="612ab-141">The second command creates a `StreamWriter` to use to write the response content to a file.</span></span> <span data-ttu-id="612ab-142">Свойство **Encoding** объекта Response используется для задания кодировки для файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-142">The **Encoding** property of the response object is used to set the encoding for the file.</span></span>

<span data-ttu-id="612ab-143">Последние несколько команд записывают в файл свойство **Content** , а затем удаляют `StreamWriter` .</span><span class="sxs-lookup"><span data-stu-id="612ab-143">The final few commands write the **Content** property to the file then disposes the `StreamWriter`.</span></span>

<span data-ttu-id="612ab-144">Обратите внимание, что свойство **Encoding** имеет значение null, если веб-запрос не возвращает текстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="612ab-144">Note that the **Encoding** property is null if the web request doesn't return text content.</span></span>

### <span data-ttu-id="612ab-145">Пример 5. Отправка файла составного или многофайлового данных</span><span class="sxs-lookup"><span data-stu-id="612ab-145">Example 5: Submit a multipart/form-data file</span></span>

<span data-ttu-id="612ab-146">В этом примере используется `Invoke-WebRequest` командлет для отправки файла в качестве `multipart/form-data` отправки.</span><span class="sxs-lookup"><span data-stu-id="612ab-146">This example uses the `Invoke-WebRequest` cmdlet upload a file as a `multipart/form-data` submission.</span></span> <span data-ttu-id="612ab-147">Файл `c:\document.txt` отправляется в виде поля формы `document` с параметром `Content-Type` `text/plain` .</span><span class="sxs-lookup"><span data-stu-id="612ab-147">The file `c:\document.txt` is submitted as the form field `document` with the `Content-Type` of `text/plain`.</span></span>

```powershell
$FilePath = 'c:\document.txt'
$FieldName = 'document'
$ContentType = 'text/plain'

$FileStream = [System.IO.FileStream]::new($filePath, [System.IO.FileMode]::Open)
$FileHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new('form-data')
$FileHeader.Name = $FieldName
$FileHeader.FileName = Split-Path -leaf $FilePath
$FileContent = [System.Net.Http.StreamContent]::new($FileStream)
$FileContent.Headers.ContentDisposition = $FileHeader
$FileContent.Headers.ContentType = [System.Net.Http.Headers.MediaTypeHeaderValue]::Parse($ContentType)

$MultipartContent = [System.Net.Http.MultipartFormDataContent]::new()
$MultipartContent.Add($FileContent)

$Response = Invoke-WebRequest -Body $MultipartContent -Method 'POST' -Uri 'https://api.contoso.com/upload'
```

### <span data-ttu-id="612ab-148">Пример 6. Упрощенная многокомпонентная или форма-отправка данных</span><span class="sxs-lookup"><span data-stu-id="612ab-148">Example 6: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="612ab-149">Для некоторых API требуется `multipart/form-data` Отправка файлов и смешанного содержимого.</span><span class="sxs-lookup"><span data-stu-id="612ab-149">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="612ab-150">В этом примере демонстрируется обновление профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="612ab-150">This example demonstrates updating a user profile.</span></span>

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-WebRequest -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="612ab-151">Для формы профиля требуются следующие поля: `firstName` , `lastName` , `email` , `avatar` , `birthday` и `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="612ab-151">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="612ab-152">API ожидает, что в поле будет указан образ для профиля пользователя PIC `avatar` .</span><span class="sxs-lookup"><span data-stu-id="612ab-152">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="612ab-153">API также принимает несколько `hobbies` записей, которые должны быть отправлены в одной и той же форме.</span><span class="sxs-lookup"><span data-stu-id="612ab-153">The API also accepts multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="612ab-154">При создании `$Form` хэш-таблицы имена ключей используются в качестве имен полей формы.</span><span class="sxs-lookup"><span data-stu-id="612ab-154">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="612ab-155">По умолчанию значения хэш-таблицы преобразуются в строки.</span><span class="sxs-lookup"><span data-stu-id="612ab-155">By default, the values of the HashTable are converted to strings.</span></span> <span data-ttu-id="612ab-156">Если значение **System. IO. FileInfo** имеется, содержимое файла отправляется.</span><span class="sxs-lookup"><span data-stu-id="612ab-156">If a **System.IO.FileInfo** value is present, the file contents are submitted.</span></span> <span data-ttu-id="612ab-157">Если имеется коллекция, такая как массивы или списки, поле формы отправляется несколько раз.</span><span class="sxs-lookup"><span data-stu-id="612ab-157">If a collection such as arrays or lists are present, the form field is submitted multiple times.</span></span>

<span data-ttu-id="612ab-158">При использовании `Get-Item` в `avatar` ключе `FileInfo` объект задается как значение.</span><span class="sxs-lookup"><span data-stu-id="612ab-158">By using `Get-Item` on the `avatar` key, the `FileInfo` object is set as the value.</span></span> <span data-ttu-id="612ab-159">В результате отправляются данные изображения для `jdoe.png` .</span><span class="sxs-lookup"><span data-stu-id="612ab-159">The result is that the image data for `jdoe.png` is submitted.</span></span>

<span data-ttu-id="612ab-160">Предоставляя список для `hobbies` ключа, `hobbies` поле будет присвоено в отправку один раз для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="612ab-160">By supplying a list to the `hobbies` key, the `hobbies` field is present in the submissions once for each list item.</span></span>

### <span data-ttu-id="612ab-161">Пример 7. перехват сообщений без успешности Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="612ab-161">Example 7: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="612ab-162">При `Invoke-WebRequest` обнаружении сообщения HTTP, не являющегося успешным (404, 500 и т. д.), оно не возвращает выходные данные и вызывает ошибку, которая завершается.</span><span class="sxs-lookup"><span data-stu-id="612ab-162">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="612ab-163">Чтобы перехватить ошибку и просмотреть **StatusCode** , можно заключить выполнение в `try/catch` блок.</span><span class="sxs-lookup"><span data-stu-id="612ab-163">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
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

<span data-ttu-id="612ab-164">Команда вызывает метод `Invoke-WebRequest` с **ErrorAction** **остановки** , который заставляет `Invoke-WebRequest` вызывать завершающую ошибку при любых неудачных запросах.</span><span class="sxs-lookup"><span data-stu-id="612ab-164">The command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="612ab-165">Завершающая ошибка перехвачена `catch` блоком, который извлекает **StatusCode** из объекта **исключения** .</span><span class="sxs-lookup"><span data-stu-id="612ab-165">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="612ab-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="612ab-166">PARAMETERS</span></span>

### <span data-ttu-id="612ab-167">-Алловуненкриптедаусентикатион</span><span class="sxs-lookup"><span data-stu-id="612ab-167">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="612ab-168">Разрешает отправку учетных данных и секретов через незашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="612ab-168">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="612ab-169">По умолчанию предоставление **учетных данных** или любого варианта **проверки подлинности** с **URI** , который не начинается с, `https://` приводит к ошибке и запрос прерывается, чтобы предотвратить непреднамеренное взаимодействие секретов в виде обычного текста с помощью незашифрованных соединений.</span><span class="sxs-lookup"><span data-stu-id="612ab-169">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` results in an error and the request is aborted to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="612ab-170">Чтобы переопределить это поведение на свой риск, укажите параметр **алловуненкриптедаусентикатион** .</span><span class="sxs-lookup"><span data-stu-id="612ab-170">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="612ab-171">Использование этого параметра не является безопасным и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="612ab-171">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="612ab-172">Он предоставляется только для обеспечения совместимости с устаревшими системами, которые не могут предоставлять зашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="612ab-172">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="612ab-173">Используйте свой собственный риск.</span><span class="sxs-lookup"><span data-stu-id="612ab-173">Use at your own risk.</span></span>

<span data-ttu-id="612ab-174">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-174">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="612ab-175">-Authentication</span><span class="sxs-lookup"><span data-stu-id="612ab-175">-Authentication</span></span>

<span data-ttu-id="612ab-176">Указывает тип явной проверки подлинности, используемый для запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-176">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="612ab-177">Значение по умолчанию — **None** .</span><span class="sxs-lookup"><span data-stu-id="612ab-177">The default is **None** .</span></span>
<span data-ttu-id="612ab-178">**Проверку подлинности** нельзя использовать с **уседефаулткредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="612ab-178">**Authentication** cannot be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="612ab-179">Доступные варианты проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="612ab-179">Available Authentication Options:</span></span>

- <span data-ttu-id="612ab-180">**Нет** . Этот параметр используется по умолчанию, если не указана **Проверка подлинности** . явная проверка подлинности не используется.</span><span class="sxs-lookup"><span data-stu-id="612ab-180">**None** : This is the default option when **Authentication** isn't supplied; no explicit authentication is used.</span></span>
- <span data-ttu-id="612ab-181">**Базовый** : требуются **учетные данные** .</span><span class="sxs-lookup"><span data-stu-id="612ab-181">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="612ab-182">Учетные данные отправляются в заголовке обычной проверки подлинности RFC 7617 в формате `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="612ab-182">The credentials are sent in an RFC 7617 Basic Authentication header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="612ab-183">**Bearer** : требуется **токен** .</span><span class="sxs-lookup"><span data-stu-id="612ab-183">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="612ab-184">Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера.</span><span class="sxs-lookup"><span data-stu-id="612ab-184">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="612ab-185">Это псевдоним для **OAuth**</span><span class="sxs-lookup"><span data-stu-id="612ab-185">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="612ab-186">**OAuth** : требуется **токен** .</span><span class="sxs-lookup"><span data-stu-id="612ab-186">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="612ab-187">Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера.</span><span class="sxs-lookup"><span data-stu-id="612ab-187">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="612ab-188">Это псевдоним для **носителя**</span><span class="sxs-lookup"><span data-stu-id="612ab-188">This is an alias for **Bearer**</span></span>

<span data-ttu-id="612ab-189">При указании **проверки подлинности** переопределяются все `Authorization` заголовки, предоставленные **заголовкам** или добавленные в **сеансе** .</span><span class="sxs-lookup"><span data-stu-id="612ab-189">Supplying **Authentication** overrides any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="612ab-190">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-190">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-191">-Body</span><span class="sxs-lookup"><span data-stu-id="612ab-191">-Body</span></span>

<span data-ttu-id="612ab-192">Задает основной текст запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-192">Specifies the body of the request.</span></span> <span data-ttu-id="612ab-193">Основной текст — это содержимое запроса, идущее после заголовков.</span><span class="sxs-lookup"><span data-stu-id="612ab-193">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="612ab-194">Можно также передать значение текста по конвейеру в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="612ab-194">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="612ab-195">Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.</span><span class="sxs-lookup"><span data-stu-id="612ab-195">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="612ab-196">Если входные данные являются запросом GET, а тело является `IDictionary` (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-196">When the input is a GET request and the body is an `IDictionary` (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="612ab-197">Для других типов запросов (например, POST) текст задается как значение текста запроса в стандартном `name=value` формате.</span><span class="sxs-lookup"><span data-stu-id="612ab-197">For other request types (such as POST), the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="612ab-198">Параметр **Body** может также принимать `System.Net.Http.MultipartFormDataContent` объект.</span><span class="sxs-lookup"><span data-stu-id="612ab-198">The **Body** parameter may also accept a `System.Net.Http.MultipartFormDataContent` object.</span></span> <span data-ttu-id="612ab-199">Это упрощает `multipart/form-data` запросы.</span><span class="sxs-lookup"><span data-stu-id="612ab-199">This facilitates `multipart/form-data` requests.</span></span> <span data-ttu-id="612ab-200">Когда для **тела** передается объект **мултипартформдатаконтент** , все заголовки содержимого, относящиеся к параметрам **ContentType** , **headers** или **Session** , переопределяются заголовками содержимого объекта **мултипартформдатаконтент** .</span><span class="sxs-lookup"><span data-stu-id="612ab-200">When a **MultipartFormDataContent** object is supplied for **Body** , any Content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters is overridden by the Content headers of the **MultipartFormDataContent** object.</span></span> <span data-ttu-id="612ab-201">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-201">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="612ab-202">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="612ab-202">-Certificate</span></span>

<span data-ttu-id="612ab-203">Указывает сертификат клиента, используемый для безопасного веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-203">Specifies the client certificate that's used for a secure web request.</span></span> <span data-ttu-id="612ab-204">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="612ab-204">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="612ab-205">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске Certificate ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="612ab-205">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="612ab-206">Если сертификат недействителен или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="612ab-206">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="612ab-207">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="612ab-207">-CertificateThumbprint</span></span>

<span data-ttu-id="612ab-208">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-208">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="612ab-209">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="612ab-209">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="612ab-210">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="612ab-210">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="612ab-211">Они могут сопоставляться только с локальными учетными записями пользователей. они не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="612ab-211">They can be mapped only to local user accounts; they don't work with domain accounts.</span></span>

<span data-ttu-id="612ab-212">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="612ab-212">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="612ab-213">В настоящее время эта функция поддерживается только на платформах ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="612ab-213">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="612ab-214">-ContentType</span><span class="sxs-lookup"><span data-stu-id="612ab-214">-ContentType</span></span>

<span data-ttu-id="612ab-215">Задает тип содержимого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-215">Specifies the content type of the web request.</span></span>

<span data-ttu-id="612ab-216">Если этот параметр пропущен и метод Request имеет значение POST, `Invoke-WebRequest` задает для типа содержимого значение `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="612ab-216">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="612ab-217">В противном случае тип содержимого не указывается в вызове.</span><span class="sxs-lookup"><span data-stu-id="612ab-217">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="612ab-218">**ContentType** переопределяется при предоставлении объекта **мултипартформдатаконтент** для **тела** .</span><span class="sxs-lookup"><span data-stu-id="612ab-218">**ContentType** is overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="612ab-219">-Credential</span><span class="sxs-lookup"><span data-stu-id="612ab-219">-Credential</span></span>

<span data-ttu-id="612ab-220">Указывает учетную запись пользователя, обладающую разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-220">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="612ab-221">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="612ab-221">The default is the current user.</span></span>

<span data-ttu-id="612ab-222">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="612ab-222">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="612ab-223">**Учетные данные** можно использовать отдельно или в сочетании с определенными параметрами **проверки подлинности** .</span><span class="sxs-lookup"><span data-stu-id="612ab-223">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="612ab-224">При отдельном использовании он предоставляет учетные данные только удаленному серверу, если удаленный сервер отправляет запрос на проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="612ab-224">When used alone, it only supplies credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="612ab-225">При использовании с параметрами **проверки подлинности** учетные данные явно отправляются.</span><span class="sxs-lookup"><span data-stu-id="612ab-225">When used with **Authentication** options, the credentials are explicitly sent.</span></span>

<span data-ttu-id="612ab-226">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="612ab-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="612ab-227">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="612ab-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-228">-Кустоммесод</span><span class="sxs-lookup"><span data-stu-id="612ab-228">-CustomMethod</span></span>

<span data-ttu-id="612ab-229">Указывает пользовательский метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-229">Specifies a custom method used for the web request.</span></span> <span data-ttu-id="612ab-230">Это можно использовать, если метод запроса, требуемый конечной точкой, не является доступным для **метода** .</span><span class="sxs-lookup"><span data-stu-id="612ab-230">This can be used if the Request Method required by the endpoint isn't an available option on the **Method** .</span></span> <span data-ttu-id="612ab-231">**Методы** и **кустоммесод** нельзя использовать вместе.</span><span class="sxs-lookup"><span data-stu-id="612ab-231">**Method** and **CustomMethod** can't be used together.</span></span>

<span data-ttu-id="612ab-232">Этот пример выполняет `TEST` http-запрос к API:</span><span class="sxs-lookup"><span data-stu-id="612ab-232">This example makes a `TEST` HTTP request to the API:</span></span>

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="612ab-233">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-233">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethod, CustomMethodNoProxy
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-234">-Дисаблекипаливе</span><span class="sxs-lookup"><span data-stu-id="612ab-234">-DisableKeepAlive</span></span>

<span data-ttu-id="612ab-235">Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение **false** .</span><span class="sxs-lookup"><span data-stu-id="612ab-235">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False** .</span></span> <span data-ttu-id="612ab-236">По умолчанию **KeepAlive** имеет **значение true** .</span><span class="sxs-lookup"><span data-stu-id="612ab-236">By default, **KeepAlive** is **True** .</span></span> <span data-ttu-id="612ab-237">**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="612ab-237">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="612ab-238">-Форма</span><span class="sxs-lookup"><span data-stu-id="612ab-238">-Form</span></span>

<span data-ttu-id="612ab-239">Преобразует словарь в `multipart/form-data` отправку.</span><span class="sxs-lookup"><span data-stu-id="612ab-239">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="612ab-240">**Форма** не может использоваться с **телом** .</span><span class="sxs-lookup"><span data-stu-id="612ab-240">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="612ab-241">Если используется **ContentType** , он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="612ab-241">If **ContentType** is used, it's ignored.</span></span>

<span data-ttu-id="612ab-242">Ключи словаря используются в качестве имен полей формы.</span><span class="sxs-lookup"><span data-stu-id="612ab-242">The keys of the dictionary are used as the form field names.</span></span> <span data-ttu-id="612ab-243">По умолчанию значения формы преобразуются в строковые значения.</span><span class="sxs-lookup"><span data-stu-id="612ab-243">By default, form values are converted to string values.</span></span>

<span data-ttu-id="612ab-244">Если значение является объектом **System. IO. FileInfo** , то передаются содержимое двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-244">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="612ab-245">Имя файла отправляется как свойство **filename** .</span><span class="sxs-lookup"><span data-stu-id="612ab-245">The name of the file is submitted as the **filename** property.</span></span> <span data-ttu-id="612ab-246">Тип MIME задан как `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="612ab-246">The MIME type is set as `application/octet-stream`.</span></span> <span data-ttu-id="612ab-247">`Get-Item` можно использовать для упрощения предоставления объекта **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="612ab-247">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="612ab-248">Если значение является типом коллекции, такими массивами или списками, поле for отправляется несколько раз.</span><span class="sxs-lookup"><span data-stu-id="612ab-248">If the value is a collection type, such Arrays or Lists, the for field are submitted multiple times.</span></span>
<span data-ttu-id="612ab-249">Значения списка по умолчанию обрабатываются как строки.</span><span class="sxs-lookup"><span data-stu-id="612ab-249">The values of the list are treated as strings by default.</span></span> <span data-ttu-id="612ab-250">Если значение является объектом **System. IO. FileInfo** , то передаются содержимое двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-250">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="612ab-251">Вложенные коллекции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="612ab-251">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="612ab-252">В приведенном выше примере `tags` поле указано в форме три раза, по одному разу для каждого из `Vacation` , `Italy` и `2017` .</span><span class="sxs-lookup"><span data-stu-id="612ab-252">In the above example the `tags` field are supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="612ab-253">`pictures`Поле также отправляется один раз для каждого файла в `2017-Italy` папке.</span><span class="sxs-lookup"><span data-stu-id="612ab-253">The `pictures` field is also submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="612ab-254">Двоичное содержимое файлов в этой папке отправляется в виде значений.</span><span class="sxs-lookup"><span data-stu-id="612ab-254">The binary contents of the files in that folder are submitted as the values.</span></span>

<span data-ttu-id="612ab-255">Эта функция была добавлена в PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-255">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="612ab-256">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="612ab-256">-Headers</span></span>

<span data-ttu-id="612ab-257">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-257">Specifies the headers of the web request.</span></span> <span data-ttu-id="612ab-258">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="612ab-258">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="612ab-259">Чтобы задать заголовки UserAgent, используйте параметр **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="612ab-259">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="612ab-260">Этот параметр нельзя использовать для указания заголовков **User-Agent** и cookie.</span><span class="sxs-lookup"><span data-stu-id="612ab-260">You can't use this parameter to specify **User-Agent** or cookie headers.</span></span>

<span data-ttu-id="612ab-261">Заголовки, связанные с содержимым, такие как, `Content-Type` переопределяются при предоставлении объекта **Мултипартформдатаконтент** для **тела** .</span><span class="sxs-lookup"><span data-stu-id="612ab-261">Content related headers, such as `Content-Type` is overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

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

### <span data-ttu-id="612ab-262">-Файл</span><span class="sxs-lookup"><span data-stu-id="612ab-262">-InFile</span></span>

<span data-ttu-id="612ab-263">Получает содержимое веб-запроса из файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-263">Gets the content of the web request from a file.</span></span> <span data-ttu-id="612ab-264">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-264">Enter a path and file name.</span></span> <span data-ttu-id="612ab-265">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="612ab-265">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="612ab-266">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="612ab-266">-MaximumRedirection</span></span>

<span data-ttu-id="612ab-267">Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="612ab-267">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="612ab-268">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="612ab-268">The default value is 5.</span></span> <span data-ttu-id="612ab-269">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="612ab-269">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-270">-Максимумретрикаунт</span><span class="sxs-lookup"><span data-stu-id="612ab-270">-MaximumRetryCount</span></span>

<span data-ttu-id="612ab-271">Указывает, сколько раз PowerShell повторяет попытку подключения при получении кода ошибки между 400 и 599, включительно или 304.</span><span class="sxs-lookup"><span data-stu-id="612ab-271">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="612ab-272">См. также параметр **ретринтервалсек** для указания числа повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="612ab-272">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="612ab-273">-Method</span><span class="sxs-lookup"><span data-stu-id="612ab-273">-Method</span></span>

<span data-ttu-id="612ab-274">Задает метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-274">Specifies the method used for the web request.</span></span> <span data-ttu-id="612ab-275">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="612ab-275">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="612ab-276">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="612ab-276">Default</span></span>
- <span data-ttu-id="612ab-277">DELETE</span><span class="sxs-lookup"><span data-stu-id="612ab-277">Delete</span></span>
- <span data-ttu-id="612ab-278">Получить</span><span class="sxs-lookup"><span data-stu-id="612ab-278">Get</span></span>
- <span data-ttu-id="612ab-279">Head</span><span class="sxs-lookup"><span data-stu-id="612ab-279">Head</span></span>
- <span data-ttu-id="612ab-280">Объединить</span><span class="sxs-lookup"><span data-stu-id="612ab-280">Merge</span></span>
- <span data-ttu-id="612ab-281">Параметры</span><span class="sxs-lookup"><span data-stu-id="612ab-281">Options</span></span>
- <span data-ttu-id="612ab-282">Обновление</span><span class="sxs-lookup"><span data-stu-id="612ab-282">Patch</span></span>
- <span data-ttu-id="612ab-283">Опубликовать</span><span class="sxs-lookup"><span data-stu-id="612ab-283">Post</span></span>
- <span data-ttu-id="612ab-284">Put</span><span class="sxs-lookup"><span data-stu-id="612ab-284">Put</span></span>
- <span data-ttu-id="612ab-285">Трассировка</span><span class="sxs-lookup"><span data-stu-id="612ab-285">Trace</span></span>

<span data-ttu-id="612ab-286">Параметр **кустоммесод** можно использовать для методов запроса, не перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="612ab-286">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-287">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="612ab-287">-NoProxy</span></span>

<span data-ttu-id="612ab-288">Указывает, что командлет не должен использовать прокси-сервер для достижения места назначения.</span><span class="sxs-lookup"><span data-stu-id="612ab-288">Indicates that the cmdlet shouldn't use a proxy to reach the destination.</span></span> <span data-ttu-id="612ab-289">Если необходимо обойти прокси-сервер, настроенный в среде, используйте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="612ab-289">When you need to bypass the proxy configured in the environment, use this switch.</span></span> <span data-ttu-id="612ab-290">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-290">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-291">-Файл</span><span class="sxs-lookup"><span data-stu-id="612ab-291">-OutFile</span></span>

<span data-ttu-id="612ab-292">Указывает выходной файл, для которого этот командлет сохраняет текст ответа.</span><span class="sxs-lookup"><span data-stu-id="612ab-292">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="612ab-293">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-293">Enter a path and file name.</span></span>
<span data-ttu-id="612ab-294">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="612ab-294">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="612ab-295">Имя рассматривается как литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="612ab-295">The name is treated as a literal path.</span></span>
<span data-ttu-id="612ab-296">Имена, содержащие квадратные скобки ( `[]` ), должны быть заключены в одинарные кавычки ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="612ab-296">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="612ab-297">По умолчанию `Invoke-WebRequest` возвращает результаты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="612ab-297">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="612ab-298">Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru** .</span><span class="sxs-lookup"><span data-stu-id="612ab-298">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="612ab-299">-PassThru</span><span class="sxs-lookup"><span data-stu-id="612ab-299">-PassThru</span></span>

<span data-ttu-id="612ab-300">Указывает, что командлет возвращает результаты в дополнение к записи в файл.</span><span class="sxs-lookup"><span data-stu-id="612ab-300">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="612ab-301">Этот параметр активен, если в команде также используется параметр **OutFile** .</span><span class="sxs-lookup"><span data-stu-id="612ab-301">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="612ab-302">-Пресервеаусоризатиононредирект</span><span class="sxs-lookup"><span data-stu-id="612ab-302">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="612ab-303">Указывает, что командлет должен сохранить `Authorization` заголовок (при его наличии) в перенаправлениях.</span><span class="sxs-lookup"><span data-stu-id="612ab-303">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="612ab-304">По умолчанию этот командлет отделяет `Authorization` заголовок перед перенаправлением.</span><span class="sxs-lookup"><span data-stu-id="612ab-304">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="612ab-305">Указание этого параметра отключает эту логику в случаях, когда заголовок необходимо отправить в расположение перенаправления.</span><span class="sxs-lookup"><span data-stu-id="612ab-305">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="612ab-306">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-306">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="612ab-307">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="612ab-307">-Proxy</span></span>

<span data-ttu-id="612ab-308">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="612ab-308">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>
<span data-ttu-id="612ab-309">Введите URI сетевого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="612ab-309">Enter the URI of a network proxy server.</span></span>

```yaml
Type: System.Uri
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-310">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="612ab-310">-ProxyCredential</span></span>

<span data-ttu-id="612ab-311">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="612ab-311">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="612ab-312">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="612ab-312">The default is the current user.</span></span>

<span data-ttu-id="612ab-313">Введите имя пользователя, например **User01** или **Domain01\User01** , **User@Domain.Com** или введите `PSCredential` объект, например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="612ab-313">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="612ab-314">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="612ab-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="612ab-315">В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="612ab-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-316">-Проксюседефаулткредентиалс</span><span class="sxs-lookup"><span data-stu-id="612ab-316">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="612ab-317">Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.</span><span class="sxs-lookup"><span data-stu-id="612ab-317">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="612ab-318">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="612ab-318">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="612ab-319">В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="612ab-319">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-320">-Resume</span><span class="sxs-lookup"><span data-stu-id="612ab-320">-Resume</span></span>

<span data-ttu-id="612ab-321">Выполняет наиболее эффективную попытку возобновить загрузку частичного файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-321">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="612ab-322">Для **возобновления** требуется **файл** .</span><span class="sxs-lookup"><span data-stu-id="612ab-322">**Resume** requires **OutFile** .</span></span>

<span data-ttu-id="612ab-323">**Resume** работает только с размером локального файла и удаленного файла и не выполняет никаких других проверок того, что локальный файл и удаленный файл одинаковы.</span><span class="sxs-lookup"><span data-stu-id="612ab-323">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="612ab-324">Если размер локального файла меньше, чем размер удаленного файла, командлет попытается возобновить загрузку файла и добавить оставшиеся байты в конец файла.</span><span class="sxs-lookup"><span data-stu-id="612ab-324">If the local file size is smaller than the remote file size, then the cmdlet attempts to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="612ab-325">Если размер локального файла совпадает с размером удаленного файла, никакие действия не выполняются и командлет предполагает, что скачивание уже завершено.</span><span class="sxs-lookup"><span data-stu-id="612ab-325">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already complete.</span></span>

<span data-ttu-id="612ab-326">Если размер локального файла превышает размер удаленного файла, то локальный файл перезаписывается, а весь удаленный файл загружается повторно.</span><span class="sxs-lookup"><span data-stu-id="612ab-326">If the local file size is larger than the remote file size, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="612ab-327">Это поведение аналогично использованию **файла** без **возобновления** .</span><span class="sxs-lookup"><span data-stu-id="612ab-327">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="612ab-328">Если удаленный сервер не поддерживает возобновление загрузки, то локальный файл перезаписывается, а весь удаленный файл повторно загружается.</span><span class="sxs-lookup"><span data-stu-id="612ab-328">If the remote server does not support download resuming, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="612ab-329">Это поведение аналогично использованию **файла** без **возобновления** .</span><span class="sxs-lookup"><span data-stu-id="612ab-329">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="612ab-330">Если локальный файл не существует, то создается локальный файл и загружается весь удаленный файл.</span><span class="sxs-lookup"><span data-stu-id="612ab-330">If the local file does not exist, then the local file is created and the entire remote file is downloaded.</span></span> <span data-ttu-id="612ab-331">Это поведение аналогично использованию **файла** без **возобновления** .</span><span class="sxs-lookup"><span data-stu-id="612ab-331">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="612ab-332">Эта функция была добавлена в PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-332">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="612ab-333">-Ретринтервалсек</span><span class="sxs-lookup"><span data-stu-id="612ab-333">-RetryIntervalSec</span></span>

<span data-ttu-id="612ab-334">Указывает интервал между повторными попытками соединения при получении кода ошибки между 400 и 599, включительно или 304.</span><span class="sxs-lookup"><span data-stu-id="612ab-334">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="612ab-335">См. также параметр **максимумретрикаунт** для указания числа повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="612ab-335">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="612ab-336">-Сессионвариабле</span><span class="sxs-lookup"><span data-stu-id="612ab-336">-SessionVariable</span></span>

<span data-ttu-id="612ab-337">Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.</span><span class="sxs-lookup"><span data-stu-id="612ab-337">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="612ab-338">Введите имя переменной без символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="612ab-338">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="612ab-339">При указании переменной сеанса `Invoke-WebRequest` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="612ab-339">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="612ab-340">Переменную в сеансе можно использовать сразу после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="612ab-340">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="612ab-341">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="612ab-341">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="612ab-342">Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="612ab-342">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="612ab-343">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="612ab-343">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="612ab-344">Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="612ab-344">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="612ab-345">При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-345">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="612ab-346">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** .</span><span class="sxs-lookup"><span data-stu-id="612ab-346">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="612ab-347">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-347">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="612ab-348">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="612ab-348">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="612ab-349">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="612ab-349">-SkipCertificateCheck</span></span>

<span data-ttu-id="612ab-350">Пропускает проверку сертификатов.</span><span class="sxs-lookup"><span data-stu-id="612ab-350">Skips certificate validation checks.</span></span> <span data-ttu-id="612ab-351">Сюда входят все проверки, такие как срок действия, отзыв, доверенный корневой центр и т. д.</span><span class="sxs-lookup"><span data-stu-id="612ab-351">This includes all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="612ab-352">Использование этого параметра не является безопасным и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="612ab-352">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="612ab-353">Этот параметр предназначен только для использования с известными узлами с использованием самозаверяющего сертификата для тестирования.</span><span class="sxs-lookup"><span data-stu-id="612ab-353">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="612ab-354">Используйте свой собственный риск.</span><span class="sxs-lookup"><span data-stu-id="612ab-354">Use at your own risk.</span></span>

<span data-ttu-id="612ab-355">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-355">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="612ab-356">-Скифеадервалидатион</span><span class="sxs-lookup"><span data-stu-id="612ab-356">-SkipHeaderValidation</span></span>

<span data-ttu-id="612ab-357">Указывает, что командлет должен добавить в запрос заголовки без проверки.</span><span class="sxs-lookup"><span data-stu-id="612ab-357">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="612ab-358">Этот параметр следует использовать для сайтов, которым требуются значения заголовка, не соответствующие стандартам.</span><span class="sxs-lookup"><span data-stu-id="612ab-358">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="612ab-359">Указание этого параметра отключает проверку, чтобы разрешить передачу значения без проверки.</span><span class="sxs-lookup"><span data-stu-id="612ab-359">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="612ab-360">Если указано, все заголовки добавляются без проверки.</span><span class="sxs-lookup"><span data-stu-id="612ab-360">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="612ab-361">Этот параметр отключает проверку значений, передаваемых в параметры **ContentType** , **headers** и **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="612ab-361">This switch disables validation for values passed to the **ContentType** , **Headers** and **UserAgent** parameters.</span></span>

<span data-ttu-id="612ab-362">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="612ab-362">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="612ab-363">-Скифттперрорчекк</span><span class="sxs-lookup"><span data-stu-id="612ab-363">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="612ab-364">Этот параметр приводит к тому, что командлет игнорирует состояния ошибок HTTP и продолжает обрабатывать ответы.</span><span class="sxs-lookup"><span data-stu-id="612ab-364">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="612ab-365">Ответы об ошибках записываются в конвейер точно так же, как если бы они были успешными.</span><span class="sxs-lookup"><span data-stu-id="612ab-365">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="612ab-366">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="612ab-366">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-367">-Сслпротокол</span><span class="sxs-lookup"><span data-stu-id="612ab-367">-SslProtocol</span></span>

<span data-ttu-id="612ab-368">Задает протоколы SSL/TLS, допустимые для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-368">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="612ab-369">По умолчанию разрешены все протоколы SSL и TLS, поддерживаемые системой.</span><span class="sxs-lookup"><span data-stu-id="612ab-369">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="612ab-370">**Сслпротокол** позволяет ограничить конкретные протоколы в целях обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="612ab-370">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="612ab-371">**Сслпротокол** использует перечисление флага **вебсслпротокол** .</span><span class="sxs-lookup"><span data-stu-id="612ab-371">**SslProtocol** uses the **WebSslProtocol** Flag Enum.</span></span> <span data-ttu-id="612ab-372">Можно указать несколько протоколов, используя нотацию флагов или объединив несколько параметров **вебсслпротокол** с **бор** , однако предоставление нескольких протоколов не поддерживается на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="612ab-372">It is possible to supply more than one protocol using flag notation or combining multiple **WebSslProtocol** options with **bor** , however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="612ab-373">На платформах, отличных от Windows, невозможно предоставить `Tls` или `Tls12` как вариант.</span><span class="sxs-lookup"><span data-stu-id="612ab-373">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="612ab-374">Поддержка `Tls13` недоступна во всех операционных системах и должна проверяться отдельно для каждой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="612ab-374">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="612ab-375">Эта функция была добавлена в PowerShell 6.0.0, а поддержка `Tls13` добавлена в powershell 7,1.</span><span class="sxs-lookup"><span data-stu-id="612ab-375">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-376">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="612ab-376">-TimeoutSec</span></span>

<span data-ttu-id="612ab-377">Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="612ab-377">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="612ab-378">Значение по умолчанию, равное 0, указывает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="612ab-378">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="612ab-379">Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.</span><span class="sxs-lookup"><span data-stu-id="612ab-379">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-380">-Token</span><span class="sxs-lookup"><span data-stu-id="612ab-380">-Token</span></span>

<span data-ttu-id="612ab-381">Токен OAuth или носитель для включения в запрос.</span><span class="sxs-lookup"><span data-stu-id="612ab-381">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="612ab-382">Для некоторых параметров **проверки подлинности** требуется **токен** .</span><span class="sxs-lookup"><span data-stu-id="612ab-382">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="612ab-383">Его нельзя использовать независимо.</span><span class="sxs-lookup"><span data-stu-id="612ab-383">It cannot be used independently.</span></span>

<span data-ttu-id="612ab-384">**Токен** принимает значение, `SecureString` содержащее токен.</span><span class="sxs-lookup"><span data-stu-id="612ab-384">**Token** takes a `SecureString` containing the token.</span></span> <span data-ttu-id="612ab-385">Для предоставления маркера вручную используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="612ab-385">To supply the token manually use the following:</span></span>

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="612ab-386">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="612ab-386">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="612ab-387">-Трансференкодинг</span><span class="sxs-lookup"><span data-stu-id="612ab-387">-TransferEncoding</span></span>

<span data-ttu-id="612ab-388">Задает значение для заголовка transfer-encoding ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="612ab-388">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="612ab-389">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="612ab-389">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="612ab-390">Chunked</span><span class="sxs-lookup"><span data-stu-id="612ab-390">Chunked</span></span>
- <span data-ttu-id="612ab-391">Сжать</span><span class="sxs-lookup"><span data-stu-id="612ab-391">Compress</span></span>
- <span data-ttu-id="612ab-392">Deflate</span><span class="sxs-lookup"><span data-stu-id="612ab-392">Deflate</span></span>
- <span data-ttu-id="612ab-393">GZip</span><span class="sxs-lookup"><span data-stu-id="612ab-393">GZip</span></span>
- <span data-ttu-id="612ab-394">Идентификация</span><span class="sxs-lookup"><span data-stu-id="612ab-394">Identity</span></span>

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

### <span data-ttu-id="612ab-395">— URI</span><span class="sxs-lookup"><span data-stu-id="612ab-395">-Uri</span></span>

<span data-ttu-id="612ab-396">Указывает универсальный код ресурса (URI) Интернет-ресурса, в который отправляется веб-запрос.</span><span class="sxs-lookup"><span data-stu-id="612ab-396">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="612ab-397">Введите URI.</span><span class="sxs-lookup"><span data-stu-id="612ab-397">Enter a URI.</span></span> <span data-ttu-id="612ab-398">Этот параметр поддерживает только протоколы HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="612ab-398">This parameter supports HTTP or HTTPS only.</span></span>

<span data-ttu-id="612ab-399">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="612ab-399">This parameter is required.</span></span> <span data-ttu-id="612ab-400">**URI** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="612ab-400">The parameter name **Uri** is optional.</span></span>

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

### <span data-ttu-id="612ab-401">-Усебасикпарсинг</span><span class="sxs-lookup"><span data-stu-id="612ab-401">-UseBasicParsing</span></span>

<span data-ttu-id="612ab-402">Этот параметр является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="612ab-402">This parameter has been deprecated.</span></span> <span data-ttu-id="612ab-403">Начиная с PowerShell 6.0.0, все веб-запросы используют только базовый анализ.</span><span class="sxs-lookup"><span data-stu-id="612ab-403">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="612ab-404">Этот параметр включен только для обеспечения обратной совместимости, и его использование не влияет на работу командлета.</span><span class="sxs-lookup"><span data-stu-id="612ab-404">This parameter is included for backwards compatibility only and any use of it has no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="612ab-405">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="612ab-405">-UseDefaultCredentials</span></span>

<span data-ttu-id="612ab-406">Указывает, что командлет использует учетные данные текущего пользователя для отправки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-406">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="612ab-407">Это не может использоваться с **проверкой подлинности** или **учетными данными** и может не поддерживаться на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="612ab-407">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="612ab-408">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="612ab-408">-UserAgent</span></span>

<span data-ttu-id="612ab-409">Указывает строку агента пользователя для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-409">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="612ab-410">Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` небольшому варианту для каждой операционной системы и платформы.</span><span class="sxs-lookup"><span data-stu-id="612ab-410">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="612ab-411">Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari.</span><span class="sxs-lookup"><span data-stu-id="612ab-411">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

<span data-ttu-id="612ab-412">Например, следующая команда использует строку агента пользователя для Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="612ab-412">For example, the following command uses the user agent string for Internet Explorer:</span></span>

```powershell
Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)
```

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

### <span data-ttu-id="612ab-413">-Семинар</span><span class="sxs-lookup"><span data-stu-id="612ab-413">-WebSession</span></span>

<span data-ttu-id="612ab-414">Указывает сеанс веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-414">Specifies a web request session.</span></span> <span data-ttu-id="612ab-415">Введите имя переменной, включая знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="612ab-415">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="612ab-416">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** .</span><span class="sxs-lookup"><span data-stu-id="612ab-416">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="612ab-417">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="612ab-417">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="612ab-418">Заголовки, связанные с содержимым, такие как `Content-Type` , также переопределяются при предоставлении объекта **Мултипартформдатаконтент** для **тела** .</span><span class="sxs-lookup"><span data-stu-id="612ab-418">Content related headers, such as `Content-Type`, are also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="612ab-419">В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="612ab-419">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="612ab-420">Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="612ab-420">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="612ab-421">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="612ab-421">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="612ab-422">Чтобы создать сеанс веб-запроса, введите имя переменной без знака доллара в значении параметра **сессионвариабле** `Invoke-WebRequest` команды.</span><span class="sxs-lookup"><span data-stu-id="612ab-422">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="612ab-423">`Invoke-WebRequest` создает сеанс и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="612ab-423">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="612ab-424">В последующих командах используйте переменную в качестве значения параметра **WebSession** .</span><span class="sxs-lookup"><span data-stu-id="612ab-424">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="612ab-425">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="612ab-425">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="612ab-426">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="612ab-426">CommonParameters</span></span>

<span data-ttu-id="612ab-427">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="612ab-427">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="612ab-428">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="612ab-428">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="612ab-429">Входные данные</span><span class="sxs-lookup"><span data-stu-id="612ab-429">INPUTS</span></span>

### <span data-ttu-id="612ab-430">System.Object</span><span class="sxs-lookup"><span data-stu-id="612ab-430">System.Object</span></span>

<span data-ttu-id="612ab-431">Текст веб-запроса можно передать в `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="612ab-431">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="612ab-432">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="612ab-432">OUTPUTS</span></span>

### <span data-ttu-id="612ab-433">Microsoft. PowerShell. Commands. Басичтмлвебреспонсеобжект</span><span class="sxs-lookup"><span data-stu-id="612ab-433">Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject</span></span>

## <span data-ttu-id="612ab-434">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="612ab-434">NOTES</span></span>

<span data-ttu-id="612ab-435">Начиная с PowerShell 6.0.0 `Invoke-WebRequest` поддерживает только базовый анализ.</span><span class="sxs-lookup"><span data-stu-id="612ab-435">Beginning with PowerShell 6.0.0 `Invoke-WebRequest` supports basic parsing only.</span></span>

<span data-ttu-id="612ab-436">Дополнительные сведения см. в разделе [басичтмлвебреспонсеобжект](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span><span class="sxs-lookup"><span data-stu-id="612ab-436">For more information, see [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span></span>

<span data-ttu-id="612ab-437">В связи с изменениями в .NET Core 3,1, PowerShell 7,0 и более поздних версий использует свойство [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) для определения конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="612ab-437">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="612ab-438">Значение этого свойства определяется вашей платформой:</span><span class="sxs-lookup"><span data-stu-id="612ab-438">The value of this property is determined by your platform:</span></span>

- <span data-ttu-id="612ab-439">**Для Windows** : считывает конфигурацию прокси-сервера из переменных среды.</span><span class="sxs-lookup"><span data-stu-id="612ab-439">**For Windows** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="612ab-440">Если эти переменные не определены, свойство является производным от параметров прокси пользователя.</span><span class="sxs-lookup"><span data-stu-id="612ab-440">If those variables are not defined the property is derived from the user's proxy settings.</span></span>
- <span data-ttu-id="612ab-441">**Для macOS** : считывает конфигурацию прокси-сервера из переменных среды.</span><span class="sxs-lookup"><span data-stu-id="612ab-441">**For macOS** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="612ab-442">Если эти переменные не определены, свойство является производным от параметров прокси-сервера системы.</span><span class="sxs-lookup"><span data-stu-id="612ab-442">If those variables are not defined the property is derived from the system's proxy settings.</span></span>
- <span data-ttu-id="612ab-443">**Для Linux** : считывает конфигурацию прокси-сервера из переменных среды.</span><span class="sxs-lookup"><span data-stu-id="612ab-443">**For Linux** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="612ab-444">Если эти переменные не определены, свойство инициализирует ненастроенный экземпляр, который обходит все адреса.</span><span class="sxs-lookup"><span data-stu-id="612ab-444">If those variables are not defined the property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="612ab-445">Переменные среды, используемые для `DefaultProxy` инициализации платформ на платформе Windows и UNIX:</span><span class="sxs-lookup"><span data-stu-id="612ab-445">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="612ab-446">` HTTP_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в HTTP-запросах.</span><span class="sxs-lookup"><span data-stu-id="612ab-446">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="612ab-447">`HTTPS_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в запросах HTTPS.</span><span class="sxs-lookup"><span data-stu-id="612ab-447">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="612ab-448">`ALL_PROXY`: имя узла или IP-адрес прокси-сервера, используемого для запросов HTTP и HTTPS в случае `HTTP_PROXY` или `HTTPS_PROXY` , не определен.</span><span class="sxs-lookup"><span data-stu-id="612ab-448">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="612ab-449">`NO_PROXY`: список имен узлов с разделителями-запятыми, которые следует исключить из прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="612ab-449">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="612ab-450">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="612ab-450">RELATED LINKS</span></span>

[<span data-ttu-id="612ab-451">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="612ab-451">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="612ab-452">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="612ab-452">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="612ab-453">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="612ab-453">ConvertTo-Json</span></span>](ConvertTo-Json.md)
