---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: dc49f153adc22b7c2c943a4cc529ac155561228a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601607"
---
# <span data-ttu-id="91480-102">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="91480-102">Get-Culture</span></span>

## <span data-ttu-id="91480-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="91480-103">SYNOPSIS</span></span>
<span data-ttu-id="91480-104">Получает текущий язык и региональные параметры, установленные в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="91480-104">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="91480-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91480-105">SYNTAX</span></span>

### <span data-ttu-id="91480-106">CurrentCulture (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="91480-106">CurrentCulture (Default)</span></span>

```
Get-Culture [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="91480-107">Имя</span><span class="sxs-lookup"><span data-stu-id="91480-107">Name</span></span>

```
Get-Culture [-Name <String[]>] [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="91480-108">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="91480-108">ListAvailable</span></span>

```
Get-Culture [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="91480-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91480-109">DESCRIPTION</span></span>

<span data-ttu-id="91480-110">`Get-Culture`Командлет возвращает сведения о текущих параметрах языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="91480-110">The `Get-Culture` cmdlet gets information about the current culture settings.</span></span> <span data-ttu-id="91480-111">Сюда входят сведения о текущих языковых настройках, например раскладке клавиатуры, и формате отображения элементов, например чисел, валют и дат.</span><span class="sxs-lookup"><span data-stu-id="91480-111">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="91480-112">Можно также использовать `Get-UICulture` командлет, который получает текущий язык и региональные параметры пользовательского интерфейса в системе, и командлет [Set-Culture](/powershell/module/international/set-culture) в международном модуле.</span><span class="sxs-lookup"><span data-stu-id="91480-112">You can also use the `Get-UICulture` cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](/powershell/module/international/set-culture) cmdlet in the International module.</span></span> <span data-ttu-id="91480-113">Язык и региональные параметры пользовательского интерфейса определяют, какие текстовые строки используются для элементов пользовательского интерфейса, например меню и сообщений.</span><span class="sxs-lookup"><span data-stu-id="91480-113">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="91480-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="91480-114">EXAMPLES</span></span>

### <span data-ttu-id="91480-115">Пример 1. получение параметров культуры</span><span class="sxs-lookup"><span data-stu-id="91480-115">Example 1: Get culture settings</span></span>

```powershell
Get-Culture
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="91480-116">Эта команда отображает сведения о региональных настройках компьютера.</span><span class="sxs-lookup"><span data-stu-id="91480-116">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="91480-117">Пример 2. форматирование свойств объекта Culture</span><span class="sxs-lookup"><span data-stu-id="91480-117">Example 2: Format the properties of a culture object</span></span>

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

<span data-ttu-id="91480-118">В этом примере показано значительное количество данных в объекте языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="91480-118">This example demonstrates the vast amount of data in the culture object.</span></span> <span data-ttu-id="91480-119">Показано, как отобразить свойства и подсвойства объекта.</span><span class="sxs-lookup"><span data-stu-id="91480-119">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="91480-120">Первая команда использует `Get-Culture` командлет для получения текущих настроек языка и региональных параметров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="91480-120">The first command uses the `Get-Culture` cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="91480-121">Он сохраняет результирующий объект языка и региональных параметров в `$C` переменной.</span><span class="sxs-lookup"><span data-stu-id="91480-121">It stores the resulting culture object in the `$C` variable.</span></span>

<span data-ttu-id="91480-122">Вторая команда отображает все свойства объекта языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="91480-122">The second command displays all of the properties of the culture object.</span></span> <span data-ttu-id="91480-123">Он использует оператор конвейера ( `|` ) для отправки объекта языка и региональных параметров в `$C` `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="91480-123">It uses a pipeline operator (`|`) to send the culture object in `$C` to the `Format-List` cmdlet.</span></span> <span data-ttu-id="91480-124">Он использует параметр **Property** для вывода всех `*` свойств объекта ().</span><span class="sxs-lookup"><span data-stu-id="91480-124">It uses the **Property** parameter to display all (`*`) properties of the object.</span></span> <span data-ttu-id="91480-125">Эту команду можно сократить на `$c | fl *` .</span><span class="sxs-lookup"><span data-stu-id="91480-125">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="91480-126">Оставшиеся команды просматривают свойства объекта языка и региональных параметров, используя нотацию с точкой, чтобы отобразить значения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="91480-126">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span> <span data-ttu-id="91480-127">Можно использовать эту нотацию для отображения значения любого свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="91480-127">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="91480-128">Третья команда использует точечную нотацию для вывода значения свойства **Calendar** объекта Culture.</span><span class="sxs-lookup"><span data-stu-id="91480-128">The third command uses dot notation to display the value of the **Calendar** property of the culture object.</span></span>

<span data-ttu-id="91480-129">Четвертая команда использует точечную нотацию для вывода значения свойства **дататимеформат** объекта Culture.</span><span class="sxs-lookup"><span data-stu-id="91480-129">The fourth command uses dot notation to display the value of the **DataTimeFormat** property of the culture object.</span></span>

<span data-ttu-id="91480-130">У многих свойств объекта тоже есть свойства.</span><span class="sxs-lookup"><span data-stu-id="91480-130">Many object properties have properties.</span></span> <span data-ttu-id="91480-131">Пятая команда использует точечную нотацию для вывода значения свойства **FirstDayOfWeek** свойства **DateTimeFormat** .</span><span class="sxs-lookup"><span data-stu-id="91480-131">The fifth command uses dot notation to display the value of the **FirstDayOfWeek** property of the **DateTimeFormat** property.</span></span>

### <span data-ttu-id="91480-132">Пример 3. получение определенного языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="91480-132">Example 3: Get a specific culture</span></span>

<span data-ttu-id="91480-133">Получение объекта CultureInfo для французского языка в Франции.</span><span class="sxs-lookup"><span data-stu-id="91480-133">Get the CultureInfo object for French in France.</span></span>

```powershell
Get-Culture -Name fr-FR
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1036             fr-FR            French (France)
```

## <span data-ttu-id="91480-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91480-134">PARAMETERS</span></span>

### <span data-ttu-id="91480-135">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="91480-135">-ListAvailable</span></span>

<span data-ttu-id="91480-136">Извлекает все языки и региональные параметры, поддерживаемые текущей операционной системой.</span><span class="sxs-lookup"><span data-stu-id="91480-136">Retrieves all cultures supported by the current operating system.</span></span>

<span data-ttu-id="91480-137">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="91480-137">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="91480-138">-Name</span><span class="sxs-lookup"><span data-stu-id="91480-138">-Name</span></span>

<span data-ttu-id="91480-139">Получение определенного языка и региональных параметров на основе имени.</span><span class="sxs-lookup"><span data-stu-id="91480-139">Retrieve a specific culture based on the name.</span></span>

<span data-ttu-id="91480-140">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="91480-140">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="91480-141">-Наусероверридес</span><span class="sxs-lookup"><span data-stu-id="91480-141">-NoUserOverrides</span></span>

<span data-ttu-id="91480-142">Игнорировать изменения пользователей для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="91480-142">Ignore user changes for current culture.</span></span>

<span data-ttu-id="91480-143">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="91480-143">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="91480-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="91480-144">CommonParameters</span></span>

<span data-ttu-id="91480-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91480-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91480-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91480-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91480-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="91480-147">INPUTS</span></span>

### <span data-ttu-id="91480-148">None</span><span class="sxs-lookup"><span data-stu-id="91480-148">None</span></span>

<span data-ttu-id="91480-149">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="91480-149">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="91480-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="91480-150">OUTPUTS</span></span>

### <span data-ttu-id="91480-151">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="91480-151">System.Globalization.CultureInfo</span></span>

<span data-ttu-id="91480-152">`Get-Culture` Возвращает объект, представляющий текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="91480-152">`Get-Culture` returns an object that represents the current culture.</span></span>

## <span data-ttu-id="91480-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="91480-153">NOTES</span></span>

<span data-ttu-id="91480-154">Можно также использовать `$PsCulture` `$PsUICulture` переменные и.</span><span class="sxs-lookup"><span data-stu-id="91480-154">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="91480-155">`$PsCulture`Переменная хранит имя текущего языка и региональных параметров, а `$PsUICulture` переменная сохраняет имя текущего языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="91480-155">The `$PsCulture` variable stores the name of the current culture and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="91480-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="91480-156">RELATED LINKS</span></span>

[<span data-ttu-id="91480-157">Set-Culture</span><span class="sxs-lookup"><span data-stu-id="91480-157">Set-Culture</span></span>](/powershell/module/international/set-culture)

[<span data-ttu-id="91480-158">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="91480-158">Get-UICulture</span></span>](Get-UICulture.md)
