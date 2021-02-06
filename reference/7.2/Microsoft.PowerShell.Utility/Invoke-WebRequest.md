---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 0925bef2e7b0f5ad46f6dc1aabf96e0de604c08a
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "99604599"
---
# Invoke-WebRequest

## Краткий обзор
Получает содержимое с веб-страницы в Интернете.

## SYNTAX

### Стандардмесод (по умолчанию)

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

### стандардмесоднопрокси

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

### кустоммесод

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

### кустоммесоднопрокси

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

## DESCRIPTION

`Invoke-WebRequest`Командлет отправляет запросы HTTP и HTTPS на веб-страницу или веб-службу. Он анализирует ответ и возвращает коллекции ссылок, изображений и других значащих HTML-элементов.

Этот командлет появился в PowerShell 3,0.

Начиная с PowerShell 7,0, `Invoke-WebRequest` поддерживает настройку прокси-сервера, определяемую переменными среды. См. раздел " [Примечания](#notes) " этой статьи.

## Примеры

### Пример 1. Отправка веб-запроса

В этом примере `Invoke-WebRequest` командлет используется для отправки веб-запроса на сайт Bing.com.

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

Первая команда выдает запрос и сохраняет ответ в `$Response` переменной.

Вторая команда получает все **инпутфиелд** , где свойство **Name** имеет значение `"* Value"` . Отфильтрованные результаты передаются в, `Select-Object` чтобы выбрать свойства " **имя** " и " **значение** ".

### Пример 2. Использование веб-службы с отслеживанием состояния

В этом примере показано, как использовать `Invoke-WebRequest` командлет с веб-службой с отслеживанием состояния.

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

Первый вызов для `Invoke-WebRequest` отправки запроса на вход. Команда задает значение "Session" в качестве значения параметра **-сессионвариабле** и сохраняет результат в `$LoginResponse` переменной. После выполнения команды переменная содержит переменную, `$LoginResponse` `BasicHtmlWebResponseObject` а `$Session` переменная содержит `WebRequestSession` объект. Это записывает пользователя на сайт.

Вызов `$Session` сам по себе показывает `WebRequestSession` объект в переменной.

Второй вызов `Invoke-WebRequest` извлекает профиль пользователя, который требует входа пользователя на сайт. Данные сеанса, хранящиеся в `$Session` переменной, используются для предоставления файлов cookie сеанса сайту, созданному во время входа. Результат сохраняется в `$ProfileResponse` переменной.

Вызов `$ProfileResponse` сам по себе показывает `BasicHtmlWebResponseObject` в переменной.

### Пример 3. получение ссылок с веб-страницы

В этом примере выполняется получение ссылок на веб-странице. Он использует `Invoke-WebRequest` командлет для получения содержимого веб-страницы. Затем используется свойство **Links** объекта, `BasicHtmlWebResponseObject` которое `Invoke-WebRequest` возвращает, и свойство **href** каждой ссылки.

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### Пример 4. записывает содержимое ответа в файл, используя кодировку, определенную на запрошенной странице.

В этом примере `Invoke-WebRequest` командлет используется для получения содержимого веб-страницы для страницы документации по PowerShell.

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

Первая команда извлекает страницу и сохраняет объект ответа в `$Response` переменной.

Вторая команда создает объект `StreamWriter` для использования при записи содержимого ответа в файл. Свойство **Encoding** объекта Response используется для задания кодировки для файла.

Последние несколько команд записывают в файл свойство **Content** , а затем удаляют `StreamWriter` .

Обратите внимание, что свойство **Encoding** имеет значение null, если веб-запрос не возвращает текстовое содержимое.

### Пример 5. Отправка файла составного или многофайлового данных

В этом примере используется `Invoke-WebRequest` командлет для отправки файла в качестве `multipart/form-data` отправки. Файл `c:\document.txt` отправляется в виде поля формы `document` с параметром `Content-Type` `text/plain` .

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

### Пример 6. Упрощенная многокомпонентная или форма-отправка данных

Для некоторых API требуется `multipart/form-data` Отправка файлов и смешанного содержимого. В этом примере демонстрируется обновление профиля пользователя.

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

