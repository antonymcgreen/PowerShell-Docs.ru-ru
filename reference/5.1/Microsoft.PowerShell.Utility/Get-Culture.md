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
# <span data-ttu-id="a0164-103">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="a0164-103">Get-Culture</span></span>

## <span data-ttu-id="a0164-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a0164-104">SYNOPSIS</span></span>
<span data-ttu-id="a0164-105">Получает текущий язык и региональные параметры, установленные в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="a0164-105">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="a0164-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0164-106">SYNTAX</span></span>

```
Get-Culture [<CommonParameters>]
```

## <span data-ttu-id="a0164-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0164-107">DESCRIPTION</span></span>
<span data-ttu-id="a0164-108">Командлет **Get-Culture** получает сведения о текущих параметрах языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a0164-108">The **Get-Culture** cmdlet gets information about the current culture settings.</span></span>
<span data-ttu-id="a0164-109">Сюда входят сведения о текущих языковых настройках, например раскладке клавиатуры, и формате отображения элементов, например чисел, валют и дат.</span><span class="sxs-lookup"><span data-stu-id="a0164-109">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="a0164-110">Можно также использовать командлет Get-UICulture, который получает текущий язык и региональные параметры пользовательского интерфейса в системе, и командлет [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) в международном модуле.</span><span class="sxs-lookup"><span data-stu-id="a0164-110">You can also use the Get-UICulture cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) cmdlet in the International module.</span></span>
<span data-ttu-id="a0164-111">Язык и региональные параметры пользовательского интерфейса определяют, какие текстовые строки используются для элементов пользовательского интерфейса, например меню и сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0164-111">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="a0164-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a0164-112">EXAMPLES</span></span>

### <span data-ttu-id="a0164-113">Пример 1. получение параметров культуры</span><span class="sxs-lookup"><span data-stu-id="a0164-113">Example 1: Get culture settings</span></span>

```
PS C:\> Get-Culture
```

<span data-ttu-id="a0164-114">Эта команда отображает сведения о региональных настройках компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0164-114">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="a0164-115">Пример 2. форматирование свойств объекта Culture</span><span class="sxs-lookup"><span data-stu-id="a0164-115">Example 2: Format the properties of a culture object</span></span>

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

<span data-ttu-id="a0164-116">В этом примере показано значительное количество данных в объекте языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a0164-116">This example demonstrates the vast amount of data in the culture object.</span></span>
<span data-ttu-id="a0164-117">Показано, как отобразить свойства и подсвойства объекта.</span><span class="sxs-lookup"><span data-stu-id="a0164-117">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="a0164-118">Первая команда использует командлет **Get-Culture** для получения текущих настроек языка и региональных параметров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0164-118">The first command uses the **Get-Culture** cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="a0164-119">Он сохраняет полученный объект языка и региональных параметров в переменной $C.</span><span class="sxs-lookup"><span data-stu-id="a0164-119">It stores the resulting culture object in the $C variable.</span></span>

<span data-ttu-id="a0164-120">Вторая команда отображает все свойства объекта языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a0164-120">The second command displays all of the properties of the culture object.</span></span>
<span data-ttu-id="a0164-121">Он использует оператор конвейера (|) для отправки объекта языка и региональных параметров в $C командлету Format-List.</span><span class="sxs-lookup"><span data-stu-id="a0164-121">It uses a pipeline operator (|) to send the culture object in $C to the Format-List cmdlet.</span></span>
<span data-ttu-id="a0164-122">Он использует параметр *Property* для вывода всех свойств объекта (\*).</span><span class="sxs-lookup"><span data-stu-id="a0164-122">It uses the *Property* parameter to display all (\*) properties of the object.</span></span>
<span data-ttu-id="a0164-123">Эту команду можно сократить на `$c | fl *` .</span><span class="sxs-lookup"><span data-stu-id="a0164-123">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="a0164-124">Оставшиеся команды просматривают свойства объекта языка и региональных параметров, используя нотацию с точкой, чтобы отобразить значения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="a0164-124">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span>
<span data-ttu-id="a0164-125">Можно использовать эту нотацию для отображения значения любого свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="a0164-125">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="a0164-126">Третья команда использует нотацию с точкой, чтобы отобразить значения свойства Calendar объекта языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a0164-126">The third command uses dot notation to display the value of the Calendar property of the culture object.</span></span>

<span data-ttu-id="a0164-127">Четвертая команда использует нотацию с точкой, чтобы отобразить значение свойства DataTimeFormat объекта языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a0164-127">The fourth command uses dot notation to display the value of the DataTimeFormat property of the culture object.</span></span>

<span data-ttu-id="a0164-128">У многих свойств объекта тоже есть свойства.</span><span class="sxs-lookup"><span data-stu-id="a0164-128">Many object properties have properties.</span></span>
<span data-ttu-id="a0164-129">Пятая команда использует нотацию с точкой, чтобы отобразить значение свойства FirstDayOfWeek свойства DateTimeFormat.</span><span class="sxs-lookup"><span data-stu-id="a0164-129">The fifth command uses dot notation to display the value of the FirstDayOfWeek property of the DateTimeFormat property.</span></span>

## <span data-ttu-id="a0164-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0164-130">PARAMETERS</span></span>

### <span data-ttu-id="a0164-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a0164-131">CommonParameters</span></span>
<span data-ttu-id="a0164-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0164-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0164-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0164-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0164-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a0164-134">INPUTS</span></span>

### <span data-ttu-id="a0164-135">Нет</span><span class="sxs-lookup"><span data-stu-id="a0164-135">None</span></span>
<span data-ttu-id="a0164-136">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="a0164-136">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a0164-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a0164-137">OUTPUTS</span></span>

### <span data-ttu-id="a0164-138">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="a0164-138">System.Globalization.CultureInfo</span></span>
<span data-ttu-id="a0164-139">**Get-Culture** возвращает объект, представляющий текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="a0164-139">**Get-Culture** returns an object that represents the current culture.</span></span>

## <span data-ttu-id="a0164-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a0164-140">NOTES</span></span>

* <span data-ttu-id="a0164-141">Также можно использовать переменные $PsCulture и $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="a0164-141">You can also use the $PsCulture and $PsUICulture variables.</span></span> <span data-ttu-id="a0164-142">Переменная $PsCulture хранит имя текущего языка и региональных параметров, а переменная $PsUICulture хранит имя языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a0164-142">The $PsCulture variable stores the name of the current culture and the $PsUICulture variable stores the name of the current UI culture.</span></span>

*

## <span data-ttu-id="a0164-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a0164-143">RELATED LINKS</span></span>

[<span data-ttu-id="a0164-144">Set-Culture</span><span class="sxs-lookup"><span data-stu-id="a0164-144">Set-Culture</span></span>](/powershell/module/internationalcmdlets/set-culture)

[<span data-ttu-id="a0164-145">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="a0164-145">Get-UICulture</span></span>](Get-UICulture.md)
