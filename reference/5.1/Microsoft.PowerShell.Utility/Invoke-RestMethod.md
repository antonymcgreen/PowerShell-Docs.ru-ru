---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/13/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: c89f7351e9c874cea2cc0cd5e0912e3ca0d8b0bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227586"
---
# <span data-ttu-id="ba6fe-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="ba6fe-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="ba6fe-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ba6fe-104">Synopsis</span></span>
<span data-ttu-id="ba6fe-105">Отправляет запрос HTTP или HTTPS в веб-службу RESTful.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="ba6fe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba6fe-106">Syntax</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="ba6fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ba6fe-107">Description</span></span>

<span data-ttu-id="ba6fe-108">`Invoke-RestMethod`Командлет отправляет запросы HTTP и HTTPS в веб-службы передачи данных о состоянии представления (RESTful), которые возвращают структурированные данные.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-108">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.</span></span>

<span data-ttu-id="ba6fe-109">Windows PowerShell форматирует ответ в соответствии с типом данных.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-109">Windows PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="ba6fe-110">Для RSS-канала или веб-канала ATOM Windows PowerShell возвращает узлы XML Item или Entry.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-110">For an RSS or ATOM feed, Windows PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="ba6fe-111">Для нотации объектов JavaScript (JSON) или XML Windows PowerShell преобразует (или десериализует) содержимое в объекты.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-111">For JavaScript Object Notation (JSON) or XML, Windows PowerShell converts (or deserializes) the content into objects.</span></span>

<span data-ttu-id="ba6fe-112">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-112">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="ba6fe-113">По умолчанию код сценария на веб-странице может выполняться при синтаксическом анализе страницы для заполнения `ParsedHtml` Свойства.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-113">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="ba6fe-114">Чтобы отключить это, используйте параметр **усебасикпарсинг** .</span><span class="sxs-lookup"><span data-stu-id="ba6fe-114">Use the **UseBasicParsing** switch to suppress this.</span></span>

## <span data-ttu-id="ba6fe-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="ba6fe-115">Examples</span></span>

### <span data-ttu-id="ba6fe-116">Пример 1. Получение RSS-канала PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba6fe-116">Example 1: Get the PowerShell RSS feed</span></span>

```powershell
Invoke-RestMethod -Uri https://devblogs.microsoft.com/powershell/feed/ |
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

<span data-ttu-id="ba6fe-117">Эта команда использует `Invoke-RestMethod` командлет для получения сведений из RSS-канала блога в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-117">This command uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="ba6fe-118">Команда использует `Format-Table` командлет для вывода значений свойств **Title** и **pubDate** каждого блога в таблице.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-118">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

### <span data-ttu-id="ba6fe-119">Пример 2</span><span class="sxs-lookup"><span data-stu-id="ba6fe-119">Example 2</span></span>

<span data-ttu-id="ba6fe-120">В следующем примере пользователь запускается `Invoke-RestMethod` для выполнения запроса POST на веб-сайте интрасети в организации пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-120">In the following example, a user runs `Invoke-RestMethod` to perform a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential

# Next, allow the use of self-signed SSL certificates.

[System.Net.ServicePointManager]::ServerCertificateValidationCallback = { $True }

# Create variables to store the values consumed by the Invoke-RestMethod command.
# The search variable contents are later embedded in the body variable.

$Server = 'server.contoso.com'
$Url = "https://${server}:8089/services/search/jobs/export"
$Search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"

# The cmdlet handles URL encoding. The body variable describes the search criteria, specifies CSV as
# the output mode, and specifies a time period for returned data that starts two days ago and ends
# one day ago. The body variable specifies values for parameters that apply to the particular REST
# API with which Invoke-RestMethod is communicating.

$Body = @{
    search = $Search
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}

# Now, run the Invoke-RestMethod command with all variables in place, specifying a path and file
# name for the resulting CSV output file.

Invoke-RestMethod -Method Post -Uri $url -Credential $Cred -Body $body -OutFile output.csv

{"preview":true,"offset":0,"result":{"sourcetype":"contoso1","count":"9624"}}

{"preview":true,"offset":1,"result":{"sourcetype":"contoso2","count":"152"}}

{"preview":true,"offset":2,"result":{"sourcetype":"contoso3","count":"88494"}}

{"preview":true,"offset":3,"result":{"sourcetype":"contoso4","count":"15277"}}
```