Для формы профиля требуются следующие поля: `firstName` , `lastName` , `email` , `avatar` , `birthday` и `hobbies` . API ожидает, что в поле будет указан образ для профиля пользователя PIC `avatar` . API также принимает несколько `hobbies` записей, которые должны быть отправлены в одной и той же форме.

При создании `$Form` хэш-таблицы имена ключей используются в качестве имен полей формы. По умолчанию значения хэш-таблицы преобразуются в строки. Если значение **System. IO. FileInfo** имеется, содержимое файла отправляется. Если имеется коллекция, такая как массивы или списки, поле формы отправляется несколько раз.

При использовании `Get-Item` в `avatar` ключе `FileInfo` объект задается как значение. В результате отправляются данные изображения для `jdoe.png` .

Предоставляя список для `hobbies` ключа, `hobbies` поле будет присвоено в отправку один раз для каждого элемента списка.

### Пример 7. перехват сообщений без успешности Invoke-WebRequest

При `Invoke-WebRequest` обнаружении сообщения HTTP, не являющегося успешным (404, 500 и т. д.), оно не возвращает выходные данные и вызывает ошибку, которая завершается. Чтобы перехватить ошибку и просмотреть **StatusCode** , можно заключить выполнение в `try/catch` блок.

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

Завершающая ошибка перехвачена `catch` блоком, который извлекает **StatusCode** из объекта **исключения** .

## PARAMETERS

### -Алловуненкриптедаусентикатион

Разрешает отправку учетных данных и секретов через незашифрованные соединения. По умолчанию предоставление **учетных данных** или любого варианта **проверки подлинности** с **URI** , который не начинается с, `https://` приводит к ошибке и запрос прерывается, чтобы предотвратить непреднамеренное взаимодействие секретов в виде обычного текста с помощью незашифрованных соединений. Чтобы переопределить это поведение на свой риск, укажите параметр **алловуненкриптедаусентикатион** .

> [!WARNING]
> Использование этого параметра не является безопасным и не рекомендуется. Он предоставляется только для обеспечения совместимости с устаревшими системами, которые не могут предоставлять зашифрованные соединения. Используйте свой собственный риск.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Authentication

Указывает тип явной проверки подлинности, используемый для запроса. Значение по умолчанию — **None**.
**Проверку подлинности** нельзя использовать с **уседефаулткредентиалс**.

Доступные варианты проверки подлинности:

- **Нет**. Этот параметр используется по умолчанию, если не указана **Проверка подлинности** . явная проверка подлинности не используется.
- **Базовый**: требуются **учетные данные**. Учетные данные отправляются в заголовке обычной проверки подлинности RFC 7617 в формате `base64(user:password)` .
- **Bearer**: требуется **токен**. Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера. Это псевдоним для **OAuth**
- **OAuth**: требуется **токен**. Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера. Это псевдоним для **носителя**

При указании **проверки подлинности** переопределяются все `Authorization` заголовки, предоставленные **заголовкам** или добавленные в **сеансе**.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Body

Задает основной текст запроса. Основной текст — это содержимое запроса, идущее после заголовков.
Можно также передать значение текста по конвейеру в `Invoke-WebRequest` .

Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.

