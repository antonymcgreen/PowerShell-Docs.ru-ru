---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 15305de9512a45a92242c283f60f6fd36b80fbe3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209001"
---
# <span data-ttu-id="5194e-103">Get-Host</span><span class="sxs-lookup"><span data-stu-id="5194e-103">Get-Host</span></span>

## <span data-ttu-id="5194e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5194e-104">SYNOPSIS</span></span>
<span data-ttu-id="5194e-105">Получает объект, представляющий текущую основную программу.</span><span class="sxs-lookup"><span data-stu-id="5194e-105">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="5194e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5194e-106">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="5194e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5194e-107">DESCRIPTION</span></span>

<span data-ttu-id="5194e-108">`Get-Host`Командлет возвращает объект, представляющий программу, в которой размещается Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5194e-108">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="5194e-109">По умолчанию отображается номер версии Windows PowerShell, а также текущие языковые и региональные параметры основной программы. В то же время объект основной программы содержит и другую информацию, включая подробные сведения о версии запущенной оболочки Windows PowerShell, а также текущих региональных параметрах и региональных параметрах пользовательского интерфейса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5194e-109">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="5194e-110">Этот командлет также можно использовать для настройки функций пользовательского интерфейса основной программы, например цветов текста и фона.</span><span class="sxs-lookup"><span data-stu-id="5194e-110">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="5194e-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="5194e-111">EXAMPLES</span></span>

### <span data-ttu-id="5194e-112">Пример 1. Получение сведений о узле консоли PowerShell</span><span class="sxs-lookup"><span data-stu-id="5194e-112">Example 1: Get information about the PowerShell console host</span></span>

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

<span data-ttu-id="5194e-113">Эта команда отображает сведения о консоли Windows PowerShell, которая является основной программой для сеанса Windows PowerShell в этом примере.</span><span class="sxs-lookup"><span data-stu-id="5194e-113">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="5194e-114">Она включают имя основной программы, запущенную версию Windows PowerShell, а также текущие региональные параметры и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5194e-114">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="5194e-115">Свойства Version, UI, CurrentCulture, CurrentUICulture, PrivateData и Runspace содержат объекты со свойствами, которые могут оказаться очень полезными.</span><span class="sxs-lookup"><span data-stu-id="5194e-115">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="5194e-116">Эти свойства будут рассмотрены в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="5194e-116">Later examples examine these properties.</span></span>

### <span data-ttu-id="5194e-117">Пример 2. изменение размера окна PowerShell</span><span class="sxs-lookup"><span data-stu-id="5194e-117">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="5194e-118">Эта команда изменяет размер окна Windows PowerShell, делая его высоту и ширину равными 10 пикселям.</span><span class="sxs-lookup"><span data-stu-id="5194e-118">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="5194e-119">Пример 3. Получение версии PowerShell для узла</span><span class="sxs-lookup"><span data-stu-id="5194e-119">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="5194e-120">Эта команда получает подробные сведения о версии Windows PowerShell, запущенной в основной программе.</span><span class="sxs-lookup"><span data-stu-id="5194e-120">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="5194e-121">Эти значения можно просматривать, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="5194e-121">You can view, but not change, these values.</span></span>

<span data-ttu-id="5194e-122">Свойство Version объекта `Get-Host` содержит объект **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="5194e-122">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="5194e-123">Эта команда использует конвейерный оператор (|) для отправки объекта Version в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="5194e-123">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="5194e-124">`Format-List`Команда использует параметр *Property* со значением All (\*) для вывода всех свойств и значений свойств объекта Version.</span><span class="sxs-lookup"><span data-stu-id="5194e-124">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="5194e-125">Пример 4. Получение текущего языка и региональных параметров для узла</span><span class="sxs-lookup"><span data-stu-id="5194e-125">Example 4: Get the current culture for the host</span></span>

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

<span data-ttu-id="5194e-126">Эта команда получает подробные сведения о текущих региональных параметрах оболочки Windows PowerShell, запущенной в основной программе.</span><span class="sxs-lookup"><span data-stu-id="5194e-126">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="5194e-127">Это те же сведения, которые возвращает `Get-Culture` командлет.</span><span class="sxs-lookup"><span data-stu-id="5194e-127">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="5194e-128">Аналогичным образом свойство **CurrentUICulture** возвращает тот же объект, который `Get-UICulture` возвращает.</span><span class="sxs-lookup"><span data-stu-id="5194e-128">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="5194e-129">Свойство **CurrentCulture** объекта host содержит объект **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="5194e-129">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="5194e-130">Эта команда использует конвейерный оператор (|) для отправки объекта **CultureInfo** `Format-List` командлету.</span><span class="sxs-lookup"><span data-stu-id="5194e-130">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="5194e-131">`Format-List`Команда использует параметр *Property* со значением All (\*) для вывода всех свойств и значений свойств объекта **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="5194e-131">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="5194e-132">Пример 5. получение DateTimeFormat для текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="5194e-132">Example 5: Get the DateTimeFormat for the current culture</span></span>

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

