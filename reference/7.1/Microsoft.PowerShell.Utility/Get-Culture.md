---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: 6cadebfbcdc8cc7a333d62c3c7b9ff5fb6635168
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239835"
---
# Get-Culture

## Краткий обзор
Получает текущий язык и региональные параметры, установленные в операционной системе.

## SYNTAX

### CurrentCulture (по умолчанию)

```
Get-Culture [-NoUserOverrides] [<CommonParameters>]
```

### name

```
Get-Culture [-Name <String[]>] [-NoUserOverrides] [<CommonParameters>]
```

### ListAvailable

```
Get-Culture [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

`Get-Culture`Командлет возвращает сведения о текущих параметрах языка и региональных параметров. Сюда входят сведения о текущих языковых настройках, например раскладке клавиатуры, и формате отображения элементов, например чисел, валют и дат.

Можно также использовать `Get-UICulture` командлет, который получает текущий язык и региональные параметры пользовательского интерфейса в системе, и командлет [Set-Culture](/powershell/module/international/set-culture) в международном модуле. Язык и региональные параметры пользовательского интерфейса определяют, какие текстовые строки используются для элементов пользовательского интерфейса, например меню и сообщений.

## Примеры

### Пример 1. получение параметров культуры

```powershell
Get-Culture
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

Эта команда отображает сведения о региональных настройках компьютера.

### Пример 2. форматирование свойств объекта Culture

```powershell
PS C:\> $C = Get-Culture
PS C:\> $C | Format-List -Property *
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
CompareInfo                    : CompareInfo - 1033
TextInfo                       : TextInfo - 1033
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar, System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False

PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False

PS C:\> $C.DateTimeFormat
AMDesignator                     : AM
Calendar                         : System.Globalization.GregorianCalendar
DateSeparator                    : /
FirstDayOfWeek                   : Sunday
CalendarWeekRule                 : FirstDay
FullDateTimePattern              : dddd, MMMM dd, yyyy h:mm:ss tt
LongDatePattern                  : dddd, MMMM dd, yyyy
LongTimePattern                  : h:mm:ss tt
MonthDayPattern                  : MMMM dd
PMDesignator                     : PM
RFC1123Pattern                   : ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
ShortDatePattern                 : M/d/yyyy
ShortTimePattern                 : h:mm tt
SortableDateTimePattern          : yyyy'-'MM'-'dd'T'HH':'mm':'ss
TimeSeparator                    : :
UniversalSortableDateTimePattern : yyyy'-'MM'-'dd HH':'mm':'ss'Z'
YearMonthPattern                 : MMMM, yyyy
AbbreviatedDayNames              : {Sun, Mon, Tue, Wed...}
ShortestDayNames                 : {Su, Mo, Tu, We...}
DayNames                         : {Sunday, Monday, Tuesday, Wednesday...}
AbbreviatedMonthNames            : {Jan, Feb, Mar, Apr...}
MonthNames                       : {January, February, March, April...}
IsReadOnly                       : False
NativeCalendarName               : Gregorian Calendar
AbbreviatedMonthGenitiveNames    : {Jan, Feb, Mar, Apr...}
MonthGenitiveNames               : {January, February, March, April...}

PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

В этом примере показано значительное количество данных в объекте языка и региональных параметров. Показано, как отобразить свойства и подсвойства объекта.

Первая команда использует `Get-Culture` командлет для получения текущих настроек языка и региональных параметров на компьютере.
Он сохраняет результирующий объект языка и региональных параметров в `$C` переменной.

Вторая команда отображает все свойства объекта языка и региональных параметров. Он использует оператор конвейера ( `|` ) для отправки объекта языка и региональных параметров в `$C` `Format-List` командлет. Он использует параметр **Property** для вывода всех `*` свойств объекта (). Эту команду можно сократить на `$c | fl *` .

Оставшиеся команды просматривают свойства объекта языка и региональных параметров, используя нотацию с точкой, чтобы отобразить значения свойств объекта. Можно использовать эту нотацию для отображения значения любого свойства объекта.

Третья команда использует точечную нотацию для вывода значения свойства **Calendar** объекта Culture.

Четвертая команда использует точечную нотацию для вывода значения свойства **дататимеформат** объекта Culture.

У многих свойств объекта тоже есть свойства. Пятая команда использует точечную нотацию для вывода значения свойства **FirstDayOfWeek** свойства **DateTimeFormat** .

### Пример 3. получение определенного языка и региональных параметров

Получение объекта CultureInfo для французского языка в Франции.

```powershell
Get-Culture -Name fr-FR
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1036             fr-FR            French (France)
```

## PARAMETERS

### -ListAvailable

Извлекает все языки и региональные параметры, поддерживаемые текущей операционной системой.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Получение определенного языка и региональных параметров на основе имени.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Наусероверридес

Игнорировать изменения пользователей для текущего языка и региональных параметров.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CurrentCulture, Name
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

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Globalization. CultureInfo

`Get-Culture` Возвращает объект, представляющий текущий язык и региональные параметры.

## ПРИМЕЧАНИЯ

Можно также использовать `$PsCulture` `$PsUICulture` переменные и. `$PsCulture`Переменная хранит имя текущего языка и региональных параметров, а `$PsUICulture` переменная сохраняет имя текущего языка и региональных параметров пользовательского интерфейса.

## Связанные ссылки

[Set-Culture](/powershell/module/international/set-culture)

[Get-UICulture](Get-UICulture.md)
