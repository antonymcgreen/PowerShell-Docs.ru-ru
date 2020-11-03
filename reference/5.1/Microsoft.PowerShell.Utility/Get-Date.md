---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: f550d352ca6e400307feba9ec16cea4632603b62
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230525"
---
# Get-Date

## Краткий обзор
Получает текущую дату и время.

## SYNTAX

### net (по умолчанию)

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### UFormat

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Date`Командлет возвращает объект **DateTime** , представляющий текущую дату или указанную дату. `Get-Date` может форматировать дату и время в нескольких форматах .NET и UNIX. Можно использовать `Get-Date` для создания строки символов даты или времени, а затем отправить строку другим командлетам или программам.

`Get-Date` использует параметры языка и региональных параметров компьютера для определения формата выходных данных. Чтобы просмотреть параметры компьютера, используйте `(Get-Culture).DateTimeFormat` .

## Примеры

### Пример 1. Получение текущей даты и времени

В этом примере `Get-Date` выводит текущую системную дату и время. Выходные данные имеют формат длинной даты и длительное время.

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### Пример 2. Получение элементов текущей даты и времени

В этом примере показано, как использовать `Get-Date` для получения элемента даты или времени. Параметр использует аргументы **Date** , **time** или **DateTime** .

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

`Get-Date` использует параметр **дисплайхинт** с аргументом **Date** , чтобы получить только дату.

### Пример 3. Получение даты и времени с помощью описателя формата .NET

В этом примере используется описатель формата .NET для настройки формата вывода. Выходные данные представляют собой **строковый** объект.

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

`Get-Date` использует параметр **Format** для указания нескольких описателей формата.

Описатели формата .NET, используемые в этом примере, определяются следующим образом:

| Описатель | Определение |
| --- | --- |
| `dddd` | День недели — полное имя |
| `MM` | Номер месяца. |
| `dd` | День месяца-2 цифры |
| `yyyy` | Год в 4-значном формате |
| `HH:mm` | Время в 24-часовом формате — нет секунд |
| `K` | Смещение часового пояса от универсальной координаты времени (UTC) |

Дополнительные сведения о спецификаторах формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

### Пример 4. Получение даты и времени с помощью описателя UFormat

В этом примере для настройки формата вывода используются несколько описателей формата **UFormat** .
Выходные данные представляют собой **строковый** объект.

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

`Get-Date` использует параметр **UFormat** для указания нескольких описателей формата.

Описатели формата **UFormat** , используемые в этом примере, определяются следующим образом:

| Описатель | Определение |
| --- | --- |
| `%A` | День недели — полное имя |
| `%m` | Номер месяца. |
| `%d` | День месяца-2 цифры |
| `%Y` | Год в 4-значном формате |
| `%R` | Время в 24-часовом формате — нет секунд |
| `%Z` | Смещение часового пояса от универсальной координаты времени (UTC) |

Список допустимых описателей формата **UFormat** см. в разделе " [Примечания](#notes) ".

### Пример 5. получение дня года для даты

В этом примере свойство используется для получения числового дня года.

В григорианском календаре 365 дней, за исключением високосных лет, имеющих 366 дней. Например, 31 декабря 2020 — это день 366.

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

`Get-Date` использует три параметра для указания даты: **год** , **месяц** и **день** . Команда заключена в круглые скобки, поэтому результат вычисляется свойством **DayofYear** .

### Пример 6. Проверка того, скорректирована ли дата на летнее время

В этом примере используется логический метод для проверки, корректируется ли дата на летнее время.

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

Переменная, `$DST` в которой хранится результат `Get-Date` . `$DST` проверяет, корректируется ли дата на летнее время, с помощью метода **исдайлигхтсавингтиме** .

### Пример 7. Преобразование текущего времени в время в формате UTC

В этом примере текущее время преобразуется в время в формате UTC. Для преобразования времени используется смещение в формате UTC для языкового стандарта системы. В таблице в разделе " [Примечания](#notes) " перечислены допустимые описатели формата **UFormat** .

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

`Get-Date` использует параметр **UFormat** с описателями формата для вывода текущей системной даты и времени. Описатель формата **% Z** представляет смещение в формате UTC, равное **-07** .

`$Time`Переменная хранит текущую системную дату и время. `$Time` использует метод **ToUniversalTime ()** для преобразования времени на основе смещения UTC компьютера.

### Пример 8. Создание метки времени

В этом примере описатель формата создает объект **строки** метки времени для имени каталога. Метка времени включает дату, время и смещение в формате UTC.

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

`$timestamp`Переменная хранит результаты выполнения `Get-Date` команды. `Get-Date` использует параметр **Format** с описателем формата "нижний регистр" `o` для создания объекта **строки** метки времени. Объект отправляется по конвейеру в `ForEach-Object` . Блок **ScriptBlock** содержит `$_` переменную, представляющую текущий объект конвейера. Строка метки времени разделяются двоеточиями, которые заменяются точками.

`New-Item` использует параметр **path** для указания расположения нового каталога. Путь включает `$timestamp` переменную в качестве имени каталога. Параметр **типа** указывает, что каталог создан.

## PARAMETERS

### -Date

Указывает дату и время. Время является необязательным и, если не указано, возвращает 00:00:00.

Введите дату и время в формате, стандартном для национальной настройки системы.

Например, на английском языке США:

`Get-Date -Date "6/25/2019 12:30:22"` Возвращает вторник, 25 июня 2019 12:30:22

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Day

Указывает выводимый день месяца. Введите значение от 1 до 31.

Если указанное значение больше числа дней в месяце, PowerShell добавляет число дней в месяц. Например, `Get-Date -Month 2 -Day 31` отображается **3 марта** , а не **31 февраля** .

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

### -DisplayHint

Определяет, какие элементы даты и времени будут отображаться.

Допустимы следующие значения:

- **Date:** отображается только дата;
- **Time:** отображается только время;
- **DateTime:** отображаются дата и время.

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format

Выводит дату и время в формате Microsoft .NET Framework, определяемом спецификатором формата.
Параметр **Format** выводит **строковый** объект.

Список доступных описателей формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

При использовании параметра **Format** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты. Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.

Начиная с PowerShell 5,0, в качестве значений параметра **Format** можно использовать следующие дополнительные форматы.

- **Филедате** . Представление текущей даты в формате местного времени в файле или пути. Формат (с `yyyyMMdd` учетом регистра, с использованием 4-значного года, 2-значный месяц и день в 2 цифры). Пример:
  20190627.

- **Филедатеуниверсал** . Представление текущей даты в формате UTC в виде файла или пути. Формат (с `yyyyMMddZ` учетом регистра, с использованием 4-разрядного года, месяца, 2 цифры и буквы в `Z` качестве индикатора времени в формате UTC). Например: 20190627Z.

- **Филедатетиме** . Представление текущей даты и времени по местному времени в 24-часовом формате в виде файла или пути. Формат (с `yyyyMMddTHHmmssffff` учетом регистра, с использованием 4-разрядного года, 2-значный месяц, с двумя цифрами, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда и 4-значная миллисекунда). Например: 20190627T0840107271.

- **Филедатетимеуниверсал** . Представление текущей даты и времени в формате UTC в 24-часовом виде файла или пути. Формат (с `yyyyMMddTHHmmssffffZ` учетом регистра, с использованием 4-разрядного года, 2-значного месяца, буквы в 2 цифры, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда, 4-разрядная миллисекунда и букву в `Z` качестве индикатора времени в формате UTC). Например: 20190627T1540500718Z.

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hour

Указывает выводимый час. Введите значение от 0 до 23.

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

### -Millisecond

Указывает миллисекунды в дате. Введите значение от 0 до 999.

Этот параметр появился в PowerShell 3,0.

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

### -Minute

Указывает выводимую минуту. Введите значение от 0 до 59.

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

### -Month

Указывает выводимый месяц. Введите значение от 1 до 12.

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

### -Second

Указывает выводимую секунду. Введите значение от 0 до 59.

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

### -UFormat

Выводит дату и время в формате UNIX. Параметр **UFormat** выводит строковый объект.

Спецификаторам **UFormat** предшествует знак процента (), например,, `%` `%m` `%d` и `%Y` . В разделе " [Примечания](#notes) " содержится таблица допустимых **описателей UFormat** .

При использовании параметра **UFormat** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты. Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Year

Указывает выводимый год. Введите значение от 1 до 9999.

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

### Входные данные конвейера

`Get-Date` принимает входные данные конвейера. Например, `Get-ChildItem | Get-Date`.

## Выходные данные

### System.DateTime или System.String

`Get-Date` Возвращает объект **DateTime** , за исключением случаев, когда используются параметры **Format** и **UFormat** . Параметры **Format** или **UFormat** возвращают **строковые** объекты.

Когда объект **DateTime** отправляется по конвейеру в командлет, например, при `Add-Content` ожидании ввода строки, PowerShell преобразует объект в **строковый** объект.

Метод `(Get-Date).ToString()` преобразует объект **DateTime** в объект **String** .

Чтобы отобразить свойства и методы объекта, отправьте объект по конвейеру в `Get-Member` .
Например, `Get-Date | Get-Member`.

## ПРИМЕЧАНИЯ

Объекты **DateTime** имеют формат длинной даты и длительное время для национальной настройки системы.

В следующей таблице показаны допустимые **описатели UFormat** .

| Описатель формата |                                 Значение                     |         Пример          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | День недели — полное имя                                             | Понедельник                   |
| `%a` | День в сокращенном названии недели                                      | Mon                      |
| `%B` | Имя месяца — полное                                                       | Январь                  |
| `%b` | Название месяца — сокращенное                                                | Январь                      |
| `%C` | Век                                                                 | 20 для 2019              |
| `%c` | Дата и время-сокращенные                                             | Четверг июня 27 08:44:18 2019 |
| `%D` | Дата в формате мм/дд/гг                                                 | 06/27/19                 |
| `%d` | День месяца-2 цифры                                             | 05                       |
| `%e` | День месяца — цифра, предшествующая пробелом                            | \<space\>5.0               |
| `%G` | То же, что "Y"                                                             |                          |
| `%g` | То же, что "y"                                                             |                          |
| `%H` | Час в 24-часовом формате                                                  | 17                       |
| `%h` | То же, что "b"                                                             |                          |
| `%I` | Час в 12-часовом формате                                                  | 05                       |
| `%j` | День года                                                         | 1-366                    |
| `%k` | То же, что "H"                                                             |                          |
| `%l` | То же, что "I" (верхний регистр I)                                              | 05                       |
| `%M` | Минуты                                                                 | 35                       |
| `%m` | Номер месяца.                                                            | 06                       |
| `%n` | символ новой строки                                                       |                          |
| `%p` | AM или PM                                                                |                          |
| `%R` | Время в 24-часовом формате — нет секунд                                      | 17:45                    |
| `%r` | Время в 12-часовом формате                                                  | 09:15:36 AM              |
| `%S` | Секунды                                                                 | 05                       |
| `%s` | Секунды, прошедшие с 1 января 1970 00:00:00                          | 1150451174,95705         |
| `%t` | Символ горизонтальной табуляции                                                |                          |
| `%T` | Время в 24-часовом формате                                                  | 17:45:52                 |
| `%U` | То же, что "W"                                                             |                          |
| `%u` | День недели — номер                                                | Воскресенье = 0               |
| `%V` | Неделя года                                                        | 01-53                    |
| `%w` | То же, что и "u"                                                             |                          |
| `%W` | Неделя года                                                        | 00-52                    |
| `%X` | То же, что 'T»                                                             |                          |
| `%x` | Дата в стандартном формате для языкового стандарта                                      | 06/27/19 для английского языка США  |
| `%Y` | Год в 4-значном формате                                                  | 2019                     |
| `%y` | Год в формате 2 цифр                                                  | 19                       |
| `%Z` | Смещение часового пояса от универсальной координаты времени (UTC)                   | -07                      |

## Связанные ссылки

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Culture](Get-Culture.md)

[Get-Member](Get-Member.md)

[New-Item](../Microsoft.PowerShell.Management/New-Item.md)

[New-TimeSpan](New-TimeSpan.md)

[Set-Date](Set-Date.md)
