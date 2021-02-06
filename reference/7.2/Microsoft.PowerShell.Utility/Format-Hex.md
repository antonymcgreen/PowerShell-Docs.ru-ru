---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: a45e7919b5a24189ca7f50661795ff035c38a037
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602700"
---
# Format-Hex

## Краткий обзор

Отображает файл или другие входные данные в шестнадцатеричном формате.

## SYNTAX

### Путь

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### бинпутобжект

```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
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
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` . Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.

### Пример 2. Поиск типа файла из шестнадцатеричного вывода

В этом примере используется шестнадцатеричный вывод для определения типа файла. Командлет отображает полный путь к файлу и шестнадцатеричные значения.

Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в `File.t7f` .

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге, `File.t7f` . Расширение файла `.t7f` является редким, но шестнадцатеричные выходные данные `%PDF` показывают, что это файл PDF. В этом примере параметр **Count** используется для ограничения выходных данных до первых 48 байт файла.

### Пример 3. форматирование массива различных типов данных

В этом примере используется массив различных типов данных для выделения `Format-Hex` их обработки в конвейере.

Он будет передавать каждый объект через конвейер и обрабатывать его по отдельности. Однако если это числовые данные, а смежный объект также является числовым, он будет сгруппирован в один выходной блок.

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾-Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## PARAMETERS

### -Encoding

Задает кодировку входных строк. Это относится только к `[string]` входным данным. Параметр не влияет на числовые типы. Выходное значение всегда равно `utf8NoBOM` .

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> Больше не рекомендуется использовать **UTF-7** _. В PowerShell 7,1 записывается предупреждение, если указано `utf7` для параметра _ *Encoding**.

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Используется для входных данных конвейера. Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .

Поддерживаемые скалярные типы:

- `[string]`, `[char]`
- `[byte]`, `[sbyte]`
- `[int16]`, `[uint16]`, `[short]`, `[ushort]`
- `[int]`, `[uint]`, `[int32]`, `[uint32]`,
- `[long]`, `[ulong]`, `[int64]`, `[uint64]`
- `[single]`, `[float]`, `[double]`
- `[boolean]`

До выхода версии PowerShell 6,2 `Format-Hex` обрабатывает входные данные конвейера с несколькими типами входных данных, объединяя все объекты, аналогичные. Теперь он обрабатывает каждый отдельный объект по мере его прохождения через конвейер и не будет группировать объекты вместе, если они не являются смежными объектами.

```yaml
Type: System.Management.Automation.PSObject
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
Aliases: PSPath, LP

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

Этот параметр больше не выполняет никаких действий. Он сохраняется для совместимости скриптов.

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

### -Offset

Представляет число байтов, которые нужно пропустить, после которого они являются частью шестнадцатеричного вывода.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### — Количество

Представляет число байтов, включаемых в Шестнадцатеричный вывод.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
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

Этот командлет возвращает **битеколлектион**. Этот объект представляет коллекцию байтов. Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` . В выходных данных также указывается тип обрабатываемых байтов. При указании параметра **path** или **LiteralPath** объект содержит путь к файлу, содержащему каждый байт. Если передать строку, логическое значение, целое число и т. д., она будет помечена соответствующим образом.

## ПРИМЕЧАНИЯ

Правый столбец выходных данных пытается отобразить байты как символы ASCII:

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

