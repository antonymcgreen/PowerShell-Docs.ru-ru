---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: d7e9ebd56db3ad9de2bfbcec62f73f1f8c0e2eaa
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209065"
---
# Get-Culture

## Краткий обзор
Получает текущий язык и региональные параметры, установленные в операционной системе.

## SYNTAX

```
Get-Culture [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-Culture** получает сведения о текущих параметрах языка и региональных параметров.
Сюда входят сведения о текущих языковых настройках, например раскладке клавиатуры, и формате отображения элементов, например чисел, валют и дат.

Можно также использовать командлет Get-UICulture, который получает текущий язык и региональные параметры пользовательского интерфейса в системе, и командлет [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) в международном модуле.
Язык и региональные параметры пользовательского интерфейса определяют, какие текстовые строки используются для элементов пользовательского интерфейса, например меню и сообщений.

## Примеры

### Пример 1. получение параметров культуры

```
PS C:\> Get-Culture
```

Эта команда отображает сведения о региональных настройках компьютера.

### Пример 2. форматирование свойств объекта Culture

```
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
IsReadOnly                     : False PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False PS C:\> $C.DateTimeFormat
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
MonthGenitiveNames               : {January, February, March, April...} PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

В этом примере показано значительное количество данных в объекте языка и региональных параметров.
Показано, как отобразить свойства и подсвойства объекта.

Первая команда использует командлет **Get-Culture** для получения текущих настроек языка и региональных параметров на компьютере.
Он сохраняет полученный объект языка и региональных параметров в переменной $C.

Вторая команда отображает все свойства объекта языка и региональных параметров.
Он использует оператор конвейера (|) для отправки объекта языка и региональных параметров в $C командлету Format-List.
Он использует параметр *Property* для вывода всех свойств объекта (*).
Эту команду можно сократить на `$c | fl *` .

Оставшиеся команды просматривают свойства объекта языка и региональных параметров, используя нотацию с точкой, чтобы отобразить значения свойств объекта.
Можно использовать эту нотацию для отображения значения любого свойства объекта.

Третья команда использует нотацию с точкой, чтобы отобразить значения свойства Calendar объекта языка и региональных параметров.

Четвертая команда использует нотацию с точкой, чтобы отобразить значение свойства DataTimeFormat объекта языка и региональных параметров.

У многих свойств объекта тоже есть свойства.
Пятая команда использует нотацию с точкой, чтобы отобразить значение свойства FirstDayOfWeek свойства DateTimeFormat.

## PARAMETERS

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Globalization. CultureInfo
**Get-Culture** возвращает объект, представляющий текущий язык и региональные параметры.

## ПРИМЕЧАНИЯ

* Также можно использовать переменные $PsCulture и $PsUICulture. Переменная $PsCulture хранит имя текущего языка и региональных параметров, а переменная $PsUICulture хранит имя языка и региональных параметров пользовательского интерфейса.

*

## Связанные ссылки

[Set-Culture](/powershell/module/internationalcmdlets/set-culture)

[Get-UICulture](Get-UICulture.md)
