---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: d00885d0911d20dee0e5c498e5e339af4fa39a34
ms.sourcegitcommit: eaac7af89171379df2e20464ebee9fc7e7d7674a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "93230593"
---
# Invoke-RestMethod

## Краткий обзор
Отправляет запрос HTTP или HTTPS в веб-службу RESTful.

## SYNTAX

### Стандардмесод (по умолчанию)

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

### стандардмесоднопрокси

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

### кустоммесоднопрокси

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

### кустоммесод

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

## Описание

`Invoke-RestMethod`Командлет отправляет запросы HTTP и HTTPS к веб-службам, которые возвращают структурированные данные.

PowerShell форматирует ответ на основе типа данных. Для канала RSS или ATOM PowerShell возвращает XML-узлы элемента или записи. Для нотация объектов JavaScript (JSON) или XML, PowerShell преобразует или десериализует содержимое в объекты.

Этот командлет впервые появился в Windows PowerShell 3.0.

Начиная с PowerShell 7,0, `Invoke-RestMethod` поддерживает настройку прокси-сервера, определяемую переменными среды. См. раздел " [Примечания](#notes) " этой статьи.

## Примеры

### Пример 1. Получение RSS-канала PowerShell

В этом примере `Invoke-RestMethod` командлет используется для получения сведений из RSS-канала блога в блоге PowerShell. Команда использует `Format-Table` командлет для вывода значений свойств **Title** и **pubDate** каждого блога в таблице.

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

### Пример 2. выполнение запроса POST

В этом примере пользователь выполняет `Invoke-RestMethod` запрос POST на веб-сайте интрасети в организации пользователя.

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

Учетные данные запрашиваются, а затем сохраняются в, `$Cred` а URL-адрес, к которому будет осуществляться доступ, определяется в `$Url` .

`$Body`Переменная описывает критерии поиска, указывает CSV в качестве режима вывода и задает период времени для возвращаемых данных, которые запускаются два дня назад и завершаются один день назад. Переменная Body задает значения параметров, которые применяются к конкретному REST API, с которым `Invoke-RestMethod` устанавливается связь.

`Invoke-RestMethod`Команда выполняется со всеми переменными на месте, указывая путь и имя файла для результирующего выходного CSV-файла.

### Пример 3. следование ссылкам на связи

