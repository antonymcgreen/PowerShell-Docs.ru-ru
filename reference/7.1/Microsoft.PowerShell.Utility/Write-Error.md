---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: ad9e3daa7d67fc2bec6fa19a873573ce33dc609d
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232850"
---
# Write-Error

## Краткий обзор
Записывает объект в поток ошибок.

## SYNTAX

### Except (по умолчанию)

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### висексцептион

```
Write-Error -Exception <Exception> [[-Message] <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### ерроррекорд

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## DESCRIPTION

`Write-Error`Командлет объявляет неустранимую ошибку. По умолчанию ошибки отправляются в основную программу для отображения вместе с выводом.

Устранимую можно записать путем отправки строки сообщения об ошибке, объекта **ErrorRecord** или объекта **Exception**. Используйте другие параметры `Write-Error` для заполнения записи об ошибке.

Устранимые ошибки записываются в поток, но не прерывают обработку команд.
Если один из элементов в коллекции элементов ввода объявляет устранимую ошибку, команда продолжает обработку других элементов в коллекции.

Чтобы объявить завершающую ошибку, используйте `Throw` ключевое слово.
Дополнительные сведения см. в разделе [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).

## Примеры

### Пример 1. запись ошибки для объекта RegistryKey

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

Эта команда объявляет неустранимую ошибку `Get-ChildItem` , когда командлет возвращает `Microsoft.Win32.RegistryKey` объект, например объекты на `HKLM:` `HKCU:` дисках или поставщика реестра PowerShell.

### Пример 2. запись сообщения об ошибке в консоль

```powershell
Write-Error "Access denied."
```

Эта команда объявляет устранимую ошибку и записывает ошибку «Отказано в доступе». Для задания сообщения в команде используется параметр **Message** , однако, имя параметра **Message** опущено, поскольку указывать его не обязательно.

### Пример 3. запись ошибки в консоль и указание категории

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

Эта команда объявляет устранимую ошибку и указывает ее категорию.

### Пример 4. запись ошибки с помощью объекта исключения

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

Эта команда объявляет устранимую ошибку с помощью объекта **Exception**.

Первая команда создает объект **System.Exception** , используя хэш-таблицу. Объект исключения сохраняется в `$E` переменной. Хэш-таблицу можно использовать для создания любого объекта с конструктором типа, имеющим значение null.

Вторая команда использует `Write-Error` командлет для объявления незавершающей ошибки. Значение параметра **исключения** является объектом **исключения** в `$E` переменной.

## PARAMETERS

### -Category

Задает категорию ошибки. Значение по умолчанию — **NotSpecified**. Допустимые значения для этого параметра:

- NotSpecified
- опенеррор
- клосиррор
- девицееррор
- деадлоккдетектед
- InvalidArgument
- InvalidData
- InvalidOperation
- инвалидресулт
- инвалидтипе
- метадатаеррор
- NotImplemented
- нотинсталлед
- ObjectNotFound
- оператионстоппед
- OperationTimeout
- SyntaxError
- парсереррор
- пермиссиондениед
- ресаурцебуси
- ресаурцеексистс
- ресаурцеунаваилабле
- реадеррор
- WriteError
- фромстдерр
- секуритеррор
- ProtocolError
- коннектионеррор
- аусентикатионеррор
- лимитсексцеедед
- QuotaExceeded
- нотенаблед

Дополнительные сведения о категориях ошибок см. в разделе [ErrorCategory enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### -Категоряктивити

Указывает действие, вызвавшее ошибку.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Категориреасон

Указывает, как или почему действие привело к ошибке.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Категоритаржетнаме

Задает имя объекта, который обрабатывался во время возникновения ошибки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Категоритаржеттипе

Задает тип объекта, который обрабатывался во время возникновения ошибки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Код ошибки

Задает строку идентификатора для идентификации ошибки. Эта строка должны быть уникальной для конкретной ошибки.

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ерроррекорд

Задает объект записи об ошибке. Для описания ошибки используются свойства объекта.

Чтобы создать объект записи об ошибке, используйте `New-Object` командлет или получите объект записи об ошибке из массива в `$Error` автоматической переменной.

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exception

Задает объект исключения, представляющего ошибку. Для описания ошибки используются свойства объекта.

Чтобы создать объект исключения, используйте хэш-таблицу или `New-Object` командлет.

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Message

Задает текст сообщения об ошибке. Если текст содержит пробелы или специальные символы, заключите его в кавычки. Можно также передать строку сообщения в `Write-Error` .

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Рекоммендедактион

Указывает действие, которое должен предпринять пользователь для разрешения или предотвращения ошибки.

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

### -TargetObject

Задает объект, который обрабатывался во время возникновения ошибки. Введите объект, переменную, содержащую объект, или команду, которая получает объект.

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
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

### System.String

Строку, содержащую сообщение об ошибке, можно передать в `Write-Error` .

## Выходные данные

### Объект ошибки

`Write-Error` выполняет запись только в поток ошибок. Он не возвращает никакие объекты.

## ПРИМЕЧАНИЯ

`Write-Error` не изменяет значение `$?` автоматически изменяемой переменной, поэтому не сообщает о неустранимой ошибке. Чтобы сообщить о завершающей ошибке, используйте метод [$PSCmdlet. writeError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) .

## Связанные ссылки

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