<span data-ttu-id="5194e-133">Эта команда возвращает подробные сведения о формате даты и времени текущих региональных параметров (DateTimeFormat), которые используются в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5194e-133">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="5194e-134">Свойство **CurrentCulture** объекта host содержит объект **CultureInfo** , который, в свою очередь, имеет много полезных свойств.</span><span class="sxs-lookup"><span data-stu-id="5194e-134">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="5194e-135">Кроме того, свойство **DateTimeFormat** содержит объект **DateTimeFormatInfo** со многими полезными свойствами.</span><span class="sxs-lookup"><span data-stu-id="5194e-135">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="5194e-136">Чтобы найти тип объекта, хранящегося в свойстве объекта, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="5194e-136">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="5194e-137">Чтобы отобразить значения свойств объекта, используйте `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="5194e-137">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="5194e-138">Пример 6. получение свойства Равуи для узла</span><span class="sxs-lookup"><span data-stu-id="5194e-138">Example 6: Get the RawUI property for the host</span></span>

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

<span data-ttu-id="5194e-139">Эта команда отображает свойства свойства **равуи** объекта Host.</span><span class="sxs-lookup"><span data-stu-id="5194e-139">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="5194e-140">Изменение этих значений позволяет изменить внешний вид окна основной программы.</span><span class="sxs-lookup"><span data-stu-id="5194e-140">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="5194e-141">Пример 7. Задание цвета фона для консоли PowerShell</span><span class="sxs-lookup"><span data-stu-id="5194e-141">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="5194e-142">Эти команды изменяют цвет фона консоли Windows PowerShell на черный.</span><span class="sxs-lookup"><span data-stu-id="5194e-142">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="5194e-143">Команда **CLS** является псевдонимом для `Clear-Host` функции, которая очищает экран и изменяет весь экран на новый цвет.</span><span class="sxs-lookup"><span data-stu-id="5194e-143">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="5194e-144">Это изменение действует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5194e-144">This change is effective only in the current session.</span></span> <span data-ttu-id="5194e-145">Чтобы изменить цвет фона консоли для всех сеансов, добавьте эту команду в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5194e-145">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="5194e-146">Пример 8. Задание цвета фона для сообщений об ошибках</span><span class="sxs-lookup"><span data-stu-id="5194e-146">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="5194e-147">Эта команда изменяет цвет фона сообщений об ошибках на белый.</span><span class="sxs-lookup"><span data-stu-id="5194e-147">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="5194e-148">Эта команда использует `$Host` автоматическую переменную, которая содержит объект узла для текущей основной программы.</span><span class="sxs-lookup"><span data-stu-id="5194e-148">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="5194e-149">`Get-Host` возвращает тот же объект, который `$Host` содержит, поэтому вы можете использовать их взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="5194e-149">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="5194e-150">Эта команда использует свойство **PrivateData** в `$Host` качестве свойства еррорбаккграундколор.</span><span class="sxs-lookup"><span data-stu-id="5194e-150">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="5194e-151">Для просмотра всех свойств объекта в `$Host` . PrivateData, введите `$host.privatedata | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="5194e-151">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="5194e-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5194e-152">PARAMETERS</span></span>

### <span data-ttu-id="5194e-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5194e-153">CommonParameters</span></span>

<span data-ttu-id="5194e-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5194e-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5194e-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5194e-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5194e-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5194e-156">INPUTS</span></span>

### <span data-ttu-id="5194e-157">Нет</span><span class="sxs-lookup"><span data-stu-id="5194e-157">None</span></span>
<span data-ttu-id="5194e-158">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="5194e-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5194e-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5194e-159">OUTPUTS</span></span>

### <span data-ttu-id="5194e-160">System. Management. Automation. internal. host. Интерналхост</span><span class="sxs-lookup"><span data-stu-id="5194e-160">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="5194e-161">`Get-Host` Возвращает объект **System. Management. Automation. internal. host. интерналхост** .</span><span class="sxs-lookup"><span data-stu-id="5194e-161">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="5194e-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5194e-162">NOTES</span></span>

<span data-ttu-id="5194e-163">`$Host`Автоматическая переменная содержит тот же объект, который `Get-Host` возвращает, и его можно использовать аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="5194e-163">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="5194e-164">Аналогичным образом, `$PSCulture` и `$PSUICulture` Автоматические переменные содержат те же объекты, которые содержат свойства CurrentCulture и CurrentUICulture объекта Host.</span><span class="sxs-lookup"><span data-stu-id="5194e-164">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="5194e-165">Эти функции можно использовать на равных основаниях.</span><span class="sxs-lookup"><span data-stu-id="5194e-165">You can use these features interchangeably.</span></span>

<span data-ttu-id="5194e-166">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5194e-166">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="5194e-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5194e-167">RELATED LINKS</span></span>

[<span data-ttu-id="5194e-168">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="5194e-168">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="5194e-169">Read-Host</span><span class="sxs-lookup"><span data-stu-id="5194e-169">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="5194e-170">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5194e-170">Write-Host</span></span>](Write-Host.md)