### <span data-ttu-id="ba6fe-121">Пример 3. Передача нескольких заголовков</span><span class="sxs-lookup"><span data-stu-id="ba6fe-121">Example 3: Pass multiple headers</span></span>

<span data-ttu-id="ba6fe-122">В этом примере показано, как передать несколько заголовков из в `hash-table` в REST API.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-122">This example demonstrates, how to pass multiple headers in from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

<span data-ttu-id="ba6fe-123">API часто нуждаются в переданных заголовках для проверки подлинности, проверки и т. д.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-123">APIs often require passed headers for authentication, validation etc.</span></span>

### <span data-ttu-id="ba6fe-124">Пример 3. Отправка данных формы</span><span class="sxs-lookup"><span data-stu-id="ba6fe-124">Example 3: Submitting form data</span></span>

<span data-ttu-id="ba6fe-125">Если тело является формой или является выходным результатом другого `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-125">When the body is a form, or it is the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="ba6fe-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="ba6fe-126">For example:</span></span>

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## <span data-ttu-id="ba6fe-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba6fe-127">Parameters</span></span>

### <span data-ttu-id="ba6fe-128">-Body</span><span class="sxs-lookup"><span data-stu-id="ba6fe-128">-Body</span></span>

<span data-ttu-id="ba6fe-129">Задает основной текст запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-129">Specifies the body of the request.</span></span> <span data-ttu-id="ba6fe-130">Основной текст — это содержимое запроса, идущее после заголовков.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-130">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="ba6fe-131">Можно также передать значение текста по конвейеру в `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="ba6fe-131">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="ba6fe-132">Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-132">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="ba6fe-133">Если входные данные — это запрос GET, а основной текст — IDictionary (обычно это хэш-таблица), основной текст добавляется в URI как параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-133">When the input is a GET request, and the body is an IDictionary (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="ba6fe-134">Для других типов запросов (таких как POST) основной текст задается как значение основного текста запроса в стандартном формате имя=значение.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-134">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

> [!WARNING]
> <span data-ttu-id="ba6fe-135">Подробный вывод тела сообщения POST заканчивается `with -1-byte payload` , даже если размер текста известен и отправляется в `Content-Length` заголовке HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-135">The verbose output of a POST body will end with `with -1-byte payload`, even though the size of the body is both known and sent in the `Content-Length` HTTP header.</span></span>

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

### <span data-ttu-id="ba6fe-136">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="ba6fe-136">-Certificate</span></span>

<span data-ttu-id="ba6fe-137">Задает сертификат клиента, который используется для выполнения защищенного веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-137">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="ba6fe-138">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-138">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="ba6fe-139">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске Certificate ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-139">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="ba6fe-140">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-140">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="ba6fe-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="ba6fe-141">-CertificateThumbprint</span></span>

<span data-ttu-id="ba6fe-142">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-142">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="ba6fe-143">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="ba6fe-144">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="ba6fe-145">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="ba6fe-146">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске Windows PowerShell ( `Cert:` ).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell (`Cert:`) drive.</span></span>

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

### <span data-ttu-id="ba6fe-147">-ContentType</span><span class="sxs-lookup"><span data-stu-id="ba6fe-147">-ContentType</span></span>

<span data-ttu-id="ba6fe-148">Задает тип содержимого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-148">Specifies the content type of the web request.</span></span>

<span data-ttu-id="ba6fe-149">Если этот параметр пропущен, а метод запроса — POST, `Invoke-RestMethod` устанавливает тип содержимого "Application/x-www-Form-UrlEncoded".</span><span class="sxs-lookup"><span data-stu-id="ba6fe-149">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to "application/x-www-form-urlencoded".</span></span> <span data-ttu-id="ba6fe-150">В противном случае тип содержимого в вызове не указывается.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-150">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="ba6fe-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="ba6fe-151">-Credential</span></span>

<span data-ttu-id="ba6fe-152">Указывает учетную запись пользователя, обладающую разрешением для отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-152">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="ba6fe-153">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-153">The default is the current user.</span></span>

<span data-ttu-id="ba6fe-154">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-154">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="ba6fe-155">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-155">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ba6fe-156">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-156">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="ba6fe-157">-Дисаблекипаливе</span><span class="sxs-lookup"><span data-stu-id="ba6fe-157">-DisableKeepAlive</span></span>

<span data-ttu-id="ba6fe-158">Задает значение False для параметра **KeepAlive** в заголовке HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-158">Sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="ba6fe-159">По умолчанию **KeepAlive** имеет значение True.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-159">By default, **KeepAlive** is True.</span></span>
<span data-ttu-id="ba6fe-160">**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-160">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: KeepAlive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba6fe-161">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="ba6fe-161">-Headers</span></span>

<span data-ttu-id="ba6fe-162">Задает заголовки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-162">Specifies the headers of the web request.</span></span> <span data-ttu-id="ba6fe-163">Введите словарь или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-163">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="ba6fe-164">Чтобы задать заголовки UserAgent, используйте параметр **UserAgent**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-164">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="ba6fe-165">Этот параметр нельзя использовать для указания заголовков UserAgent или файла cookie.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-165">You cannot use this parameter to specify UserAgent or cookie headers.</span></span>

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

### <span data-ttu-id="ba6fe-166">-Файл</span><span class="sxs-lookup"><span data-stu-id="ba6fe-166">-InFile</span></span>

<span data-ttu-id="ba6fe-167">Получает содержимое веб-запроса из файла.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-167">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="ba6fe-168">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-168">Enter a path and file name.</span></span> <span data-ttu-id="ba6fe-169">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-169">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="ba6fe-170">-Максимумредиректион</span><span class="sxs-lookup"><span data-stu-id="ba6fe-170">-MaximumRedirection</span></span>

<span data-ttu-id="ba6fe-171">Определяет, сколько раз Windows PowerShell перенаправляет соединение на альтернативный URI перед сбоем подключения.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-171">Determines how many times Windows PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="ba6fe-172">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-172">The default value is 5.</span></span> <span data-ttu-id="ba6fe-173">Значение 0 (ноль) запрещает любые перенаправления.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-173">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="ba6fe-174">-Method</span><span class="sxs-lookup"><span data-stu-id="ba6fe-174">-Method</span></span>

<span data-ttu-id="ba6fe-175">Задает метод, используемый для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-175">Specifies the method used for the web request.</span></span> <span data-ttu-id="ba6fe-176">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="ba6fe-176">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ba6fe-177">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="ba6fe-177">Default</span></span>
- <span data-ttu-id="ba6fe-178">DELETE</span><span class="sxs-lookup"><span data-stu-id="ba6fe-178">Delete</span></span>
- <span data-ttu-id="ba6fe-179">Получить</span><span class="sxs-lookup"><span data-stu-id="ba6fe-179">Get</span></span>
- <span data-ttu-id="ba6fe-180">Head</span><span class="sxs-lookup"><span data-stu-id="ba6fe-180">Head</span></span>
- <span data-ttu-id="ba6fe-181">Объединить</span><span class="sxs-lookup"><span data-stu-id="ba6fe-181">Merge</span></span>
- <span data-ttu-id="ba6fe-182">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba6fe-182">Options</span></span>
- <span data-ttu-id="ba6fe-183">Обновление</span><span class="sxs-lookup"><span data-stu-id="ba6fe-183">Patch</span></span>
- <span data-ttu-id="ba6fe-184">Опубликовать</span><span class="sxs-lookup"><span data-stu-id="ba6fe-184">Post</span></span>
- <span data-ttu-id="ba6fe-185">Put</span><span class="sxs-lookup"><span data-stu-id="ba6fe-185">Put</span></span>
- <span data-ttu-id="ba6fe-186">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ba6fe-186">Trace</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba6fe-187">-Файл</span><span class="sxs-lookup"><span data-stu-id="ba6fe-187">-OutFile</span></span>

<span data-ttu-id="ba6fe-188">Сохраняет основной текст ответа в указанный выходной файл.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-188">Saves the response body in the specified output file.</span></span> <span data-ttu-id="ba6fe-189">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-189">Enter a path and file name.</span></span> <span data-ttu-id="ba6fe-190">Если путь не указан, по умолчанию используется текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-190">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="ba6fe-191">По умолчанию `Invoke-RestMethod` возвращает результаты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-191">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="ba6fe-192">Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-192">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="ba6fe-193">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ba6fe-193">-PassThru</span></span>

<span data-ttu-id="ba6fe-194">Возвращает результаты в дополнение к их записи в файл.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-194">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="ba6fe-195">Этот параметр активен, если в команде также используется параметр **OutFile**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-195">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="ba6fe-196">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="ba6fe-196">-Proxy</span></span>

<span data-ttu-id="ba6fe-197">Использует прокси-сервер для выполнения запроса вместо того, чтобы напрямую подключиться к интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-197">Uses a proxy server for the request, rather than connecting directly to the Internet resource.</span></span> <span data-ttu-id="ba6fe-198">Введите URI сетевого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-198">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="ba6fe-199">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ba6fe-199">-ProxyCredential</span></span>

<span data-ttu-id="ba6fe-200">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-200">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="ba6fe-201">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-201">The default is the current user.</span></span>

<span data-ttu-id="ba6fe-202">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-202">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="ba6fe-203">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-203">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="ba6fe-204">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-204">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="ba6fe-205">-Проксюседефаулткредентиалс</span><span class="sxs-lookup"><span data-stu-id="ba6fe-205">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="ba6fe-206">Использует учетные данные текущего пользователя для доступа к прокси-серверу, который задан параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-206">Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="ba6fe-207">Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-207">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="ba6fe-208">Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-208">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="ba6fe-209">-Сессионвариабле</span><span class="sxs-lookup"><span data-stu-id="ba6fe-209">-SessionVariable</span></span>

<span data-ttu-id="ba6fe-210">Создает сеанс веб-запроса и сохраняет его в значении указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-210">Creates a web request session and saves it in the value of the specified variable.</span></span> <span data-ttu-id="ba6fe-211">Введите имя переменной без символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-211">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="ba6fe-212">При указании переменной сеанса `Invoke-RestMethod` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-212">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="ba6fe-213">Переменную в сеансе можно использовать сразу после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-213">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="ba6fe-214">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-214">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="ba6fe-215">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-215">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="ba6fe-216">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-216">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="ba6fe-217">Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-217">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="ba6fe-218">Windows PowerShell использует данные из объекта сеанса веб-запроса при установке нового подключения.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-218">Windows PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="ba6fe-219">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-219">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="ba6fe-220">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-220">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="ba6fe-221">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="ba6fe-221">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="ba6fe-222">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="ba6fe-222">-TimeoutSec</span></span>

<span data-ttu-id="ba6fe-223">Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-223">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="ba6fe-224">Значение по умолчанию, равное 0, указывает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-224">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="ba6fe-225">Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра TimeoutSec задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-225">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set TimeoutSec to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="ba6fe-226">-Трансференкодинг</span><span class="sxs-lookup"><span data-stu-id="ba6fe-226">-TransferEncoding</span></span>

<span data-ttu-id="ba6fe-227">Задает значение для заголовка transfer-encoding ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-227">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="ba6fe-228">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="ba6fe-228">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ba6fe-229">Chunked</span><span class="sxs-lookup"><span data-stu-id="ba6fe-229">Chunked</span></span>
- <span data-ttu-id="ba6fe-230">Сжать</span><span class="sxs-lookup"><span data-stu-id="ba6fe-230">Compress</span></span>
- <span data-ttu-id="ba6fe-231">Deflate</span><span class="sxs-lookup"><span data-stu-id="ba6fe-231">Deflate</span></span>
- <span data-ttu-id="ba6fe-232">GZip</span><span class="sxs-lookup"><span data-stu-id="ba6fe-232">GZip</span></span>
- <span data-ttu-id="ba6fe-233">Идентификация</span><span class="sxs-lookup"><span data-stu-id="ba6fe-233">Identity</span></span>

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

### <span data-ttu-id="ba6fe-234">— URI</span><span class="sxs-lookup"><span data-stu-id="ba6fe-234">-Uri</span></span>

<span data-ttu-id="ba6fe-235">Указывает URI интернет-ресурса, на который отправляется веб-запрос.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-235">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="ba6fe-236">Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-236">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="ba6fe-237">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-237">This parameter is required.</span></span> <span data-ttu-id="ba6fe-238">Имя параметра ( **URI** ) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-238">The parameter name ( **Uri** ) is optional.</span></span>

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

### <span data-ttu-id="ba6fe-239">-Усебасикпарсинг</span><span class="sxs-lookup"><span data-stu-id="ba6fe-239">-UseBasicParsing</span></span>

<span data-ttu-id="ba6fe-240">Указывает, что командлет использует базовый синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-240">Indicates that the cmdlet uses basic parsing.</span></span> <span data-ttu-id="ba6fe-241">Командлет возвращает необработанный код HTML в **строковом** объекте.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-241">The cmdlet returns the raw HTML in a **String** object.</span></span>

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

### <span data-ttu-id="ba6fe-242">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="ba6fe-242">-UseDefaultCredentials</span></span>

<span data-ttu-id="ba6fe-243">Использует учетные данные текущего пользователя для отправки веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-243">Uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="ba6fe-244">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="ba6fe-244">-UserAgent</span></span>

<span data-ttu-id="ba6fe-245">Указывает строку агента пользователя для веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-245">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="ba6fe-246">По умолчанию агент пользователя аналогичен Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0 с небольшими вариациями для каждой операционной системы и платформы.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-246">The default user agent is similar to "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="ba6fe-247">Чтобы проверить веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands) , такие как Chrome, Firefox, Internet Explorer, Opera и Safari.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-247">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands) class, such as Chrome, FireFox, Internet Explorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="ba6fe-248">-Семинар</span><span class="sxs-lookup"><span data-stu-id="ba6fe-248">-WebSession</span></span>

