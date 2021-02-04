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
# Invoke-WebRequest

## Краткий обзор
Получает содержимое с веб-страницы в Интернете.

## SYNTAX

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-WebRequest`Командлет отправляет запросы HTTP, HTTPS, FTP и файлы на веб-страницу или веб-службу.
Он анализирует ответ и возвращает коллекции форм, ссылок, изображений и других значимых HTML-элементов.

Этот командлет впервые появился в Windows PowerShell 3.0.

> [!NOTE]
> По умолчанию код сценария на веб-странице может выполняться при синтаксическом анализе страницы для заполнения `ParsedHtml` Свойства.
> `-UseBasicParsing`Чтобы отключить это действие, используйте параметр.

## Примеры

### Пример 1. Отправка веб-запроса

Эта команда использует `Invoke-WebRequest` командлет для отправки веб-запроса на сайт Bing.com.

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

Первая команда выдает запрос и сохраняет ответ в `$R` переменной.

Вторая команда фильтрует объекты в свойстве **аллелементс** , где свойство **Name** имеет значение "* value", а **TagName** — "input". Отфильтрованные результаты передаются в, `Select-Object` чтобы выбрать свойства " **имя** " и " **значение** ".

### Пример 2. Использование веб-службы с отслеживанием состояния

В этом примере показано, как использовать `Invoke-WebRequest` командлет с веб-службой с отслеживанием состояния, например Facebook.

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

Первая команда использует `Invoke-WebRequest` командлет для отправки запроса на вход. Команда задает значение "FB" в качестве значения параметра **сессионвариабле** и сохраняет результат в `$R` переменной. После выполнения команды `$R` переменная содержит **хтмлвебреспонсеобжект** , а `$FB` переменная содержит объект **вебрекуестсессион** .

После того как `Invoke-WebRequest` командлет войдет в Facebook, свойство **StatusDescription** объекта веб-ответа в `$R` переменной указывает, что пользователь успешно выполнил вход.

### Пример 3. получение ссылок с веб-страницы

Эта команда возвращает ссылки с веб-страницы.

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

`Invoke-WebRequest`Командлет возвращает содержимое веб-страницы. Затем свойство **Links** возвращаемого **хтмлвебреспонсеобжект** используется для вывода свойства **href** каждой ссылки.

### Пример 4. перехват сообщений без успешности Invoke-WebRequest

При `Invoke-WebRequest` обнаружении сообщения HTTP, не являющегося успешным (404, 500 и т. д.), оно не возвращает выходные данные и вызывает ошибку, которая завершается. Чтобы перехватить ошибку и просмотреть **StatusCode** , можно заключить выполнение в `try/catch` блок. В следующем примере показано, как это сделать.

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

### -Body

Задает основной текст запроса.
Основной текст — это содержимое запроса, идущее после заголовков.
Можно также передать значение текста по конвейеру в `Invoke-WebRequest` .

Параметр **Body** используется для указания списка параметров запроса или указания содержимого ответа.

Если входные данные являются запросом GET, а тело является **IDictionary** (как правило, хэш-таблицей), текст добавляется в универсальный код ресурса (URI) в качестве параметров запроса. Для других запросов GET текст задается как значение текста запроса в стандартном `name=value` формате.

Если тело является формой или является выходным результатом `Invoke-WebRequest` вызова, то PowerShell устанавливает содержимое запроса в поля формы.
Пример:

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- или

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

### — Сертификат

Задает сертификат клиента, который используется для выполнения защищенного веб-запроса. Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.

Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске **Certificate** ( `Cert:` ). Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.

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

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для отправки запроса. Введите отпечаток сертификата. Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .

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

Если этот параметр пропущен и метод Request является POST, `Invoke-WebRequest` устанавливает тип содержимого application/x-www-Form-UrlEncoded. В противном случае тип содержимого в вызове не указывается.

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

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -Заголовки

Задает заголовки веб-запроса. Введите словарь или хэш-таблицу.

Чтобы задать заголовки **UserAgent** , используйте параметр **UserAgent** . Этот параметр нельзя использовать для указания заголовков **UserAgent** или cookie.

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

### -Method

Задает метод, используемый для веб-запроса. Допустимые значения для этого параметра:

- По умолчанию
- DELETE
- Получить
- Head
- Объединить
- Варианты
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Файл

Указывает выходной файл, для которого этот командлет сохраняет текст ответа. Введите путь и имя файла.
Если путь не указан, по умолчанию используется текущее расположение.

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

### Прокси-сервер

Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.
Введите URI сетевого прокси-сервера.

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

Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.

Этот параметр допустим только в том случае, если параметр **прокси-сервера** также используется в команде. Нельзя использовать параметры **ProxyCredential** и **ProxyUseDefaultCredentials** в одной команде.

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

### -Проксюседефаулткредентиалс

Указывает, что командлет использует учетные данные текущего пользователя для доступа к прокси-серверу, указанному параметром **прокси-** сервера.

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

Указывает переменную, для которой этот командлет создает сеанс веб-запроса и сохраняет его в значении.
Введите имя переменной без символа доллара ( `$` ).

При указании переменной сеанса `Invoke-WebRequest` создает объект сеанса веб-запроса и назначает его переменной с указанным именем в сеансе PowerShell. Переменную в сеансе можно использовать сразу после выполнения команды.

В отличие от удаленного сеанса сеанс веб-запроса не является постоянным подключением. Это объект, содержащий сведения о подключении и запросе, включая файлы cookie, учетные данные, максимальное число перенаправлений и строку агента пользователя. Его можно использовать для обмена состоянием и данными между веб-запросами.

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

### -TimeoutSec

Указывает, как долго запрос может быть отложен до истечения времени ожидания. Введите значение в секундах. Значение по умолчанию, равное 0, указывает неопределенное время ожидания.

Возвращение или истечение времени ожидания DNS-запрос может занять до 15 секунд. Если запрос содержит имя узла, для которого требуется разрешение, а для параметра **TimeoutSec** задано значение больше нуля, но менее 15 секунд, это может занять 15 секунд или более, прежде **чем будет создано исключение,** а время ожидания запроса истечет.

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

Указывает URI интернет-ресурса, на который отправляется веб-запрос. Введите URI. Этот параметр поддерживает значения HTTP, HTTPS, FTP и FILE.

Это обязательный параметр.

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

Указывает, что командлет использует объект Response для HTML-содержимого без синтаксического анализа модель DOM (DOM). Этот параметр является обязательным, если на компьютерах не установлен Internet Explorer, например, в случае установки основных серверных компонентов операционной системы Windows Server.

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

Указывает, что кмдет использует учетные данные текущего пользователя для отправки веб-запроса.

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

Указывает строку агента пользователя для веб-запроса. Агент пользователя по умолчанию аналогичен `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` небольшому варианту для каждой операционной системы и платформы.

Чтобы протестировать веб-сайт со стандартной строкой агента пользователя, используемой большинством браузеров Интернета, используйте свойства класса [псусеражент](/dotnet/api/microsoft.powershell.commands.psuseragent) , такие как Chrome, Firefox, InternetExplorer, Opera и Safari. Например, следующая команда использует строку агента пользователя для Internet Explorer.

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

Чтобы создать сеанс веб-запроса, введите имя переменной (без знака доллара) в качестве значения параметра **сессионвариабле** `Invoke-WebRequest` команды. `Invoke-WebRequest` создает сеанс и сохраняет его в переменной. В последующих командах используйте переменную в качестве значения параметра **WebSession**.

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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Object

Текст веб-запроса можно передать в `Invoke-WebRequest` .

## Выходные данные

### Microsoft.PowerShell.Commands.HtmЛвебреспонсеобжект

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
