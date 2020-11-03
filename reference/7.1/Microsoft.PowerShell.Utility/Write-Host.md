---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: 47a4d9bb66e3e6c3267bbdf18f41c8af8e5448f0
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "93230638"
---
# Write-Host

## Краткий обзор

Записывает пользовательские выходные данные в узел.

## SYNTAX

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## DESCRIPTION

`Write-Host`Основным предназначением командлета является создание для (узла) вывода только для просмотра, например при выводе запроса на ввод в сочетании с [чтением-узлом](Read-Host.md).
`Write-Host` использует метод [ToString ()](/dotnet/api/system.object.tostring) для записи выходных данных. Напротив, для вывода данных в конвейер используйте [Write-Output](Write-Output.md) или неявные выходные данные.

Можно указать цвет текста с помощью `ForegroundColor` параметра, а цвет фона можно указать с помощью `BackgroundColor` параметра. Параметр Separator позволяет указать строку, которая будет использоваться для разделения отображаемых объектов. Конкретный результат зависит от программы, в которой размещается PowerShell.

> [!NOTE]
> Начиная с Windows PowerShell 5,0, `Write-Host` — это оболочка для этого, которая `Write-Information` позволяет использовать `Write-Host` для отправки выходных данных в информационный поток. Это позволяет **записывать** или **подавить** данные, написанные с помощью, сохраняя `Write-Host` обратную совместимость.
>
> `$InformationPreference`Привилегированная переменная и `InformationAction` общий параметр не влияют на `Write-Host` сообщения. Исключением из этого правила является `-InformationAction Ignore` , которое фактически подавляет `Write-Host` вывод. (см. "Пример 5")

## Примеры

### Пример 1. запись в консоль без добавления новой строки

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

Эта команда отображает строку "без теста для новой строки" с `NoNewline` параметром.

Записывается вторая строка, но она завершается на той же строке, что и первая из-за отсутствия строки, разделяющей строку.

### Пример 2. запись в консоль и добавление разделителя

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Эта команда отображает четные числа от двух до двенадцати. Параметр **разделителя** используется для добавления строки `, +2= ` (запятая, пробел,,, `+` `2` `=` , пробел).

### Пример 3. запись с другими цветами текста и фона

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

Эта команда отображает четные числа от двух до двенадцати. Он использует `ForegroundColor` параметр для вывода темно-зеленого текста, а `BackgroundColor` параметр — для показа белого фона.

### Пример 4. запись с различными цветами текста и фона

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

Эта команда выводит строку Red on white text. Текст имеет красный цвет, как определено `ForegroundColor` параметром. Фон является белым, как определено `BackgroundColor` параметром.

### Пример 5. Отключение вывода от Write-Host

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

Эти команды эффективно подавляют вывод `Write-Host` командлета. В первом из них используется `InformationAction` параметр со `Ignore` значением для подавления вывода в информационный поток.
Во втором примере поток информации команды переправляется в `$null` переменную и, таким образом, подавляется.

## PARAMETERS

### -BackgroundColor

Определяет цвет фона. Значение по умолчанию отсутствует. Допустимые значения для этого параметра:

- Черный
- даркблуе
- даркгрин
- даркциан
- даркред
- даркмажента
- даркеллов
- Серый
- даркграй
- Синий
- Зеленый
- Цвет
- Красный
- Пурпурный
- Желтый
- White

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForegroundColor

Определяет цвет текста. Значение по умолчанию отсутствует. Допустимые значения для этого параметра:

- Черный
- даркблуе
- даркгрин
- даркциан
- даркред
- даркмажента
- даркеллов
- Серый
- даркграй
- Синий
- Зеленый
- Цвет
- Красный
- Пурпурный
- Желтый
- White

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Новая строка

Строковые представления входных объектов сцепляются для формирования выходных данных. Между выходными строками не вставляются пробелы и символы новой строки. После последней выходной строки не добавляется новая строка.

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

### -Object

Объекты, отображаемые на узле.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Separator

Задает разделительную строку для вставки между объектами, отображаемыми узлом.

```yaml
Type: System.Object
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

Объекты, которые необходимо записать в хост, можно передавать по конвейеру.

## Выходные данные

### Нет

`Write-Host` отправляет объекты на узел. Он не возвращает никакие объекты. Однако узел отображает объекты, которые `Write-Host` отправляются в него.

## ПРИМЕЧАНИЯ

- При записи коллекции на узел элементы коллекции выводятся на той же строке, разделенной одним пробелом. Это можно переопределить с помощью параметра **разделителя** .

- Типы данных, отличные от примитивов, такие как объекты со свойствами, могут вызвать непредвиденные результаты и не предоставить осмысленные выходные данные. Например, `Write-Host @{a = 1; b = 2}` выполнит печать `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` на узле.

## Связанные ссылки

[Clear-Host;](../Microsoft.PowerShell.Core/Clear-Host.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Write-Debug](Write-Debug.md)

[Ошибка записи](Write-Error.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
