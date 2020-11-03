---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: a64b11206a0755cedabad2894ecc330fac95a8d5
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "93230733"
---
# Out-String

## Краткий обзор
Выводит входные объекты в виде строк.

## SYNTAX

### Ноневлинеформаттинг (по умолчанию)

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### стреамформаттинг

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`Out-String`Командлет преобразует входные объекты в строки. По умолчанию `Out-String` накапливает строки и возвращает их в виде одной строки, но можно использовать параметр **Stream** , чтобы направить `Out-String` Возврат по одной строке за раз или создать массив строк. Этот командлет позволяет управлять строковым выводом и выполнять в нем поиск, как при работе с традиционными оболочками, если использовать объектов неудобно.

## Примеры

### Пример 1. Получение текущего языка и региональных параметров и преобразование данных в строки

Этот пример возвращает региональные параметры текущего пользователя и преобразует данные объекта в строки.

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

`$C`Переменная хранит **Selected.SysTEM. Объект Globalization. CultureInfo** . Объект является результатом `Get-Culture` отправки выходных данных в конвейер `Select-Object` . Параметр **Property** использует `*` подстановочный знак звездочки (), чтобы указать все свойства, содержащиеся в объекте.

`Out-String` использует параметр **InputObject** для указания объекта **CultureInfo** , хранящегося в `$C` переменной. Объекты в `$C` преобразуются в строку.

> [!NOTE]
> Чтобы просмотреть `Out-String` массив, сохраните выходные данные в переменную и используйте индекс массива для просмотра элементов. Дополнительные сведения об индексе массива см. в разделе [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).
>
> `$str = Out-String -InputObject $C -Width 100`

### Пример 2. Работа с объектами

В этом примере показано различие между работой с объектами и работой со строками. Команда отображает псевдоним, который содержит текст **gcm** , псевдоним для `Get-Command` .

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

`Get-Alias` Возвращает объекты **System. Management. Automation. AliasInfo** , по одному для каждого псевдонима, и отправляет объекты по конвейеру. `Out-String` использует параметр **Stream** для преобразования каждого объекта в строку, вместо того чтобы объединить все объекты в одну строку. Объекты **System. String** отправляются в конвейер и `Select-String` используют параметр **pattern** для поиска совпадений для текста **gcm** .

> [!NOTE]
> Если опустить параметр **Stream** , команда выводит все псевдонимы, так как `Select-String` находит текст **gcm** в одной строке, которая `Out-String` возвращает.

### Пример 3. Использование параметра Width для предотвращения усечения.

Хотя большинство выходных данных из `Out-String` переносится на следующую строку, существуют сценарии, в которых выходные данные усекаются системой форматирования перед передачей в `Out-String` . Можно избежать усечения с помощью параметра **Width** .

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## PARAMETERS

### -InputObject

Указывает объекты для записи в строку. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Новая строка

Удаляет все символы новой строки из выходных данных, созданных модулем форматирования PowerShell. Символы новой строки, которые являются частью строковых объектов, сохраняются.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stream

Указывает, что командлет отправляет отдельную строку для каждой строки входного объекта. По умолчанию строки для каждого объекта накапливаются и отправляются в виде одной строки.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Width

Указывает количество символов в каждой строке выходных данных. Все дополнительные символы упаковываются в следующую строку или усекаются в зависимости от используемого командлета модуля форматирования. Параметр **Width** применяется только к отформатированным объектам. Если данный параметр не указан, ширина определяется характеристиками основного приложения. В окнах терминала (консоли) в качестве значения по умолчанию используется текущая ширина окна. В окнах консоли PowerShell по умолчанию устанавливается ширина 80 символов при установке.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объекты можно отправить по конвейеру в `Out-String` .

## Выходные данные

### System.String

`Out-String` Возвращает строку, которая создается из входного объекта.

## ПРИМЕЧАНИЯ

Командлеты, содержащие `Out` команду, не отформатируют объекты. `Out`Командлеты отправляют объекты в модуль форматирования для указанного отображаемого назначения.

## Связанные ссылки

[about_Formatting](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[Out-Default;](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-File](Out-File.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-GridView](Out-GridView.md)

[Out-Printer](Out-Printer.md)
