---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 91cd2dda912d6e79177e8a961012a1604d9460ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601878"
---
# <span data-ttu-id="2eb0f-102">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="2eb0f-102">Invoke-RestMethod</span></span>

## <span data-ttu-id="2eb0f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2eb0f-103">SYNOPSIS</span></span>
<span data-ttu-id="2eb0f-104">Отправляет запрос HTTP или HTTPS в веб-службу RESTful.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-104">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="2eb0f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2eb0f-105">SYNTAX</span></span>

### <span data-ttu-id="2eb0f-106">Стандардмесод (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2eb0f-106">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2eb0f-107">стандардмесоднопрокси</span><span class="sxs-lookup"><span data-stu-id="2eb0f-107">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2eb0f-108">кустоммесоднопрокси</span><span class="sxs-lookup"><span data-stu-id="2eb0f-108">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="2eb0f-109">кустоммесод</span><span class="sxs-lookup"><span data-stu-id="2eb0f-109">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="2eb0f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2eb0f-110">Description</span></span>

<span data-ttu-id="2eb0f-111">`Invoke-RestMethod`Командлет отправляет запросы HTTP и HTTPS к веб-службам, которые возвращают структурированные данные.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-111">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="2eb0f-112">PowerShell форматирует ответ на основе типа данных.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-112">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="2eb0f-113">Для канала RSS или ATOM PowerShell возвращает XML-узлы элемента или записи.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-113">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="2eb0f-114">Для нотация объектов JavaScript (JSON) или XML, PowerShell преобразует или десериализует содержимое в объекты.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-114">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="2eb0f-115">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="2eb0f-116">Начиная с PowerShell 7,0, `Invoke-RestMethod` поддерживает настройку прокси-сервера, определяемую переменными среды.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-116">Beginning in PowerShell 7.0, `Invoke-RestMethod` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="2eb0f-117">См. раздел " [Примечания](#notes) " этой статьи.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-117">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="2eb0f-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="2eb0f-118">EXAMPLES</span></span>

### <span data-ttu-id="2eb0f-119">Пример 1. Получение RSS-канала PowerShell</span><span class="sxs-lookup"><span data-stu-id="2eb0f-119">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="2eb0f-120">В этом примере `Invoke-RestMethod` командлет используется для получения сведений из RSS-канала блога в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-120">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="2eb0f-121">Команда использует `Format-Table` командлет для вывода значений свойств **Title** и **pubDate** каждого блога в таблице.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-121">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

```powershell
Invoke-RestMethod -Uri https://blogs.msdn.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

### <span data-ttu-id="2eb0f-122">Пример 2. выполнение запроса POST</span><span class="sxs-lookup"><span data-stu-id="2eb0f-122">Example 2: Run a POST request</span></span>

<span data-ttu-id="2eb0f-123">В этом примере пользователь выполняет `Invoke-RestMethod` запрос POST на веб-сайте интрасети в организации пользователя.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-123">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential
$Url = "https://server.contoso.com:8089/services/search/jobs/export"
$Body = @{
    search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}
Invoke-RestMethod -Method 'Post' -Uri $url -Credential $Cred -Body $body -OutFile output.csv
```

<span data-ttu-id="2eb0f-124">Учетные данные запрашиваются, а затем сохраняются в, `$Cred` а URL-адрес, к которому будет осуществляться доступ, определяется в `$Url` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-124">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="2eb0f-125">`$Body`Переменная описывает критерии поиска, указывает CSV в качестве режима вывода и задает период времени для возвращаемых данных, которые запускаются два дня назад и завершаются один день назад.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-125">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="2eb0f-126">Переменная Body задает значения параметров, которые применяются к конкретному REST API, с которым `Invoke-RestMethod` устанавливается связь.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-126">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="2eb0f-127">`Invoke-RestMethod`Команда выполняется со всеми переменными на месте, указывая путь и имя файла для результирующего выходного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-127">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="2eb0f-128">Пример 3. следование ссылкам на связи</span><span class="sxs-lookup"><span data-stu-id="2eb0f-128">Example 3: Follow relation links</span></span>

<span data-ttu-id="2eb0f-129">Некоторые интерфейсы API-интерфейса поддерживают разбиение на страницы по ссылкам связи на [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-129">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="2eb0f-130">Вместо того чтобы анализировать заголовок для получения URL-адреса для следующей страницы, можно воспользоваться командлетом.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-130">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="2eb0f-131">Этот пример возвращает первые две страницы проблем из репозитория GitHub в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-131">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="2eb0f-132">Пример 4. Упрощенная передача данных в составе или форме</span><span class="sxs-lookup"><span data-stu-id="2eb0f-132">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="2eb0f-133">Для некоторых API требуется `multipart/form-data` Отправка файлов и смешанного содержимого.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-133">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="2eb0f-134">В этом примере показано, как обновить профиль пользователя.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-134">This example demonstrates how to update a user's profile.</span></span>

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
$Result = Invoke-RestMethod -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="2eb0f-135">Для формы профиля требуются следующие поля: `firstName` , `lastName` , `email` , `avatar` , `birthday` и `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-135">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="2eb0f-136">API ожидает, что в поле будет указан образ для профиля пользователя PIC `avatar` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-136">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="2eb0f-137">API также будет принимать несколько `hobbies` записей для отправки в одну и ту же форму.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-137">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="2eb0f-138">При создании `$Form` хэш-таблицы имена ключей используются в качестве имен полей формы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-138">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="2eb0f-139">По умолчанию значения хэш-таблицы будут преобразованы в строки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-139">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="2eb0f-140">Если указано `System.IO.FileInfo` значение, содержимое файла будет отправлено.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-140">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="2eb0f-141">Если имеется коллекция, такая как массивы или списки, поле формы будет отправляться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-141">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="2eb0f-142">При использовании `Get-Item` в `avatar` ключе `FileInfo` объект будет задан как значение.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-142">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="2eb0f-143">В результате будут отправлены данные изображения для `jdoe.png` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-143">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="2eb0f-144">Предоставляя список для `hobbies` ключа, `hobbies` поле будет присутствовать в отправку один раз для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-144">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="2eb0f-145">Пример 5. Передача нескольких заголовков</span><span class="sxs-lookup"><span data-stu-id="2eb0f-145">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="2eb0f-146">Для проверки подлинности или проверки интерфейсам API часто требуются переданные заголовки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-146">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="2eb0f-147">В этом примере показано, как передать несколько заголовков из `hash-table` в REST API.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-147">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="2eb0f-148">Параметры</span><span class="sxs-lookup"><span data-stu-id="2eb0f-148">Parameters</span></span>

### <span data-ttu-id="2eb0f-149">-Алловуненкриптедаусентикатион</span><span class="sxs-lookup"><span data-stu-id="2eb0f-149">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="2eb0f-150">Разрешает отправку учетных данных и секретов через незашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-150">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="2eb0f-151">По умолчанию предоставление **учетных данных** или любого варианта **проверки подлинности** с **URI** , который не начинается с, `https://` приведет к ошибке и запрос будет прерван, чтобы предотвратить непреднамеренное взаимодействие секретов в виде обычного текста с помощью незашифрованных соединений.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-151">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="2eb0f-152">Чтобы переопределить это поведение на свой риск, укажите параметр **алловуненкриптедаусентикатион** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-152">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="2eb0f-153">Использование этого параметра не является безопасным и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-153">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="2eb0f-154">Он предоставляется только для обеспечения совместимости с устаревшими системами, которые не могут предоставлять зашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-154">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="2eb0f-155">Используйте свой собственный риск.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-155">Use at your own risk.</span></span>

<span data-ttu-id="2eb0f-156">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-156">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-157">-Authentication</span><span class="sxs-lookup"><span data-stu-id="2eb0f-157">-Authentication</span></span>

<span data-ttu-id="2eb0f-158">Указывает тип явной проверки подлинности, используемый для запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-158">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="2eb0f-159">Значение по умолчанию — **None**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-159">The default is **None**.</span></span>
<span data-ttu-id="2eb0f-160">**Проверку подлинности** нельзя использовать с **уседефаулткредентиалс**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-160">**Authentication** can't be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="2eb0f-161">Доступные варианты проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="2eb0f-161">Available Authentication Options:</span></span>

- <span data-ttu-id="2eb0f-162">**Нет**. Этот параметр используется по умолчанию, если не указана **Проверка подлинности** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-162">**None**: This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="2eb0f-163">Явная проверка подлинности не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-163">No explicit authentication will be used.</span></span>
- <span data-ttu-id="2eb0f-164">**Базовый**: требуются **учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-164">**Basic**: Requires **Credential**.</span></span> <span data-ttu-id="2eb0f-165">Учетные данные будут использоваться для отправки заголовка обычной проверки подлинности RFC 7617 `Authorization: Basic` в формате `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-165">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="2eb0f-166">**Bearer**: требуется **токен**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-166">**Bearer**: Requires **Token**.</span></span> <span data-ttu-id="2eb0f-167">Будет отсылать и `Authorization: Bearer` заголовку RFC 6750 с помощью заданного маркера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-167">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="2eb0f-168">Это псевдоним для **OAuth**</span><span class="sxs-lookup"><span data-stu-id="2eb0f-168">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="2eb0f-169">**OAuth**: требуется **токен**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-169">**OAuth**: Requires **Token**.</span></span> <span data-ttu-id="2eb0f-170">Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-170">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="2eb0f-171">Это псевдоним для **носителя**</span><span class="sxs-lookup"><span data-stu-id="2eb0f-171">This is an alias for **Bearer**</span></span>

<span data-ttu-id="2eb0f-172">При предоставлении **проверки подлинности** все заголовки, заданные `Authorization` для **заголовков** или входящие в состав **сеанса**, переопределяются.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-172">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="2eb0f-173">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-173">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-174">-Body</span><span class="sxs-lookup"><span data-stu-id="2eb0f-174">-Body</span></span>

<span data-ttu-id="2eb0f-175">Задает основной текст запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-175">Specifies the body of the request.</span></span> <span data-ttu-id="2eb0f-176">Основной текст — это содержимое запроса, идущее после заголовков.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-176">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="2eb0f-177">Можно также передать значение текста по конвейеру в `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-177">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="2eb0f-178">Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-178">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="2eb0f-179">Если входные данные являются запросом GET, а тело является `IDictionary` (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-179">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="2eb0f-180">Для других типов запросов (таких как POST) основной текст задается как значение основного текста запроса в стандартном формате имя=значение.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-180">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="2eb0f-181">Если текст является формой или выходными данными другого `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-181">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="2eb0f-182">Параметр **Body** может также принимать объект **System .NET. http. мултипартформдатаконтент** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-182">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="2eb0f-183">Это упростит `multipart/form-data` запросы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-183">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="2eb0f-184">Когда для **тела** передается объект **мултипартформдатаконтент** , все заголовки содержимого, связанные с параметрами **ContentType**, **headers** или для **сеанса** , будут переопределены заголовками содержимого `MultipartFormDataContent` объекта.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-184">When a **MultipartFormDataContent** object is supplied for **Body**, any content related headers supplied to the **ContentType**, **Headers**, or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="2eb0f-185">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-185">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-186">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="2eb0f-186">-Certificate</span></span>

<span data-ttu-id="2eb0f-187">Задает сертификат клиента, который используется для выполнения защищенного веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-187">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="2eb0f-188">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-188">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="2eb0f-189">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске Certificate ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-189">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="2eb0f-190">Если сертификат недействителен или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-190">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="2eb0f-191">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="2eb0f-191">-CertificateThumbprint</span></span>

<span data-ttu-id="2eb0f-192">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-192">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="2eb0f-193">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-193">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="2eb0f-194">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-194">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="2eb0f-195">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-195">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="2eb0f-196">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-196">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="2eb0f-197">В настоящее время эта функция поддерживается только на платформах ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-197">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="2eb0f-198">-ContentType</span><span class="sxs-lookup"><span data-stu-id="2eb0f-198">-ContentType</span></span>

<span data-ttu-id="2eb0f-199">Задает тип содержимого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-199">Specifies the content type of the web request.</span></span>

<span data-ttu-id="2eb0f-200">Если этот параметр пропущен и метод Request имеет значение POST, `Invoke-RestMethod` задает для типа содержимого значение `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-200">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="2eb0f-201">В противном случае тип содержимого не указывается в вызове.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-201">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="2eb0f-202">**ContentType** будет переопределен при `MultipartFormDataContent` предоставлении объекта для **тела**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-202">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="2eb0f-203">-Credential</span><span class="sxs-lookup"><span data-stu-id="2eb0f-203">-Credential</span></span>

<span data-ttu-id="2eb0f-204">Указывает учетную запись пользователя, обладающую разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-204">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="2eb0f-205">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-205">The default is the current user.</span></span>

<span data-ttu-id="2eb0f-206">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-206">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="2eb0f-207">**Учетные данные** можно использовать отдельно или в сочетании с определенными параметрами **проверки подлинности** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-207">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="2eb0f-208">Если удаленный сервер отправляет запрос на проверку подлинности, то он будет предоставлять учетные данные только удаленному серверу.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-208">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="2eb0f-209">При использовании с параметрами **проверки подлинности** учетные данные будут явно отправлены.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-209">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="2eb0f-210">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-210">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2eb0f-211">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-211">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2eb0f-212">-Кустоммесод</span><span class="sxs-lookup"><span data-stu-id="2eb0f-212">-CustomMethod</span></span>

<span data-ttu-id="2eb0f-213">Указывает пользовательский метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-213">Specifies custom method used for the web request.</span></span> <span data-ttu-id="2eb0f-214">Его можно использовать с методом Request, необходимым для конечной точки, который не является доступным для **метода**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-214">This can be used with the Request Method required by the endpoint is not an available option on the **Method**.</span></span> <span data-ttu-id="2eb0f-215">**Методы** и **кустоммесод** не могут использоваться вместе.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-215">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="2eb0f-216">Пример.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-216">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="2eb0f-217">Это делает `TEST` http-запрос к API.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-217">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="2eb0f-218">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-218">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-219">-Дисаблекипаливе</span><span class="sxs-lookup"><span data-stu-id="2eb0f-219">-DisableKeepAlive</span></span>

<span data-ttu-id="2eb0f-220">Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение false.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-220">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="2eb0f-221">По умолчанию **KeepAlive** имеет значение True.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-221">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="2eb0f-222">**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-222">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="2eb0f-223">-Фолловреллинк</span><span class="sxs-lookup"><span data-stu-id="2eb0f-223">-FollowRelLink</span></span>

<span data-ttu-id="2eb0f-224">Указывает, что командлет должен следовать ссылкам связи.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-224">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="2eb0f-225">Некоторые интерфейсы API-интерфейса поддерживают разбиение на страницы по ссылкам связи на [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-225">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="2eb0f-226">Вместо того чтобы анализировать заголовок для получения URL-адреса для следующей страницы, можно воспользоваться командлетом.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-226">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="2eb0f-227">Чтобы задать, сколько раз следует следовать ссылкам связи, используйте параметр **максимумфолловреллинк** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-227">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="2eb0f-228">При использовании этого параметра командлет возвращает коллекцию страниц результатов.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-228">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="2eb0f-229">Каждая страница результатов может содержать несколько результирующих элементов.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-229">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="2eb0f-230">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-230">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-231">-Форма</span><span class="sxs-lookup"><span data-stu-id="2eb0f-231">-Form</span></span>

<span data-ttu-id="2eb0f-232">Преобразует словарь в `multipart/form-data` отправку.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-232">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="2eb0f-233">**Форма** не может использоваться с **телом**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-233">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="2eb0f-234">Значение, если **ContentType** будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-234">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="2eb0f-235">Ключи словаря будут использоваться в качестве имен полей формы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-235">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="2eb0f-236">По умолчанию значения форм будут преобразованы в строковые значения.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-236">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="2eb0f-237">Если значение является объектом **System. IO. FileInfo** , будет отправлено содержимое двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-237">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="2eb0f-238">Имя файла будет отправлено как `filename` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-238">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="2eb0f-239">MIME будет установлен в значение `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-239">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="2eb0f-240">`Get-Item` можно использовать для упрощения предоставления объекта **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-240">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="2eb0f-241">Если значение является типом коллекции, например массивом или списком, поле for будет отправляться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-241">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="2eb0f-242">Значения списка будут рассматриваться как строки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-242">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="2eb0f-243">Если значение является объектом **System. IO. FileInfo** , будет отправлено содержимое двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-243">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="2eb0f-244">Вложенные коллекции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-244">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="2eb0f-245">В приведенном выше примере `tags` поле будет представлено в форме три раза, по одному разу для каждого из `Vacation` , `Italy` и `2017` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-245">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="2eb0f-246">`pictures`Поле также будет отправлено один раз для каждого файла в `2017-Italy` папке.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-246">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="2eb0f-247">Двоичное содержимое файлов в этой папке будет отправлено как значения.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-247">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="2eb0f-248">Эта функция была добавлена в PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-248">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="2eb0f-249">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="2eb0f-249">-Headers</span></span>

<span data-ttu-id="2eb0f-250">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-250">Specifies the headers of the web request.</span></span> <span data-ttu-id="2eb0f-251">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-251">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="2eb0f-252">Чтобы задать заголовки UserAgent, используйте параметр **UserAgent**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-252">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="2eb0f-253">Этот параметр нельзя использовать для указания `User-Agent` заголовков или файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-253">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="2eb0f-254">Заголовки, связанные с содержимым, такие как, `Content-Type` будут переопределены при `MultipartFormDataContent` предоставлении объекта для **тела**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-254">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="2eb0f-255">-Файл</span><span class="sxs-lookup"><span data-stu-id="2eb0f-255">-InFile</span></span>

<span data-ttu-id="2eb0f-256">Получает содержимое веб-запроса из файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-256">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="2eb0f-257">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-257">Enter a path and file name.</span></span> <span data-ttu-id="2eb0f-258">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-258">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="2eb0f-259">-Максимумфолловреллинк</span><span class="sxs-lookup"><span data-stu-id="2eb0f-259">-MaximumFollowRelLink</span></span>

<span data-ttu-id="2eb0f-260">Указывает, сколько раз следует следовать ссылкам связи, если используется **фолловреллинк** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-260">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="2eb0f-261">Значение меньшего размера может потребоваться, если при регулировании API-интерфейса используется слишком много запросов.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-261">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="2eb0f-262">Значение по умолчанию — `[Int32]::MaxValue`.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-262">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="2eb0f-263">Значение 0 (ноль) предотвращает следующие ссылки связи.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-263">A value of 0 (zero) prevents following relation links.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: Int32.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-264">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="2eb0f-264">-MaximumRedirection</span></span>

<span data-ttu-id="2eb0f-265">Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-265">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="2eb0f-266">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-266">The default value is 5.</span></span> <span data-ttu-id="2eb0f-267">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-267">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="2eb0f-268">-Максимумретрикаунт</span><span class="sxs-lookup"><span data-stu-id="2eb0f-268">-MaximumRetryCount</span></span>

<span data-ttu-id="2eb0f-269">Указывает, сколько раз PowerShell повторяет попытку подключения при получении кода ошибки между 400 и 599, включительно или 304.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-269">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="2eb0f-270">См. также параметр **ретринтервалсек** для указания числа повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-270">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="2eb0f-271">-Method</span><span class="sxs-lookup"><span data-stu-id="2eb0f-271">-Method</span></span>

<span data-ttu-id="2eb0f-272">Задает метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-272">Specifies the method used for the web request.</span></span> <span data-ttu-id="2eb0f-273">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2eb0f-273">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2eb0f-274">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="2eb0f-274">Default</span></span>
- <span data-ttu-id="2eb0f-275">DELETE</span><span class="sxs-lookup"><span data-stu-id="2eb0f-275">Delete</span></span>
- <span data-ttu-id="2eb0f-276">Получить</span><span class="sxs-lookup"><span data-stu-id="2eb0f-276">Get</span></span>
- <span data-ttu-id="2eb0f-277">Head</span><span class="sxs-lookup"><span data-stu-id="2eb0f-277">Head</span></span>
- <span data-ttu-id="2eb0f-278">Объединение</span><span class="sxs-lookup"><span data-stu-id="2eb0f-278">Merge</span></span>
- <span data-ttu-id="2eb0f-279">Параметры</span><span class="sxs-lookup"><span data-stu-id="2eb0f-279">Options</span></span>
- <span data-ttu-id="2eb0f-280">Обновление</span><span class="sxs-lookup"><span data-stu-id="2eb0f-280">Patch</span></span>
- <span data-ttu-id="2eb0f-281">Опубликовать</span><span class="sxs-lookup"><span data-stu-id="2eb0f-281">Post</span></span>
- <span data-ttu-id="2eb0f-282">Put</span><span class="sxs-lookup"><span data-stu-id="2eb0f-282">Put</span></span>
- <span data-ttu-id="2eb0f-283">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2eb0f-283">Trace</span></span>

<span data-ttu-id="2eb0f-284">Параметр **кустоммесод** можно использовать для методов запроса, не перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-284">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="2eb0f-285">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="2eb0f-285">-NoProxy</span></span>

<span data-ttu-id="2eb0f-286">Указывает, что командлет не будет использовать прокси-сервер для доступа к назначению.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-286">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="2eb0f-287">Если необходимо обойти прокси-сервер, настроенный в Internet Explorer, или прокси-сервер, указанный в окружении, используйте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-287">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="2eb0f-288">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-288">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="2eb0f-289">-Файл</span><span class="sxs-lookup"><span data-stu-id="2eb0f-289">-OutFile</span></span>

<span data-ttu-id="2eb0f-290">Сохраняет основной текст ответа в указанный выходной файл.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-290">Saves the response body in the specified output file.</span></span> <span data-ttu-id="2eb0f-291">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-291">Enter a path and file name.</span></span> <span data-ttu-id="2eb0f-292">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-292">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="2eb0f-293">Имя рассматривается как литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-293">The name is treated as a literal path.</span></span> <span data-ttu-id="2eb0f-294">Имена, содержащие квадратные скобки ( `[]` ), должны быть заключены в одинарные кавычки ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-294">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="2eb0f-295">По умолчанию `Invoke-RestMethod` возвращает результаты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-295">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="2eb0f-296">Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-296">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="2eb0f-297">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2eb0f-297">-PassThru</span></span>

<span data-ttu-id="2eb0f-298">Возвращает результаты в дополнение к их записи в файл.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-298">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="2eb0f-299">Этот параметр активен, если в команде также используется параметр **OutFile**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-299">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-300">-Пресервеаусоризатиононредирект</span><span class="sxs-lookup"><span data-stu-id="2eb0f-300">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="2eb0f-301">Указывает, что командлет должен сохранить `Authorization` заголовок (при его наличии) в перенаправлениях.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-301">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="2eb0f-302">По умолчанию этот командлет отделяет `Authorization` заголовок перед перенаправлением.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-302">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="2eb0f-303">Указание этого параметра отключает эту логику в случаях, когда заголовок необходимо отправить в расположение перенаправления.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-303">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="2eb0f-304">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-304">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-305">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="2eb0f-305">-Proxy</span></span>

<span data-ttu-id="2eb0f-306">Использует прокси-сервер для запроса вместо прямого подключения к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-306">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="2eb0f-307">Введите универсальный код ресурса (URI) сетевого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-307">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="2eb0f-308">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-308">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-309">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2eb0f-309">-ProxyCredential</span></span>

<span data-ttu-id="2eb0f-310">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-310">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="2eb0f-311">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-311">The default is the current user.</span></span>

<span data-ttu-id="2eb0f-312">Введите имя пользователя, например **User01** или **Domain01\User01**, **User@Domain.Com** или введите `PSCredential` объект, например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-312">Type a user name, such as **User01** or **Domain01\User01**, **User@Domain.Com**, or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="2eb0f-313">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-313">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="2eb0f-314">В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-314">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-315">-Проксюседефаулткредентиалс</span><span class="sxs-lookup"><span data-stu-id="2eb0f-315">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="2eb0f-316">Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-316">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="2eb0f-317">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-317">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="2eb0f-318">В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-318">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="2eb0f-319">-Респонсехеадерсвариабле</span><span class="sxs-lookup"><span data-stu-id="2eb0f-319">-ResponseHeadersVariable</span></span>

<span data-ttu-id="2eb0f-320">Создает словарь заголовков ответов и сохраняет его в значении указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-320">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="2eb0f-321">Ключи словаря будут содержать имена полей заголовка ответа, возвращаемого веб-сервером, а значения будут соответствующими значениями полей.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-321">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="2eb0f-322">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-322">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RHV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-323">-Resume</span><span class="sxs-lookup"><span data-stu-id="2eb0f-323">-Resume</span></span>

<span data-ttu-id="2eb0f-324">Выполняет наиболее эффективную попытку возобновить загрузку частичного файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-324">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="2eb0f-325">Для параметра **Resume** требуется параметр **файла** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-325">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="2eb0f-326">**Resume** работает только с размером локального файла и удаленного файла и не выполняет никаких других проверок того, что локальный файл и удаленный файл одинаковы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-326">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="2eb0f-327">Если размер локального файла меньше, чем размер удаленного файла, командлет попытается возобновить загрузку файла и дополнит добавление оставшихся байтов в конец файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-327">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="2eb0f-328">Если размер локального файла совпадает с размером удаленного файла, никакие действия не выполняются и командлет предполагает, что скачивание уже завершено.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-328">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="2eb0f-329">Если размер локального файла превышает размер удаленного файла, то локальный файл будет перезаписан, а весь удаленный файл будет полностью повторно скачан.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-329">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="2eb0f-330">Это поведение аналогично использованию **файла** без **возобновления**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-330">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="2eb0f-331">Если удаленный сервер не поддерживает возобновление загрузки, локальный файл будет перезаписан, а весь удаленный файл будет полностью повторно скачан.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-331">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="2eb0f-332">Это поведение аналогично использованию **файла** без **возобновления**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-332">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="2eb0f-333">Если локальный файл не существует, то будет создан локальный файл, а весь удаленный файл будет полностью скачан.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-333">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="2eb0f-334">Это поведение аналогично использованию **файла** без **возобновления**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-334">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="2eb0f-335">Эта функция была добавлена в PowerShell 6.1.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-335">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="2eb0f-336">-Ретринтервалсек</span><span class="sxs-lookup"><span data-stu-id="2eb0f-336">-RetryIntervalSec</span></span>

<span data-ttu-id="2eb0f-337">Указывает интервал между повторными попытками соединения при получении кода ошибки между 400 и 599, включительно или 304.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-337">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="2eb0f-338">См. также параметр **максимумретрикаунт** для указания числа повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-338">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="2eb0f-339">-Сессионвариабле</span><span class="sxs-lookup"><span data-stu-id="2eb0f-339">-SessionVariable</span></span>

<span data-ttu-id="2eb0f-340">Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-340">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="2eb0f-341">Введите имя переменной без символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-341">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="2eb0f-342">При указании переменной сеанса `Invoke-RestMethod` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-342">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="2eb0f-343">Переменную в сеансе можно использовать сразу после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-343">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="2eb0f-344">В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-344">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="2eb0f-345">Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-345">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="2eb0f-346">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-346">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="2eb0f-347">Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-347">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="2eb0f-348">При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-348">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="2eb0f-349">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-349">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="2eb0f-350">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-350">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="2eb0f-351">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-351">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="2eb0f-352">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="2eb0f-352">-SkipCertificateCheck</span></span>

<span data-ttu-id="2eb0f-353">Пропускает проверки сертификатов, включающие все проверки, такие как срок действия, отзыв, доверенный корневой центр и т. д.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-353">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="2eb0f-354">Использование этого параметра не является безопасным и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-354">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="2eb0f-355">Этот параметр предназначен только для использования с известными узлами с использованием самозаверяющего сертификата для тестирования.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-355">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="2eb0f-356">Используйте свой собственный риск.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-356">Use at your own risk.</span></span>

<span data-ttu-id="2eb0f-357">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-357">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-358">-Скифеадервалидатион</span><span class="sxs-lookup"><span data-stu-id="2eb0f-358">-SkipHeaderValidation</span></span>

<span data-ttu-id="2eb0f-359">Указывает, что командлет должен добавить в запрос заголовки без проверки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-359">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="2eb0f-360">Этот параметр следует использовать для сайтов, которым требуются значения заголовка, не соответствующие стандартам.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-360">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="2eb0f-361">Указание этого параметра отключает проверку, чтобы разрешить передачу значения без проверки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-361">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="2eb0f-362">Если указано, все заголовки добавляются без проверки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-362">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="2eb0f-363">Это приведет к отключению проверки значений, передаваемых в параметры **ContentType**, **headers** и **UserAgent** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-363">This will disable validation for values passed to the **ContentType**, **Headers**, and **UserAgent** parameters.</span></span>

<span data-ttu-id="2eb0f-364">Эта функция была добавлена в PowerShell 6.0.0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-364">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="2eb0f-365">-Скифттперрорчекк</span><span class="sxs-lookup"><span data-stu-id="2eb0f-365">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="2eb0f-366">Этот параметр приводит к тому, что командлет игнорирует состояния ошибок HTTP и продолжает обрабатывать ответы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-366">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="2eb0f-367">Ответы об ошибках записываются в конвейер точно так же, как если бы они были успешными.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-367">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="2eb0f-368">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-368">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="2eb0f-369">-Сслпротокол</span><span class="sxs-lookup"><span data-stu-id="2eb0f-369">-SslProtocol</span></span>

<span data-ttu-id="2eb0f-370">Задает протоколы SSL/TLS, допустимые для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-370">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="2eb0f-371">По умолчанию разрешены все протоколы SSL и TLS, поддерживаемые системой.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-371">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="2eb0f-372">**Сслпротокол** позволяет ограничить конкретные протоколы в целях обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-372">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="2eb0f-373">**Сслпротокол** использует `WebSslProtocol` флаг Enum.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-373">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="2eb0f-374">Можно указать несколько протоколов, используя нотацию флага или объединив несколько `WebSslProtocol` параметров с `-bor` , однако предоставление нескольких протоколов не поддерживается на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-374">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="2eb0f-375">На платформах, отличных от Windows, невозможно предоставить `Tls` или `Tls12` как вариант.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-375">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="2eb0f-376">Поддержка `Tls13` недоступна во всех операционных системах и должна проверяться отдельно для каждой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-376">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="2eb0f-377">Эта функция была добавлена в PowerShell 6.0.0, а поддержка `Tls13` добавлена в powershell 7,1.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-377">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12, Tls13

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-378">-Статускодевариабле</span><span class="sxs-lookup"><span data-stu-id="2eb0f-378">-StatusCodeVariable</span></span>

<span data-ttu-id="2eb0f-379">Этот параметр задает переменную, которой присваивается целочисленное значение кода состояния.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-379">This parameter specifies a variable that's assigned a status code's integer value.</span></span> <span data-ttu-id="2eb0f-380">Параметр может выявление сообщений об успешном завершении или сообщений о сбое при использовании с параметром **скифттперрорчекк** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-380">The parameter can identify success messages or failure messages when used with the **SkipHttpErrorCheck** parameter.</span></span>

<span data-ttu-id="2eb0f-381">Введите имя переменной параметра в виде строки, например `-StatusCodeVariable "scv"` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-381">Input the parameter's variable name as a string such as `-StatusCodeVariable "scv"`.</span></span>

<span data-ttu-id="2eb0f-382">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-382">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0f-383">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="2eb0f-383">-TimeoutSec</span></span>

<span data-ttu-id="2eb0f-384">Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-384">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="2eb0f-385">Значение по умолчанию, равное 0, указывает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-385">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="2eb0f-386">Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-386">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="2eb0f-387">-Token</span><span class="sxs-lookup"><span data-stu-id="2eb0f-387">-Token</span></span>

<span data-ttu-id="2eb0f-388">Токен OAuth или носитель для включения в запрос.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-388">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="2eb0f-389">Для некоторых параметров **проверки подлинности** требуется **токен** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-389">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="2eb0f-390">Его нельзя использовать независимо.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-390">It can't be used independently.</span></span>

<span data-ttu-id="2eb0f-391">**Токен** принимает `SecureString` , который содержит токен.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-391">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="2eb0f-392">Для указания токена вручную используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2eb0f-392">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="2eb0f-393">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-393">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="2eb0f-394">-Трансференкодинг</span><span class="sxs-lookup"><span data-stu-id="2eb0f-394">-TransferEncoding</span></span>

<span data-ttu-id="2eb0f-395">Задает значение для заголовка transfer-encoding ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-395">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="2eb0f-396">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2eb0f-396">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2eb0f-397">Chunked</span><span class="sxs-lookup"><span data-stu-id="2eb0f-397">Chunked</span></span>
- <span data-ttu-id="2eb0f-398">Сжать</span><span class="sxs-lookup"><span data-stu-id="2eb0f-398">Compress</span></span>
- <span data-ttu-id="2eb0f-399">Deflate</span><span class="sxs-lookup"><span data-stu-id="2eb0f-399">Deflate</span></span>
- <span data-ttu-id="2eb0f-400">GZip</span><span class="sxs-lookup"><span data-stu-id="2eb0f-400">GZip</span></span>
- <span data-ttu-id="2eb0f-401">Идентификация</span><span class="sxs-lookup"><span data-stu-id="2eb0f-401">Identity</span></span>

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

### <span data-ttu-id="2eb0f-402">— URI</span><span class="sxs-lookup"><span data-stu-id="2eb0f-402">-Uri</span></span>

<span data-ttu-id="2eb0f-403">Указывает универсальный код ресурса (URI) Интернет-ресурса, в который отправляется веб-запрос.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-403">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="2eb0f-404">Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-404">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="2eb0f-405">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-405">This parameter is required.</span></span> <span data-ttu-id="2eb0f-406">Имя параметра (**URI**) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-406">The parameter name (**Uri**) is optional.</span></span>

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

### <span data-ttu-id="2eb0f-407">-Усебасикпарсинг</span><span class="sxs-lookup"><span data-stu-id="2eb0f-407">-UseBasicParsing</span></span>

<span data-ttu-id="2eb0f-408">Этот параметр является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-408">This parameter has been deprecated.</span></span> <span data-ttu-id="2eb0f-409">Начиная с PowerShell 6.0.0, все веб-запросы используют только базовый анализ.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-409">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="2eb0f-410">Этот параметр включен только для обеспечения обратной совместимости, и его использование не влияет на работу командлета.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-410">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="2eb0f-411">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="2eb0f-411">-UseDefaultCredentials</span></span>

<span data-ttu-id="2eb0f-412">Указывает, что командлет использует учетные данные текущего пользователя для отправки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-412">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="2eb0f-413">Это не может использоваться с **проверкой подлинности** или **учетными данными** и может не поддерживаться на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-413">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="2eb0f-414">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="2eb0f-414">-UserAgent</span></span>

<span data-ttu-id="2eb0f-415">Указывает строку агента пользователя для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-415">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="2eb0f-416">Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` небольшому варианту для каждой операционной системы и платформы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-416">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="2eb0f-417">Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-417">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="2eb0f-418">-Семинар</span><span class="sxs-lookup"><span data-stu-id="2eb0f-418">-WebSession</span></span>

<span data-ttu-id="2eb0f-419">Указывает сеанс веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-419">Specifies a web request session.</span></span> <span data-ttu-id="2eb0f-420">Введите имя переменной, включая знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-420">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="2eb0f-421">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-421">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="2eb0f-422">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-422">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="2eb0f-423">Заголовки, связанные с содержимым, такие как `Content-Type` , также будут переопределены при предоставлении объекта **Мултипартформдатаконтент** для **тела**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-423">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="2eb0f-424">В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-424">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="2eb0f-425">Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-425">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="2eb0f-426">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-426">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="2eb0f-427">Чтобы создать сеанс веб-запроса, введите имя переменной без знака доллара в значении параметра **сессионвариабле** `Invoke-RestMethod` команды.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-427">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="2eb0f-428">`Invoke-RestMethod` создает сеанс и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-428">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="2eb0f-429">В последующих командах используйте переменную в качестве значения параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-429">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="2eb0f-430">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-430">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="2eb0f-431">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2eb0f-431">CommonParameters</span></span>

<span data-ttu-id="2eb0f-432">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-432">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2eb0f-433">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2eb0f-433">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2eb0f-434">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2eb0f-434">INPUTS</span></span>

### <span data-ttu-id="2eb0f-435">System.Object</span><span class="sxs-lookup"><span data-stu-id="2eb0f-435">System.Object</span></span>

<span data-ttu-id="2eb0f-436">Текст веб-запроса можно передать в `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="2eb0f-436">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="2eb0f-437">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2eb0f-437">OUTPUTS</span></span>

### <span data-ttu-id="2eb0f-438">System. Int64, System. String, System.Xml.Xmlдокумент</span><span class="sxs-lookup"><span data-stu-id="2eb0f-438">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="2eb0f-439">Выходные данные командлета зависят от формата получаемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-439">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="2eb0f-440">PSObject</span><span class="sxs-lookup"><span data-stu-id="2eb0f-440">PSObject</span></span>

<span data-ttu-id="2eb0f-441">Если запрос возвращает строки JSON, `Invoke-RestMethod` возвращает **PSObject** , представляющий строки.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-441">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="2eb0f-442">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2eb0f-442">NOTES</span></span>

<span data-ttu-id="2eb0f-443">Некоторые функции могут быть недоступны на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-443">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="2eb0f-444">В связи с изменениями в .NET Core 3,1, PowerShell 7,0 и более поздних версий использует свойство [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) для определения конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-444">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="2eb0f-445">В зависимости от используемой платформы значение этого свойства отличается от правил.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-445">The value of this property is different rules depending on your platform:</span></span>

- <span data-ttu-id="2eb0f-446">**Для Windows**: считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, из параметров прокси пользователя.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-446">**For Windows**: Reads proxy configuration from environment variables or, if those are not defined, from the user's proxy settings.</span></span>
- <span data-ttu-id="2eb0f-447">**Для macOS**: считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, из параметров прокси-сервера системы.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-447">**For macOS**: Reads proxy configuration from environment variables or, if those are not defined, from the system's proxy settings.</span></span>
- <span data-ttu-id="2eb0f-448">**Для Linux**: считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, это свойство инициализирует ненастроенный экземпляр, который обходит все адреса.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-448">**For Linux**: Reads proxy configuration from environment variables or, in case those are not defined, this property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="2eb0f-449">Переменные среды, используемые для `DefaultProxy` инициализации платформ на платформе Windows и UNIX:</span><span class="sxs-lookup"><span data-stu-id="2eb0f-449">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="2eb0f-450">` HTTP_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в HTTP-запросах.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-450">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="2eb0f-451">`HTTPS_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в запросах HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-451">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="2eb0f-452">`ALL_PROXY`: имя узла или IP-адрес прокси-сервера, используемого для запросов HTTP и HTTPS в случае `HTTP_PROXY` или `HTTPS_PROXY` , не определен.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-452">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="2eb0f-453">`NO_PROXY`: список имен узлов с разделителями-запятыми, которые следует исключить из прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2eb0f-453">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="2eb0f-454">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2eb0f-454">RELATED LINKS</span></span>

[<span data-ttu-id="2eb0f-455">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2eb0f-455">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="2eb0f-456">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="2eb0f-456">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="2eb0f-457">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="2eb0f-457">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