Некоторые интерфейсы API-интерфейса поддерживают разбиение на страницы по ссылкам связи на [RFC5988](https://tools.ietf.org/html/rfc5988#page-6). Вместо того чтобы анализировать заголовок для получения URL-адреса для следующей страницы, можно воспользоваться командлетом. Этот пример возвращает первые две страницы проблем из репозитория GitHub в PowerShell.

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### Пример 4. Упрощенная передача данных в составе или форме

Для некоторых API требуется `multipart/form-data` Отправка файлов и смешанного содержимого. В этом примере показано, как обновить профиль пользователя.

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

Для формы профиля требуются следующие поля: `firstName` , `lastName` , `email` , `avatar` , `birthday` и `hobbies` . API ожидает, что в поле будет указан образ для профиля пользователя PIC `avatar` . API также будет принимать несколько `hobbies` записей для отправки в одну и ту же форму.

При создании `$Form` хэш-таблицы имена ключей используются в качестве имен полей формы. По умолчанию значения хэш-таблицы будут преобразованы в строки. Если указано `System.IO.FileInfo` значение, содержимое файла будет отправлено. Если имеется коллекция, такая как массивы или списки, поле формы будет отправляться несколько раз.

При использовании `Get-Item` в `avatar` ключе `FileInfo` объект будет задан как значение. В результате будут отправлены данные изображения для `jdoe.png` .

Предоставляя список для `hobbies` ключа, `hobbies` поле будет присутствовать в отправку один раз для каждого элемента списка.

### Пример 5. Передача нескольких заголовков

Для проверки подлинности или проверки интерфейсам API часто требуются переданные заголовки. В этом примере показано, как передать несколько заголовков из `hash-table` в REST API.

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## Параметры

### -Алловуненкриптедаусентикатион

Разрешает отправку учетных данных и секретов через незашифрованные соединения. По умолчанию предоставление **учетных данных** или любого варианта **проверки подлинности** с **URI** , который не начинается с, `https://` приведет к ошибке и запрос будет прерван, чтобы предотвратить непреднамеренное взаимодействие секретов в виде обычного текста с помощью незашифрованных соединений. Чтобы переопределить это поведение на свой риск, укажите параметр **алловуненкриптедаусентикатион** .

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

Указывает тип явной проверки подлинности, используемый для запроса. Значение по умолчанию — **None** .
**Проверку подлинности** нельзя использовать с **уседефаулткредентиалс** .

Доступные варианты проверки подлинности:

- **Нет** . Этот параметр используется по умолчанию, если не указана **Проверка подлинности** . Явная проверка подлинности не будет использоваться.
- **Базовый** : требуются **учетные данные** . Учетные данные будут использоваться для отправки заголовка обычной проверки подлинности RFC 7617 `Authorization: Basic` в формате `base64(user:password)` .
- **Bearer** : требуется **токен** . Будет отсылать и `Authorization: Bearer` заголовку RFC 6750 с помощью заданного маркера. Это псевдоним для **OAuth**
- **OAuth** : требуется **токен** . Отправляет заголовок RFC 6750 `Authorization: Bearer` с помощью заданного маркера. Это псевдоним для **носителя**

При предоставлении **проверки подлинности** все заголовки, заданные `Authorization` для **заголовков** или входящие в состав **сеанса** , переопределяются.

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
Можно также передать значение текста по конвейеру в `Invoke-RestMethod` .

Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.

Если входные данные являются запросом GET, а тело является `IDictionary` (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса. Для других типов запросов (таких как POST) основной текст задается как значение основного текста запроса в стандартном формате имя=значение.

Если текст является формой или выходными данными другого `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.

Параметр **Body** может также принимать объект **System .NET. http. мултипартформдатаконтент** . Это упростит `multipart/form-data` запросы. Когда для **тела** передается объект **мултипартформдатаконтент** , все заголовки содержимого, связанные с параметрами **ContentType** , **headers** или для **сеанса** , будут переопределены заголовками содержимого `MultipartFormDataContent` объекта. Эта функция была добавлена в PowerShell 6.0.0.

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

Задает сертификат клиента, который используется для выполнения защищенного веб-запроса. Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.

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

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

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

Если этот параметр пропущен и метод Request имеет значение POST, `Invoke-RestMethod` задает для типа содержимого значение `application/x-www-form-urlencoded` . В противном случае тип содержимого не указывается в вызове.

**ContentType** будет переопределен при `MultipartFormDataContent` предоставлении объекта для **тела** .

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

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.

**Учетные данные** можно использовать отдельно или в сочетании с определенными параметрами **проверки подлинности** . Если удаленный сервер отправляет запрос на проверку подлинности, то он будет предоставлять учетные данные только удаленному серверу. При использовании с параметрами **проверки подлинности** учетные данные будут явно отправлены.

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

Указывает пользовательский метод, используемый для веб-запроса. Его можно использовать с методом Request, необходимым для конечной точки, который не является доступным для **метода** . **Методы** и **кустоммесод** не могут использоваться вместе.

Пример

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

Это делает `TEST` http-запрос к API.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Дисаблекипаливе

Указывает, что командлет задает для значения **KeepAlive** в заголовке HTTP значение false. По умолчанию **KeepAlive** имеет значение True. **KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.

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

### -Фолловреллинк

Указывает, что командлет должен следовать ссылкам связи.

Некоторые интерфейсы API-интерфейса поддерживают разбиение на страницы по ссылкам связи на [RFC5988](https://tools.ietf.org/html/rfc5988#page-6). Вместо того чтобы анализировать заголовок для получения URL-адреса для следующей страницы, можно воспользоваться командлетом. Чтобы задать, сколько раз следует следовать ссылкам связи, используйте параметр **максимумфолловреллинк** .

При использовании этого параметра командлет возвращает коллекцию страниц результатов. Каждая страница результатов может содержать несколько результирующих элементов.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Форма

Преобразует словарь в `multipart/form-data` отправку. **Форма** не может использоваться с **телом** .
Значение, если **ContentType** будет проигнорирован.

Ключи словаря будут использоваться в качестве имен полей формы. По умолчанию значения форм будут преобразованы в строковые значения.

Если значение является объектом **System. IO. FileInfo** , будет отправлено содержимое двоичного файла.
Имя файла будет отправлено как `filename` . MIME будет установлен в значение `application/octet-stream` . `Get-Item` можно использовать для упрощения предоставления объекта **System. IO. FileInfo** .

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

Если значение является типом коллекции, например массивом или списком, поле for будет отправляться несколько раз. Значения списка будут рассматриваться как строки по умолчанию. Если значение является объектом **System. IO. FileInfo** , будет отправлено содержимое двоичного файла. Вложенные коллекции не поддерживаются.

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

В приведенном выше примере `tags` поле будет представлено в форме три раза, по одному разу для каждого из `Vacation` , `Italy` и `2017` . `pictures`Поле также будет отправлено один раз для каждого файла в `2017-Italy` папке. Двоичное содержимое файлов в этой папке будет отправлено как значения.

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

Чтобы задать заголовки UserAgent, используйте параметр **UserAgent** . Этот параметр нельзя использовать для указания `User-Agent` заголовков или файлов cookie.

Заголовки, связанные с содержимым, такие как, `Content-Type` будут переопределены при `MultipartFormDataContent` предоставлении объекта для **тела** .

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

Получает содержимое веб-запроса из файла.

Введите путь и имя файла. Если путь не указан, по умолчанию используется текущее расположение.

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

### -Максимумфолловреллинк

Указывает, сколько раз следует следовать ссылкам связи, если используется **фолловреллинк** . Значение меньшего размера может потребоваться, если при регулировании API-интерфейса используется слишком много запросов. Значение по умолчанию — `[Int32]::MaxValue`. Значение 0 (ноль) предотвращает следующие ссылки связи.

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

### -Максимумредиректион

Указывает, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения. Значение по умолчанию — 5. Значение 0 (ноль) запрещает любые перенаправления.

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
- Объединить
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

Указывает, что командлет не будет использовать прокси-сервер для доступа к назначению.

Если необходимо обойти прокси-сервер, настроенный в Internet Explorer, или прокси-сервер, указанный в окружении, используйте этот параметр.

Этот параметр появился в PowerShell 6,0.

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

Сохраняет основной текст ответа в указанный выходной файл. Введите путь и имя файла. Если путь не указан, по умолчанию используется текущее расположение. Имя рассматривается как литеральный путь. Имена, содержащие квадратные скобки ( `[]` ), должны быть заключены в одинарные кавычки ( `'` ).

По умолчанию `Invoke-RestMethod` возвращает результаты в конвейер. Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru** .

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

Возвращает результаты в дополнение к их записи в файл. Этот параметр активен, если в команде также используется параметр **OutFile** .

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

Использует прокси-сервер для запроса вместо прямого подключения к Интернет-ресурсу. Введите универсальный код ресурса (URI) сетевого прокси-сервера.

Эта функция была добавлена в PowerShell 6.0.0.

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

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** . По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , **User@Domain.Com** или введите `PSCredential` объект, например, созданный `Get-Credential` командлетом.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. В одной команде нельзя использовать параметры **ProxyCredential** и **проксюседефаулткредентиалс** .

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

### -Респонсехеадерсвариабле

Создает словарь заголовков ответов и сохраняет его в значении указанной переменной. Ключи словаря будут содержать имена полей заголовка ответа, возвращаемого веб-сервером, а значения будут соответствующими значениями полей.

Эта функция была добавлена в PowerShell 6.0.0.

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

### -Resume

Выполняет наиболее эффективную попытку возобновить загрузку частичного файла. Для параметра **Resume** требуется параметр **файла** .

**Resume** работает только с размером локального файла и удаленного файла и не выполняет никаких других проверок того, что локальный файл и удаленный файл одинаковы.

Если размер локального файла меньше, чем размер удаленного файла, командлет попытается возобновить загрузку файла и дополнит добавление оставшихся байтов в конец файла.

Если размер локального файла совпадает с размером удаленного файла, никакие действия не выполняются и командлет предполагает, что скачивание уже завершено.

Если размер локального файла превышает размер удаленного файла, то локальный файл будет перезаписан, а весь удаленный файл будет полностью повторно скачан. Это поведение аналогично использованию **файла** без **возобновления** .

Если удаленный сервер не поддерживает возобновление загрузки, локальный файл будет перезаписан, а весь удаленный файл будет полностью повторно скачан. Это поведение аналогично использованию **файла** без **возобновления** .

Если локальный файл не существует, то будет создан локальный файл, а весь удаленный файл будет полностью скачан. Это поведение аналогично использованию **файла** без **возобновления** .

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

При указании переменной сеанса `Invoke-RestMethod` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell. Переменную в сеансе можно использовать сразу после выполнения команды.

В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession** . При установке нового соединения PowerShell использует данные в объекте сеанса веб-запроса. Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** . Значения параметров имеют приоритет над значениями в сеансе веб-запроса.

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

Пропускает проверки сертификатов, включающие все проверки, такие как срок действия, отзыв, доверенный корневой центр и т. д.

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

Это приведет к отключению проверки значений, передаваемых в параметры **ContentType** , **headers** и **UserAgent** .

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

**Сслпротокол** использует `WebSslProtocol` флаг Enum. Можно указать несколько протоколов, используя нотацию флага или объединив несколько `WebSslProtocol` параметров с `-bor` , однако предоставление нескольких протоколов не поддерживается на всех платформах.

> [!NOTE]
> На платформах, отличных от Windows, невозможно предоставить `Tls` или `Tls12` как вариант. Поддержка `Tls13` недоступна во всех операционных системах и должна проверяться отдельно для каждой операционной системы.

Эта функция была добавлена в PowerShell 6.0.0, а поддержка `Tls13` добавлена в powershell 7,1.

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

### -Статускодевариабле

Этот параметр задает переменную, которой присваивается целочисленное значение кода состояния. Параметр может выявление сообщений об успешном завершении или сообщений о сбое при использовании с параметром **скифттперрорчекк** .

Введите имя переменной параметра в виде строки, например `-StatusCodeVariable "scv"` .

Этот параметр появился в PowerShell 7.

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

### -TimeoutSec

Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах. Значение по умолчанию, равное 0, указывает неопределенное время ожидания.

Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.

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

### -Token

Токен OAuth или носитель для включения в запрос. Для некоторых параметров **проверки подлинности** требуется **токен** . Его нельзя использовать независимо.

**Токен** принимает `SecureString` , который содержит токен. Для указания токена вручную используйте следующую команду:

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

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

Указывает универсальный код ресурса (URI) Интернет-ресурса, в который отправляется веб-запрос. Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.

Этот параметр обязателен. Имя параметра ( **URI** ) является необязательным.

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

Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential** . Значения параметров имеют приоритет над значениями в сеансе веб-запроса. Заголовки, связанные с содержимым, такие как `Content-Type` , также будут переопределены при предоставлении объекта **Мултипартформдатаконтент** для **тела** .

В отличие от удаленного сеанса, сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о соединении и запросе, включая файлы cookie, учетные данные, значение максимального перенаправления и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы создать сеанс веб-запроса, введите имя переменной без знака доллара в значении параметра **сессионвариабле** `Invoke-RestMethod` команды. `Invoke-RestMethod` создает сеанс и сохраняет его в переменной. В последующих командах используйте переменную в качестве значения параметра **WebSession** .

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

Текст веб-запроса можно передать в `Invoke-RestMethod` .

## Выходные данные

### System. Int64, System. String, System.Xml.Xmlдокумент

Выходные данные командлета зависят от формата получаемого содержимого.

### PSObject

Если запрос возвращает строки JSON, `Invoke-RestMethod` возвращает **PSObject** , представляющий строки.

## ПРИМЕЧАНИЯ

Некоторые функции могут быть недоступны на всех платформах.

В связи с изменениями в .NET Core 3,1, PowerShell 7,0 и более поздних версий использует свойство [HttpClient. DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) для определения конфигурации прокси-сервера.

В зависимости от используемой платформы значение этого свойства отличается от правил.

- **Для Windows** : считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, из параметров прокси пользователя.
- **Для macOS** : считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, из параметров прокси-сервера системы.
- **Для Linux** : считывает конфигурацию прокси-сервера из переменных среды или, если они не определены, это свойство инициализирует ненастроенный экземпляр, который обходит все адреса.

Переменные среды, используемые для `DefaultProxy` инициализации платформ на платформе Windows и UNIX:

- ` HTTP_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в HTTP-запросах.
- `HTTPS_PROXY`: имя узла или IP-адрес прокси-сервера, используемого в запросах HTTPS.
- `ALL_PROXY`: имя узла или IP-адрес прокси-сервера, используемого для запросов HTTP и HTTPS в случае `HTTP_PROXY` или `HTTPS_PROXY` , не определен.
- `NO_PROXY`: список имен узлов с разделителями-запятыми, которые следует исключить из прокси-сервера.

## Связанные ссылки

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)
