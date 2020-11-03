---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: b246e316c209cd66602967d3ad41b03758057192
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226278"
---
# Set-AuthenticodeSignature

## Краткий обзор
Добавляет подпись [Authenticode](/windows-hardware/drivers/install/authenticode) в скрипт PowerShell или другой файл.

## SYNTAX

### ByPath (по умолчанию)

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### биконтент

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-AuthenticodeSignature`Командлет добавляет подпись Authenticode в любой файл, поддерживающий пакет интерфейса субъекта (SIP).

В файле сценария PowerShell сигнатура принимает форму блока текста, который указывает на конец инструкций, выполняемых в скрипте. Если при запуске командлета подпись в файле уже есть, эта подпись удаляется.

## Примеры

### Пример 1. Подписание скрипта с помощью сертификата из локального хранилища сертификатов

Эти команды извлекают сертификат подписи кода из поставщика сертификата PowerShell и используют его для подписания скрипта PowerShell.

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

Первая команда использует `Get-ChildItem` командлет и поставщик сертификата PowerShell для получения сертификатов в `Cert:\CurrentUser\My` подкаталоге хранилища сертификатов. `Cert:`Диск — это диск, предоставляемый поставщиком сертификатов. Параметр **CodeSigningCert** , который поддерживается только поставщиком сертификатов, ограничивает доступ к сертификатам, получаемым с помощью центра подписывания кода. Команда сохраняет результат в `$cert` переменной.

Вторая команда использует `Set-AuthenticodeSignature` командлет для подписи `PSTestInternet2.ps1` скрипта. Он использует параметр **FilePath** , чтобы указать имя скрипта и параметр **сертификата** , чтобы указать, что сертификат хранится в `$cert` переменной.

> [!NOTE]
> Использование параметра **CodeSigningCert** с параметрами `Get-ChildItem` возвращает только сертификаты, которые имеют центр подписи кода и содержат закрытый ключ. Если закрытый ключ отсутствует, сертификаты не могут использоваться для подписывания.

### Пример 2. Подписание сценария с помощью сертификата из PFX-файла

Эти команды используют `Get-PfxCertificate` командлет для загрузки сертификата подписи кода. Затем используйте его для подписания скрипта PowerShell.

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

Первая команда использует `Get-PfxCertificate` командлет для загрузки сертификата к:\тест\мисигн.пфкс в `$cert` переменную.

Вторая команда использует `Set-AuthenticodeSignature` для подписания скрипта. Параметр **FilePath** параметра `Set-AuthenticodeSignature` указывает путь к подписанному файлу скрипта, а параметр **CERT** передает `$cert` переменную, содержащую сертификат `Set-AuthenticodeSignature` .

Если файл сертификата защищен паролем, PowerShell запрашивает пароль.

### Пример 3. Добавление подписи, включающей корневой центр

Эта команда добавляет цифровую подпись, включающую корневой центр в цепочке доверия, и подпись стороннего сервера отметок времени.

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

Команда использует параметр **FilePath** для указания подписанного скрипта, а параметр **сертификата** — для указания сертификата, сохраненного в `$cert` переменной. Он использует параметр **инклудечаин** для включения всех подписей в цепочку доверия, включая корневой центр. Он также использует параметр **тиместампсервер** для добавления метки времени к сигнатуре.
Это защищает скрипт от сбоя, если срок действия сертификата истек.

## PARAMETERS

### — Сертификат

Задает сертификат, который будет использоваться для подписания скрипта или файла. Введите переменную, в которой хранится объект, представляющий сертификат, или выражение, которое получает сертификат.

Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске с сертификатом `Cert:` . Если сертификат недействителен или не имеет `code-signing` полномочий, команда завершается ошибкой.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает путь к подписываемому файлу.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

Позволяет командлету добавлять подпись в файл, доступный только для чтения. Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.

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

### -HashAlgorithm

Задает алгоритм хэширования, который использует Windows для расчета цифровой подписи для файла.

Для PowerShell 3,0 значение по умолчанию — SHA256, то есть алгоритм хэширования Windows по умолчанию. Для PowerShell 2,0 значение по умолчанию — SHA1. Файлы, подписанные с использованием другого алгоритма хэширования, могут не распознаваться в других системах. Поддерживаемые алгоритмы зависят от версии операционной системы.

Список возможных значений см. в разделе [Структура хашалгорисмнаме](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инклудечаин

Определяет, какие сертификаты в цепочке доверия сертификатов включаются в цифровую подпись.
По умолчанию используется **нотрут** .

Допустимые значения:

- Подписавший: включает только сертификат подписывания.
- Нотрут: включает все сертификаты в цепочке сертификатов, за исключением корневого центра сертификации.
- Все: включает все сертификаты в цепочке сертификатов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### -Тиместампсервер

Добавляет к подписи отметку времени, использует заданный сервер отметок времени. Введите URL-адрес сервера отметок времени в виде строки.

Отметка времени представляет собой значение точного времени, когда сертификат был добавлен в файл. Отметка времени защищает скрипт от сбоев в случае истечения срока действия сертификата, поскольку пользователи и программы могут проверить, что сертификат действовал в момент подписания.

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

### -LiteralPath

Указывает путь к подписываемому файлу. В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Саурцепасорекстенсион

Путь к файлу или типу файла содержимого, для которого добавляется цифровая подпись. Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### — Содержимое

Содержимое файла в виде массива байтов, для которого добавляется цифровая подпись. Этот параметр должен использоваться с параметром **саурцепасорекстенсион** . Содержимое файла должно быть в формате Unicode (UTF-16LE).

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую путь к файлу, можно передать по конвейеру `Set-AuthenticodeSignature` .

## Выходные данные

### System. Management. Automation. Signature

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Get-PfxCertificate](Get-PfxCertificate.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