<span data-ttu-id="ba6fe-249">Указывает сеанс веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-249">Specifies a web request session.</span></span> <span data-ttu-id="ba6fe-250">Введите имя переменной, включая знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-250">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="ba6fe-251">Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-251">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="ba6fe-252">Значения параметров имеют приоритет над значениями в сеансе веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-252">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="ba6fe-253">В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-253">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="ba6fe-254">Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-254">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="ba6fe-255">Его можно использовать для обмена состоянием и данными между веб-запросами.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-255">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="ba6fe-256">Чтобы создать сеанс веб-запроса, введите имя переменной (без знака доллара) в качестве значения параметра **сессионвариабле** `Invoke-RestMethod` команды.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-256">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="ba6fe-257">`Invoke-RestMethod` создает сеанс и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-257">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="ba6fe-258">В последующих командах используйте переменную в качестве значения параметра **WebSession**.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-258">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="ba6fe-259">В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .</span><span class="sxs-lookup"><span data-stu-id="ba6fe-259">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="ba6fe-260">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ba6fe-260">CommonParameters</span></span>

<span data-ttu-id="ba6fe-261">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ba6fe-262">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ba6fe-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ba6fe-263">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ba6fe-263">Inputs</span></span>

### <span data-ttu-id="ba6fe-264">System.Object</span><span class="sxs-lookup"><span data-stu-id="ba6fe-264">System.Object</span></span>

