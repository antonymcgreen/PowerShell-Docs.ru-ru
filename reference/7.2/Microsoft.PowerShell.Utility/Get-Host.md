---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 0775940f210cb028d7a0919bb8e5ca9f256b70d8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602487"
---
# <span data-ttu-id="7df35-102">Get-Host</span><span class="sxs-lookup"><span data-stu-id="7df35-102">Get-Host</span></span>

## <span data-ttu-id="7df35-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7df35-103">SYNOPSIS</span></span>
<span data-ttu-id="7df35-104">Получает объект, представляющий текущую основную программу.</span><span class="sxs-lookup"><span data-stu-id="7df35-104">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="7df35-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7df35-105">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="7df35-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7df35-106">DESCRIPTION</span></span>

<span data-ttu-id="7df35-107">`Get-Host`Командлет возвращает объект, представляющий программу, в которой размещается Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df35-107">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="7df35-108">По умолчанию отображается номер версии Windows PowerShell, а также текущие языковые и региональные параметры основной программы. В то же время объект основной программы содержит и другую информацию, включая подробные сведения о версии запущенной оболочки Windows PowerShell, а также текущих региональных параметрах и региональных параметрах пользовательского интерфейса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df35-108">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="7df35-109">Этот командлет также можно использовать для настройки функций пользовательского интерфейса основной программы, например цветов текста и фона.</span><span class="sxs-lookup"><span data-stu-id="7df35-109">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="7df35-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="7df35-110">EXAMPLES</span></span>

### <span data-ttu-id="7df35-111">Пример 1. Получение сведений о узле консоли PowerShell</span><span class="sxs-lookup"><span data-stu-id="7df35-111">Example 1: Get information about the PowerShell console host</span></span>

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

<span data-ttu-id="7df35-112">Эта команда отображает сведения о консоли Windows PowerShell, которая является основной программой для сеанса Windows PowerShell в этом примере.</span><span class="sxs-lookup"><span data-stu-id="7df35-112">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="7df35-113">Она включают имя основной программы, запущенную версию Windows PowerShell, а также текущие региональные параметры и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7df35-113">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="7df35-114">Свойства Version, UI, CurrentCulture, CurrentUICulture, PrivateData и Runspace содержат объекты со свойствами, которые могут оказаться очень полезными.</span><span class="sxs-lookup"><span data-stu-id="7df35-114">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="7df35-115">Эти свойства будут рассмотрены в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="7df35-115">Later examples examine these properties.</span></span>

### <span data-ttu-id="7df35-116">Пример 2. изменение размера окна PowerShell</span><span class="sxs-lookup"><span data-stu-id="7df35-116">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="7df35-117">Эта команда изменяет размер окна Windows PowerShell, делая его высоту и ширину равными 10 пикселям.</span><span class="sxs-lookup"><span data-stu-id="7df35-117">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="7df35-118">Пример 3. Получение версии PowerShell для узла</span><span class="sxs-lookup"><span data-stu-id="7df35-118">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="7df35-119">Эта команда получает подробные сведения о версии Windows PowerShell, запущенной в основной программе.</span><span class="sxs-lookup"><span data-stu-id="7df35-119">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="7df35-120">Эти значения можно просматривать, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="7df35-120">You can view, but not change, these values.</span></span>

<span data-ttu-id="7df35-121">Свойство Version объекта `Get-Host` содержит объект **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="7df35-121">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="7df35-122">Эта команда использует конвейерный оператор (|) для отправки объекта Version в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="7df35-122">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7df35-123">`Format-List`Команда использует параметр *Property* со значением All (\*) для вывода всех свойств и значений свойств объекта Version.</span><span class="sxs-lookup"><span data-stu-id="7df35-123">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="7df35-124">Пример 4. Получение текущего языка и региональных параметров для узла</span><span class="sxs-lookup"><span data-stu-id="7df35-124">Example 4: Get the current culture for the host</span></span>

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

<span data-ttu-id="7df35-125">Эта команда получает подробные сведения о текущих региональных параметрах оболочки Windows PowerShell, запущенной в основной программе.</span><span class="sxs-lookup"><span data-stu-id="7df35-125">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="7df35-126">Это те же сведения, которые возвращает `Get-Culture` командлет.</span><span class="sxs-lookup"><span data-stu-id="7df35-126">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="7df35-127">Аналогичным образом свойство **CurrentUICulture** возвращает тот же объект, который `Get-UICulture` возвращает.</span><span class="sxs-lookup"><span data-stu-id="7df35-127">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="7df35-128">Свойство **CurrentCulture** объекта host содержит объект **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="7df35-128">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="7df35-129">Эта команда использует конвейерный оператор (|) для отправки объекта **CultureInfo** `Format-List` командлету.</span><span class="sxs-lookup"><span data-stu-id="7df35-129">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7df35-130">`Format-List`Команда использует параметр *Property* со значением All (\*) для вывода всех свойств и значений свойств объекта **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="7df35-130">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="7df35-131">Пример 5. получение DateTimeFormat для текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="7df35-131">Example 5: Get the DateTimeFormat for the current culture</span></span>

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

