---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227678"
---
# Format-Hex

## Краткий обзор

Отображает файл или другие входные данные в шестнадцатеричном формате.

## SYNTAX

### Путь (по умолчанию)

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### бинпутобжект

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Format-Hex`Командлет отображает файл или другие входные данные в виде шестнадцатеричных значений. Чтобы определить смещение символа от выходных данных, добавьте номер, расположенный слева от строки, к номеру в верхней части столбца для этого символа.

`Format-Hex`Командлет помогает определить тип файла поврежденного файла или файл, который может не иметь расширения имени файла. Можно выполнить этот командлет, а затем прочитать шестнадцатеричные выходные данные, чтобы получить сведения о файле.

При использовании `Format-Hex` для файла командлет игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.

## Примеры

### Пример 1. получение шестнадцатеричного представления строки

Эта команда возвращает шестнадцатеричные значения строки.

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` . Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.

### Пример 2. Поиск типа файла из шестнадцатеричного вывода

В этом примере используется шестнадцатеричный вывод для определения типа файла. Командлет отображает полный путь к файлу и шестнадцатеричные значения.

Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в **файл File. t7f**.

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге, `File.t7f` . Расширение файла `.t7f` является редким, но шестнадцатеричные выходные данные `%PDF` показывают, что это файл PDF.

### Пример 3. Отображение необработанных шестнадцатеричных выходных данных

По умолчанию `Format-Hex` имеет значение Compact для числовых типов данных: однобайтовые или двухбайтовые последовательности используются, если они достаточно малы. **Необработанный** параметр отключает такое поведение.

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

Обратите внимание на разницу в выходных данных. Параметр **RAW** отображает числа в виде 4-байтовых значений (true) для их типов **Int32** .

## PARAMETERS

### -Encoding

Задает кодировку выходных данных. Это относится только к `[string]` входным данным. Параметр не влияет на числовые типы. Значение по умолчанию — `ASCII`.

Для этого параметра допустимы следующие значения:

- `Ascii` Использует кодировку ASCII (7-разрядных).
- `BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.
- `Unicode` Использует UTF-16 с прямым порядком байтов.
- `UTF7` Использует UTF-7.
- `UTF8` Использует UTF-8.
- `UTF32` Использует UTF-32 с прямым порядком байтов.

Символы, не входящие в набор ASCII, выводятся в виде литеральных `?` символов, что приводит к утрате информации.

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Используется для входных данных конвейера. Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .

Поддерживаемые скалярные типы:

- `[string]`
- `[byte]`
- `[int]`, `[int32]`
- `[long]`, `[int64]`

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает полный путь к файлу. Значение **LiteralPath** используется точно так же, как оно введено.
Этот параметр не принимает подстановочные знаки. Чтобы указать несколько путей к файлам, разделяйте пути запятой. Если параметр **LiteralPath** включает escape-символы, заключите путь в одинарные кавычки. PowerShell не интерпретирует символы в одной строке в кавычках как escape-последовательности. Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к файлам. Используйте точку ( `.` ), чтобы указать текущее расположение. Символ-шаблон ( `*` ) принимается и может использоваться для указания всех элементов в расположении. Если параметр **path** включает escape-символы, заключите путь в одинарные кавычки. Чтобы указать несколько путей к файлам, разделяйте пути запятой.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -RAW

По умолчанию `Format-Hex` имеет значение Compact для числовых типов данных: однобайтовые или двухбайтовые последовательности используются, если они достаточно малы. **Необработанный** параметр отключает такое поведение.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
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

Вы можете передать строку в этот командлет по конвейеру.

## Выходные данные

### Microsoft. PowerShell. Commands. Битеколлектион

Этот командлет возвращает **битеколлектион**. Этот объект представляет коллекцию байтов. Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` . Если указать **путь** или параметр **LiteralPath** , объект также будет содержать путь к файлу, содержащему каждый байт.

## ПРИМЕЧАНИЯ

Правый столбец выходных данных пытается визуализировать байты как символы:

Как правило, каждый байт интерпретируется как кодовая точка Юникода, что означает:

- Печатаемые символы ASCII всегда отображаются правильно
- Символы UTF-8 с несколькими байтами никогда не отображаются правильно
- Символы UTF-16 отображаются правильно, только если происходит их старший байт `NUL` .

## Связанные ссылки

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