<span data-ttu-id="ba6fe-265">Текст веб-запроса можно передать в `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="ba6fe-265">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="ba6fe-266">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ba6fe-266">Outputs</span></span>

### <span data-ttu-id="ba6fe-267">System.Xml.Xmlдокумент, Microsoft.PowerShell.Commands.HtmЛвебреспонсеобжект, System. String</span><span class="sxs-lookup"><span data-stu-id="ba6fe-267">System.Xml.XmlDocument, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System.String</span></span>

<span data-ttu-id="ba6fe-268">Выходные данные командлета зависят от формата получаемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-268">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="ba6fe-269">PSObject</span><span class="sxs-lookup"><span data-stu-id="ba6fe-269">PSObject</span></span>

<span data-ttu-id="ba6fe-270">Если запрос возвращает строки JSON, `Invoke-RestMethod` возвращает PSObject, представляющий строки.</span><span class="sxs-lookup"><span data-stu-id="ba6fe-270">If the request returns JSON strings, `Invoke-RestMethod` returns a PSObject that represents the strings.</span></span>

## <span data-ttu-id="ba6fe-271">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba6fe-271">Notes</span></span>

## <span data-ttu-id="ba6fe-272">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ba6fe-272">Related Links</span></span>

[<span data-ttu-id="ba6fe-273">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="ba6fe-273">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="ba6fe-274">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="ba6fe-274">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="ba6fe-275">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="ba6fe-275">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