Если входные данные являются запросом GET, а тело является `IDictionary` (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса. Для других типов запросов (например, POST) текст задается как значение текста запроса в стандартном `name=value` формате.

Параметр **Body** может также принимать `System.Net.Http.MultipartFormDataContent` объект. Это упрощает `multipart/form-data` запросы. Когда для **тела** передается объект **мултипартформдатаконтент** , все заголовки содержимого, относящиеся к параметрам **ContentType**, **headers** или **Session** , переопределяются заголовками содержимого объекта **мултипартформдатаконтент** . Эта функция была добавлена в PowerShell 6.0.0.

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

### — Сертификат

Указывает сертификат клиента, используемый для безопасного веб-запроса. Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.

Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске Certificate ( `Cert:` ). Если сертификат недействителен или не имеет достаточных полномочий, команда завершается ошибкой.

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

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с локальными учетными записями пользователей. они не работают с учетными записями домена.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .

> [!NOTE]
> В настоящее время эта функция поддерживается только на платформах ОС Windows.

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

### -ContentType

Задает тип содержимого веб-запроса.

Если этот параметр пропущен и метод Request имеет значение POST, `Invoke-WebRequest` задает для типа содержимого значение `application/x-www-form-urlencoded` . В противном случае тип содержимого не указывается в вызове.

**ContentType** переопределяется при предоставлении объекта **мултипартформдатаконтент** для **тела**.

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

### -Credential

Указывает учетную запись пользователя, обладающую разрешением для отправки запроса. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.

**Учетные данные** можно использовать отдельно или в сочетании с определенными параметрами **проверки подлинности** . При отдельном использовании он предоставляет учетные данные только удаленному серверу, если удаленный сервер отправляет запрос на проверку подлинности. При использовании с параметрами **проверки подлинности** учетные данные явно отправляются.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -Кустоммесод

Указывает пользовательский метод, используемый для веб-запроса. Это можно использовать, если метод запроса, требуемый конечной точкой, не является доступным для **метода**. **Методы** и **кустоммесод** нельзя использовать вместе.

Этот пример выполняет `TEST` http-запрос к API:

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Дисаблекипаливе

Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение **false**. По умолчанию **KeepAlive** имеет **значение true**. **KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.

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

### -Форма

Преобразует словарь в `multipart/form-data` отправку. **Форма** не может использоваться с **телом**.
Если используется **ContentType** , он игнорируется.

Ключи словаря используются в качестве имен полей формы. По умолчанию значения формы преобразуются в строковые значения.

Если значение является объектом **System. IO. FileInfo** , то передаются содержимое двоичного файла. Имя файла отправляется как свойство **filename** . Тип MIME задан как `application/octet-stream` . `Get-Item` можно использовать для упрощения предоставления объекта **System. IO. FileInfo** .

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

Если значение является типом коллекции, такими массивами или списками, поле for отправляется несколько раз.
Значения списка по умолчанию обрабатываются как строки. Если значение является объектом **System. IO. FileInfo** , то передаются содержимое двоичного файла. Вложенные коллекции не поддерживаются.

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

В приведенном выше примере `tags` поле указано в форме три раза, по одному разу для каждого из `Vacation` , `Italy` и `2017` . `pictures`Поле также отправляется один раз для каждого файла в `2017-Italy` папке. Двоичное содержимое файлов в этой папке отправляется в виде значений.

Эта функция была добавлена в PowerShell 6.1.0.

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

### -Заголовки

Задает заголовки веб-запроса. Введите словарь или хэш-таблицу.

Чтобы задать заголовки UserAgent, используйте параметр **UserAgent**. Этот параметр нельзя использовать для указания заголовков **User-Agent** и cookie.

Заголовки, связанные с содержимым, такие как, `Content-Type` переопределяются при предоставлении объекта **Мултипартформдатаконтент** для **тела**.

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

### -Файл

Получает содержимое веб-запроса из файла. Введите путь и имя файла. Если путь не указан, по умолчанию используется текущее расположение.

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

### -Максимумредиректион

Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения. Значение по умолчанию — 5. Значение 0 (ноль) запрещает любые перенаправления.

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

### -Максимумретрикаунт

Указывает, сколько раз PowerShell повторяет попытку подключения при получении кода ошибки между 400 и 599, включительно или 304. См. также параметр **ретринтервалсек** для указания числа повторных попыток.

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

### -Method

Задает метод, используемый для веб-запроса. Допустимые значения для этого параметра:

- По умолчанию
- DELETE
- Получить
- Head
- Объединение
- Параметры
- Обновление
- Опубликовать
- Put
- Трассировка

Параметр **кустоммесод** можно использовать для методов запроса, не перечисленных выше.

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

### -NoProxy

Указывает, что командлет не должен использовать прокси-сервер для достижения места назначения. Если необходимо обойти прокси-сервер, настроенный в среде, используйте этот параметр. Эта функция была добавлена в PowerShell 6.0.0.

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

### -Файл

Указывает выходной файл, для которого этот командлет сохраняет текст ответа. Введите путь и имя файла.
Если путь не указан, по умолчанию используется текущее расположение. Имя рассматривается как литеральный путь.
Имена, содержащие квадратные скобки ( `[]` ), должны быть заключены в одинарные кавычки ( `'` ).

По умолчанию `Invoke-WebRequest` возвращает результаты в конвейер. Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru**.

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

### -PassThru

Указывает, что командлет возвращает результаты в дополнение к записи в файл. Этот параметр активен, если в команде также используется параметр **OutFile**.

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

### -Пресервеаусоризатиононредирект

Указывает, что командлет должен сохранить `Authorization` заголовок (при его наличии) в перенаправлениях.

По умолчанию этот командлет отделяет `Authorization` заголовок перед перенаправлением. Указание этого параметра отключает эту логику в случаях, когда заголовок необходимо отправить в расположение перенаправления.

Эта функция была добавлена в PowerShell 6.0.0.

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

### Прокси-сервер

Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.
Введите URI сетевого прокси-сервера.

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

### -ProxyCredential

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01**, **User@Domain.Com** или введите `PSCredential` объект, например, созданный `Get-Credential` командлетом.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .

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

### -Проксюседефаулткредентиалс

Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .

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

### -Resume

Выполняет наиболее эффективную попытку возобновить загрузку частичного файла. Для **возобновления** требуется **файл**.

**Resume** работает только с размером локального файла и удаленного файла и не выполняет никаких других проверок того, что локальный файл и удаленный файл одинаковы.

Если размер локального файла меньше, чем размер удаленного файла, командлет попытается возобновить загрузку файла и добавить оставшиеся байты в конец файла.

Если размер локального файла совпадает с размером удаленного файла, никакие действия не выполняются и командлет предполагает, что скачивание уже завершено.

Если размер локального файла превышает размер удаленного файла, то локальный файл перезаписывается, а весь удаленный файл загружается повторно. Это поведение аналогично использованию **файла** без **возобновления**.

Если удаленный сервер не поддерживает возобновление загрузки, то локальный файл перезаписывается, а весь удаленный файл повторно загружается. Это поведение аналогично использованию **файла** без **возобновления**.

Если локальный файл не существует, то создается локальный файл и загружается весь удаленный файл. Это поведение аналогично использованию **файла** без **возобновления**.

Эта функция была добавлена в PowerShell 6.1.0.

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

### -Ретринтервалсек

Указывает интервал между повторными попытками соединения при получении кода ошибки между 400 и 599, включительно или 304. См. также параметр **максимумретрикаунт** для указания числа повторных попыток.

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

### -Сессионвариабле

Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.
Введите имя переменной без символа доллара ( `$` ).

При указании переменной сеанса `Invoke-WebRequest` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell. Переменную в сеансе можно использовать сразу после выполнения команды.

В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession**. При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса. Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**. Значения параметров имеют приоритет над значениями в сеансе веб-запроса.

В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .

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

### -SkipCertificateCheck

Пропускает проверку сертификатов. Сюда входят все проверки, такие как срок действия, отзыв, доверенный корневой центр и т. д.

> [!WARNING]
> Использование этого параметра не является безопасным и не рекомендуется. Этот параметр предназначен только для использования с известными узлами с использованием самозаверяющего сертификата для тестирования. Используйте свой собственный риск.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Скифеадервалидатион

Указывает, что командлет должен добавить в запрос заголовки без проверки.

Этот параметр следует использовать для сайтов, которым требуются значения заголовка, не соответствующие стандартам.
Указание этого параметра отключает проверку, чтобы разрешить передачу значения без проверки. Если указано, все заголовки добавляются без проверки.

Этот параметр отключает проверку значений, передаваемых в параметры **ContentType**, **headers** и **UserAgent** .

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Скифттперрорчекк

Этот параметр приводит к тому, что командлет игнорирует состояния ошибок HTTP и продолжает обрабатывать ответы.
Ответы об ошибках записываются в конвейер точно так же, как если бы они были успешными.

Этот параметр появился в PowerShell 7.

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

### -Сслпротокол

Задает протоколы SSL/TLS, допустимые для веб-запроса. По умолчанию разрешены все протоколы SSL и TLS, поддерживаемые системой. **Сслпротокол** позволяет ограничить конкретные протоколы в целях обеспечения соответствия.

**Сслпротокол** использует перечисление флага **вебсслпротокол** . Можно указать несколько протоколов, используя нотацию флагов или объединив несколько параметров **вебсслпротокол** с **бор**, однако предоставление нескольких протоколов не поддерживается на всех платформах.

> [!NOTE]
> На платформах, отличных от Windows, невозможно предоставить `Tls` или `Tls12` как вариант. Поддержка `Tls13` недоступна во всех операционных системах и должна проверяться отдельно для каждой операционной системы.

Эта функция была добавлена в PowerShell 6.0.0, а поддержка `Tls13` добавлена в powershell 7,1.

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

### -TimeoutSec

Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах. Значение по умолчанию, равное 0, указывает неопределенное время ожидания.

Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.

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

### -Token

Токен OAuth или носитель для включения в запрос. Для некоторых параметров **проверки подлинности** требуется **токен** . Его нельзя использовать независимо.

**Токен** принимает значение, `SecureString` содержащее токен. Для предоставления маркера вручную используйте следующую команду:

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

Этот параметр появился в PowerShell 6,0.

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

### -Трансференкодинг

Задает значение для заголовка transfer-encoding ответа HTTP. Допустимые значения для этого параметра:

- Chunked
- Сжать
- Deflate
- GZip
- Идентификация

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

### — URI

Указывает универсальный код ресурса (URI) Интернет-ресурса, в который отправляется веб-запрос. Введите URI. Этот параметр поддерживает только протоколы HTTP или HTTPS.

Это обязательный параметр. **URI** имени параметра является необязательным.

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

### -Усебасикпарсинг

Этот параметр является устаревшим. Начиная с PowerShell 6.0.0, все веб-запросы используют только базовый анализ. Этот параметр включен только для обеспечения обратной совместимости, и его использование не влияет на работу командлета.

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

### -UseDefaultCredentials

Указывает, что командлет использует учетные данные текущего пользователя для отправки веб-запроса. Это не может использоваться с **проверкой подлинности** или **учетными данными** и может не поддерживаться на всех платформах.

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

### -UserAgent

Указывает строку агента пользователя для веб-запроса.

Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` небольшому варианту для каждой операционной системы и платформы.

Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari.

Например, следующая команда использует строку агента пользователя для Internet Explorer:

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

### -Семинар

Указывает сеанс веб-запроса. Введите имя переменной, включая знак доллара ( `$` ).

Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**. Значения параметров имеют приоритет над значениями в сеансе веб-запроса. Заголовки, связанные с содержимым, такие как `Content-Type` , также переопределяются при предоставлении объекта **Мултипартформдатаконтент** для **тела**.

В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы создать сеанс веб-запроса, введите имя переменной без знака доллара в значении параметра **сессионвариабле** `Invoke-WebRequest` команды. `Invoke-WebRequest` создает сеанс и сохраняет его в переменной. В последующих командах используйте переменную в качестве значения параметра **WebSession**.

В одной команде нельзя использовать параметры **сессионвариабле** и **Session** .

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Object

Текст веб-запроса можно передать в `Invoke-WebRequest` .

## Выходные данные

### Microsoft. PowerShell. Commands. Басичтмлвебреспонсеобжект

## ПРИМЕЧАНИЯ

Начиная с PowerShell 6.0.0 `Invoke-WebRequest` поддерживает только базовый анализ.

Дополнительные сведения см. в разделе [басичтмлвебреспонсеобжект](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).

В связи с изменениями в .NET Core 3,1, PowerShell 7,0 и более поздних версий использует свойство [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) для определения конфигурации прокси-сервера.

Значение этого свойства определяется вашей платформой:

- **Для Windows**: считывает конфигурацию прокси-сервера из переменных среды. Если эти переменные не определены, свойство является производным от параметров прокси пользователя.
- **Для macOS**: считывает конфигурацию прокси-сервера из переменных среды. Если эти переменные не определены, свойство является производным от параметров прокси-сервера системы.
- **Для Linux**: считывает конфигурацию прокси-сервера из переменных среды. Если эти переменные не определены, свойство инициализирует ненастроенный экземпляр, который обходит все адреса.

Переменные среды, используемые для `DefaultProxy` инициализации платформ на платформе Windows и UNIX:

- ` HTTP_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в HTTP-запросах.
- `HTTPS_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в запросах HTTPS.
- `ALL_PROXY`: имя узла или IP-адрес прокси-сервера, используемого для запросов HTTP и HTTPS в случае `HTTP_PROXY` или `HTTPS_PROXY` , не определен.
- `NO_PROXY`: список имен узлов с разделителями-запятыми, которые следует исключить из прокси-сервера.

## Связанные ссылки

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
