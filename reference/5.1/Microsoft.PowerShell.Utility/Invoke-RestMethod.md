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
# Invoke-RestMethod

## Краткий обзор
Отправляет запрос HTTP или HTTPS в веб-службу RESTful.

## Синтаксис

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## Описание

`Invoke-RestMethod`Командлет отправляет запросы HTTP и HTTPS в веб-службы передачи данных о состоянии представления (RESTful), которые возвращают структурированные данные.

Windows PowerShell форматирует ответ в соответствии с типом данных. Для RSS-канала или веб-канала ATOM Windows PowerShell возвращает узлы XML Item или Entry. Для нотации объектов JavaScript (JSON) или XML Windows PowerShell преобразует (или десериализует) содержимое в объекты.

Этот командлет впервые появился в Windows PowerShell 3.0.

> [!NOTE]
> По умолчанию код сценария на веб-странице может выполняться при синтаксическом анализе страницы для заполнения `ParsedHtml` Свойства. Чтобы отключить это, используйте параметр **усебасикпарсинг** .

## Примеры

### Пример 1. Получение RSS-канала PowerShell

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

Эта команда использует `Invoke-RestMethod` командлет для получения сведений из RSS-канала блога в блоге PowerShell. Команда использует `Format-Table` командлет для вывода значений свойств **Title** и **pubDate** каждого блога в таблице.

### Пример 2

В следующем примере пользователь запускается `Invoke-RestMethod` для выполнения запроса POST на веб-сайте интрасети в организации пользователя.

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

### Пример 3. Передача нескольких заголовков

В этом примере показано, как передать несколько заголовков из в `hash-table` в REST API.

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

API часто нуждаются в переданных заголовках для проверки подлинности, проверки и т. д.

### Пример 3. Отправка данных формы

Если тело является формой или является выходным результатом другого `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.

Пример:

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## Параметры

### -Body

Задает основной текст запроса. Основной текст — это содержимое запроса, идущее после заголовков.
Можно также передать значение текста по конвейеру в `Invoke-RestMethod` .

Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.

Если входные данные — это запрос GET, а основной текст — IDictionary (обычно это хэш-таблица), основной текст добавляется в URI как параметры запроса. Для других типов запросов (таких как POST) основной текст задается как значение основного текста запроса в стандартном формате имя=значение.

> [!WARNING]
> Подробный вывод тела сообщения POST заканчивается `with -1-byte payload` , даже если размер текста известен и отправляется в `Content-Length` заголовке HTTP.

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

Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске Certificate ( `Cert:` ). Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.

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

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске Windows PowerShell ( `Cert:` ).

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

Если этот параметр пропущен, а метод запроса — POST, `Invoke-RestMethod` устанавливает тип содержимого "Application/x-www-Form-UrlEncoded". В противном случае тип содержимого в вызове не указывается.

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

### -Дисаблекипаливе

Задает значение False для параметра **KeepAlive** в заголовке HTTP. По умолчанию **KeepAlive** имеет значение True.
**KeepAlive** устанавливает постоянное подключение к серверу, чтобы упростить выполнение последующих запросов.

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

### -Заголовки

Задает заголовки веб-запроса. Введите словарь или хэш-таблицу.

Чтобы задать заголовки UserAgent, используйте параметр **UserAgent**. Этот параметр нельзя использовать для указания заголовков UserAgent или файла cookie.

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

### -Максимумредиректион

Определяет, сколько раз Windows PowerShell перенаправляет соединение на альтернативный URI перед сбоем подключения. Значение по умолчанию — 5. Значение 0 (ноль) запрещает любые перенаправления.

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

### -Файл

Сохраняет основной текст ответа в указанный выходной файл. Введите путь и имя файла. Если путь не указан, по умолчанию используется текущее расположение.

По умолчанию `Invoke-RestMethod` возвращает результаты в конвейер. Чтобы отправить результаты в файл и в конвейер, используйте параметр **Passthru**.

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

Возвращает результаты в дополнение к их записи в файл. Этот параметр активен, если в команде также используется параметр **OutFile**.

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

### Прокси-сервер

Использует прокси-сервер для выполнения запроса вместо того, чтобы напрямую подключиться к интернет-ресурсу. Введите URI сетевого прокси-сервера.

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

### -ProxyCredential

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**. По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.

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

### -Проксюседефаулткредентиалс

Использует учетные данные текущего пользователя для доступа к прокси-серверу, который задан параметром **Proxy**.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.

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

### -Сессионвариабле

Создает сеанс веб-запроса и сохраняет его в значении указанной переменной. Введите имя переменной без символа доллара ( `$` ).

При указании переменной сеанса `Invoke-RestMethod` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell. Переменную в сеансе можно использовать сразу после выполнения команды.

В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы использовать сеанс веб-запроса в последующих веб-запросах, укажите переменную сеанса в значении параметра **WebSession**. Windows PowerShell использует данные из объекта сеанса веб-запроса при установке нового подключения. Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**. Значения параметров имеют приоритет над значениями в сеансе веб-запроса.

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

### -TimeoutSec

Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах. Значение по умолчанию, равное 0, указывает неопределенное время ожидания.

Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра TimeoutSec задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде чем будет создано исключение, а время ожидания запроса истечет.

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

Указывает URI интернет-ресурса, на который отправляется веб-запрос. Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.

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

Указывает, что командлет использует базовый синтаксический анализ. Командлет возвращает необработанный код HTML в **строковом** объекте.

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

Использует учетные данные текущего пользователя для отправки веб-запроса.

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

По умолчанию агент пользователя аналогичен Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0 с небольшими вариациями для каждой операционной системы и платформы.

Чтобы проверить веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands) , такие как Chrome, Firefox, Internet Explorer, Opera и Safari.

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

Чтобы переопределить значение в сеансе веб-запроса, используйте параметр командлета, такой как **UserAgent** или **Credential**. Значения параметров имеют приоритет над значениями в сеансе веб-запроса.

В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

Чтобы создать сеанс веб-запроса, введите имя переменной (без знака доллара) в качестве значения параметра **сессионвариабле** `Invoke-RestMethod` команды. `Invoke-RestMethod` создает сеанс и сохраняет его в переменной. В последующих командах используйте переменную в качестве значения параметра **WebSession**.

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

### System.Xml.Xmlдокумент, Microsoft.PowerShell.Commands.HtmЛвебреспонсеобжект, System. String

Выходные данные командлета зависят от формата получаемого содержимого.

### PSObject

Если запрос возвращает строки JSON, `Invoke-RestMethod` возвращает PSObject, представляющий строки.

## Примечания

## Связанные ссылки

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)