<span data-ttu-id="7df35-132">Эта команда возвращает подробные сведения о формате даты и времени текущих региональных параметров (DateTimeFormat), которые используются в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df35-132">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="7df35-133">Свойство **CurrentCulture** объекта host содержит объект **CultureInfo** , который, в свою очередь, имеет много полезных свойств.</span><span class="sxs-lookup"><span data-stu-id="7df35-133">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="7df35-134">Кроме того, свойство **DateTimeFormat** содержит объект **DateTimeFormatInfo** со многими полезными свойствами.</span><span class="sxs-lookup"><span data-stu-id="7df35-134">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="7df35-135">Чтобы найти тип объекта, хранящегося в свойстве объекта, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="7df35-135">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="7df35-136">Чтобы отобразить значения свойств объекта, используйте `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="7df35-136">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="7df35-137">Пример 6. получение свойства Равуи для узла</span><span class="sxs-lookup"><span data-stu-id="7df35-137">Example 6: Get the RawUI property for the host</span></span>

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

<span data-ttu-id="7df35-138">Эта команда отображает свойства свойства **равуи** объекта Host.</span><span class="sxs-lookup"><span data-stu-id="7df35-138">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="7df35-139">Изменение этих значений позволяет изменить внешний вид окна основной программы.</span><span class="sxs-lookup"><span data-stu-id="7df35-139">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="7df35-140">Пример 7. Задание цвета фона для консоли PowerShell</span><span class="sxs-lookup"><span data-stu-id="7df35-140">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="7df35-141">Эти команды изменяют цвет фона консоли Windows PowerShell на черный.</span><span class="sxs-lookup"><span data-stu-id="7df35-141">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="7df35-142">Команда **CLS** является псевдонимом для `Clear-Host` функции, которая очищает экран и изменяет весь экран на новый цвет.</span><span class="sxs-lookup"><span data-stu-id="7df35-142">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="7df35-143">Это изменение действует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7df35-143">This change is effective only in the current session.</span></span> <span data-ttu-id="7df35-144">Чтобы изменить цвет фона консоли для всех сеансов, добавьте эту команду в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7df35-144">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="7df35-145">Пример 8. Задание цвета фона для сообщений об ошибках</span><span class="sxs-lookup"><span data-stu-id="7df35-145">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="7df35-146">Эта команда изменяет цвет фона сообщений об ошибках на белый.</span><span class="sxs-lookup"><span data-stu-id="7df35-146">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="7df35-147">Эта команда использует `$Host` автоматическую переменную, которая содержит объект узла для текущей основной программы.</span><span class="sxs-lookup"><span data-stu-id="7df35-147">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="7df35-148">`Get-Host` возвращает тот же объект, который `$Host` содержит, поэтому вы можете использовать их взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="7df35-148">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="7df35-149">Эта команда использует свойство **PrivateData** в `$Host` качестве свойства еррорбаккграундколор.</span><span class="sxs-lookup"><span data-stu-id="7df35-149">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="7df35-150">Для просмотра всех свойств объекта в `$Host` . PrivateData, введите `$host.privatedata | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="7df35-150">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="7df35-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7df35-151">PARAMETERS</span></span>

### <span data-ttu-id="7df35-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7df35-152">CommonParameters</span></span>

<span data-ttu-id="7df35-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7df35-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7df35-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7df35-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7df35-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7df35-155">INPUTS</span></span>

### <span data-ttu-id="7df35-156">None</span><span class="sxs-lookup"><span data-stu-id="7df35-156">None</span></span>
<span data-ttu-id="7df35-157">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="7df35-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7df35-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7df35-158">OUTPUTS</span></span>

### <span data-ttu-id="7df35-159">System. Management. Automation. internal. host. Интерналхост</span><span class="sxs-lookup"><span data-stu-id="7df35-159">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="7df35-160">`Get-Host` Возвращает объект **System. Management. Automation. internal. host. интерналхост** .</span><span class="sxs-lookup"><span data-stu-id="7df35-160">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="7df35-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7df35-161">NOTES</span></span>

<span data-ttu-id="7df35-162">`$Host`Автоматическая переменная содержит тот же объект, который `Get-Host` возвращает, и его можно использовать аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="7df35-162">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="7df35-163">Аналогичным образом, `$PSCulture` и `$PSUICulture` Автоматические переменные содержат те же объекты, которые содержат свойства CurrentCulture и CurrentUICulture объекта Host.</span><span class="sxs-lookup"><span data-stu-id="7df35-163">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="7df35-164">Эти функции можно использовать на равных основаниях.</span><span class="sxs-lookup"><span data-stu-id="7df35-164">You can use these features interchangeably.</span></span>

<span data-ttu-id="7df35-165">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="7df35-165">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="7df35-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7df35-166">RELATED LINKS</span></span>

[<span data-ttu-id="7df35-167">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="7df35-167">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="7df35-168">Read-Host</span><span class="sxs-lookup"><span data-stu-id="7df35-168">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="7df35-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="7df35-169">Write-Host</span></span>](Write-Host.md)

