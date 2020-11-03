---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: fee53cd5d241b04b85bc994476d26808b3975bb9
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209050"
---
# Get-Host

## Краткий обзор
Получает объект, представляющий текущую основную программу.

## SYNTAX

```
Get-Host [<CommonParameters>]
```

## DESCRIPTION

`Get-Host`Командлет возвращает объект, представляющий программу, в которой размещается Windows PowerShell.

По умолчанию отображается номер версии Windows PowerShell, а также текущие языковые и региональные параметры основной программы. В то же время объект основной программы содержит и другую информацию, включая подробные сведения о версии запущенной оболочки Windows PowerShell, а также текущих региональных параметрах и региональных параметрах пользовательского интерфейса Windows PowerShell. Этот командлет также можно использовать для настройки функций пользовательского интерфейса основной программы, например цветов текста и фона.

## Примеры

### Пример 1. Получение сведений о узле консоли PowerShell

```
PS C:\> Get-Host
Name             : ConsoleHost
Version          : 2.0
InstanceId       : e4e0ab54-cc5e-4261-9117-4081f20ce7a2
UI               : System.Management.Automation.Internal.Host.InternalHostUserInterface
CurrentCulture   : en-US
CurrentUICulture : en-US
PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
IsRunspacePushed : False
Runspace         : System.Management.Automation.Runspaces.LocalRunspace
```

Эта команда отображает сведения о консоли Windows PowerShell, которая является основной программой для сеанса Windows PowerShell в этом примере. Она включают имя основной программы, запущенную версию Windows PowerShell, а также текущие региональные параметры и региональные параметры пользовательского интерфейса.

Свойства Version, UI, CurrentCulture, CurrentUICulture, PrivateData и Runspace содержат объекты со свойствами, которые могут оказаться очень полезными. Эти свойства будут рассмотрены в следующих примерах.

### Пример 2. изменение размера окна PowerShell

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

Эта команда изменяет размер окна Windows PowerShell, делая его высоту и ширину равными 10 пикселям.

### Пример 3. Получение версии PowerShell для узла

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

Эта команда получает подробные сведения о версии Windows PowerShell, запущенной в основной программе.
Эти значения можно просматривать, но нельзя изменять.

Свойство Version объекта `Get-Host` содержит объект **System. Version** . Эта команда использует конвейерный оператор (|) для отправки объекта Version в `Format-List` командлет. `Format-List`Команда использует параметр *Property* со значением All (*) для вывода всех свойств и значений свойств объекта Version.

### Пример 4. Получение текущего языка и региональных параметров для узла

```powershell
PS C:\> (Get-Host).CurrentCulture | Format-List -Property *
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
```

Эта команда получает подробные сведения о текущих региональных параметрах оболочки Windows PowerShell, запущенной в основной программе. Это те же сведения, которые возвращает `Get-Culture` командлет.

Аналогичным образом свойство **CurrentUICulture** возвращает тот же объект, который `Get-UICulture` возвращает.

Свойство **CurrentCulture** объекта host содержит объект **System. Globalization. CultureInfo** . Эта команда использует конвейерный оператор (|) для отправки объекта **CultureInfo** `Format-List` командлету. `Format-List`Команда использует параметр *Property* со значением All (*) для вывода всех свойств и значений свойств объекта **CultureInfo** .

### Пример 5. получение DateTimeFormat для текущего языка и региональных параметров

```powershell
PS C:\> (Get-Host).CurrentCulture.DateTimeFormat | Format-List -Property *
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
```

Эта команда возвращает подробные сведения о формате даты и времени текущих региональных параметров (DateTimeFormat), которые используются в Windows PowerShell.

Свойство **CurrentCulture** объекта host содержит объект **CultureInfo** , который, в свою очередь, имеет много полезных свойств. Кроме того, свойство **DateTimeFormat** содержит объект **DateTimeFormatInfo** со многими полезными свойствами.

Чтобы найти тип объекта, хранящегося в свойстве объекта, используйте `Get-Member` командлет. Чтобы отобразить значения свойств объекта, используйте `Format-List` командлет.

### Пример 6. получение свойства Равуи для узла

```
PS C:\> (Get-Host).UI.RawUI | Format-List -Property *
ForegroundColor       : DarkYellow
BackgroundColor       : DarkBlue
CursorPosition        : 0,390
WindowPosition        : 0,341
CursorSize            : 25
BufferSize            : 120,3000
WindowSize            : 120,50
MaxWindowSize         : 120,81
MaxPhysicalWindowSize : 182,81
KeyAvailable          : False
WindowTitle           : Windows PowerShell 2.0 (04/11/2008 00:08:14)
```

Эта команда отображает свойства свойства **равуи** объекта Host. Изменение этих значений позволяет изменить внешний вид окна основной программы.

### Пример 7. Задание цвета фона для консоли PowerShell

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

Эти команды изменяют цвет фона консоли Windows PowerShell на черный. Команда **CLS** является псевдонимом для `Clear-Host` функции, которая очищает экран и изменяет весь экран на новый цвет.

Это изменение действует только в текущем сеансе. Чтобы изменить цвет фона консоли для всех сеансов, добавьте эту команду в профиль Windows PowerShell.

### Пример 8. Задание цвета фона для сообщений об ошибках

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

Эта команда изменяет цвет фона сообщений об ошибках на белый.

Эта команда использует `$Host` автоматическую переменную, которая содержит объект узла для текущей основной программы. `Get-Host` возвращает тот же объект, который `$Host` содержит, поэтому вы можете использовать их взаимозаменяемы.

Эта команда использует свойство **PrivateData** в `$Host` качестве свойства еррорбаккграундколор. Для просмотра всех свойств объекта в `$Host` . PrivateData, введите `$host.privatedata | format-list *` .

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. internal. host. Интерналхост

`Get-Host` Возвращает объект **System. Management. Automation. internal. host. интерналхост** .

## ПРИМЕЧАНИЯ

`$Host`Автоматическая переменная содержит тот же объект, который `Get-Host` возвращает, и его можно использовать аналогичным образом. Аналогичным образом, `$PSCulture` и `$PSUICulture` Автоматические переменные содержат те же объекты, которые содержат свойства CurrentCulture и CurrentUICulture объекта Host. Эти функции можно использовать на равных основаниях.

Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## Связанные ссылки

[Clear-Host;](../Microsoft.PowerShell.Core/Clear-Host.md)

[Read-Host](Read-Host.md)

[Write-Host](Write-Host.md)
