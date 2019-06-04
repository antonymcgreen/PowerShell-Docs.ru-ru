---
title: Как написать модуль сценария PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: b2a929a1724f77f0516ad24cfd90f6d6053ed19e
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470803"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="c70cc-102">Как написать модуль сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="c70cc-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="c70cc-103">Модуль сценария — по сути любой допустимый скрипт PowerShell сохранен в расширение .psm1.</span><span class="sxs-lookup"><span data-stu-id="c70cc-103">A script module is essentially any valid PowerShell script saved in a .psm1 extension.</span></span> <span data-ttu-id="c70cc-104">Это расширение позволяет модулю PowerShell для использования нескольких правил и командлеты для файла.</span><span class="sxs-lookup"><span data-stu-id="c70cc-104">This extension allows the PowerShell engine to use a number of rules and cmdlets on your file.</span></span> <span data-ttu-id="c70cc-105">Большинство из этих возможностей предназначены для установки кода в других системах, а также управлять области.</span><span class="sxs-lookup"><span data-stu-id="c70cc-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="c70cc-106">Можно также использовать файл манифеста модуля, позволяют описывать еще более сложной установки и решений.</span><span class="sxs-lookup"><span data-stu-id="c70cc-106">You can also use a module manifest file, which can describe even more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="c70cc-107">Написание модуля сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="c70cc-107">Writing a PowerShell Script Module</span></span>

<span data-ttu-id="c70cc-108">Создайте модуль сценария, сохранив это допустимый скрипт PowerShell в файле с расширением psm1, а затем сохраните этот файл в каталог где его можно найти PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c70cc-108">You create a script module by saving a valid PowerShell script to a .psm1 file, and then saving that file in a directory located where PowerShell can find it.</span></span> <span data-ttu-id="c70cc-109">В этой папке, их также можно разместить все ресурсы, необходимые для запуска скрипта а также файл манифеста, описывающий для PowerShell как работает модуль.</span><span class="sxs-lookup"><span data-stu-id="c70cc-109">In that folder you can also place any resources you need to run your script, as well as a manifest file that describes to PowerShell how your module works.</span></span>

#### <a name="to-create-a-basic-powershell-module"></a><span data-ttu-id="c70cc-110">Чтобы создать базовый модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="c70cc-110">To create a basic PowerShell Module</span></span>

1. <span data-ttu-id="c70cc-111">Использовать существующий скрипт PowerShell и сохраните сценарий с расширением .psm1.</span><span class="sxs-lookup"><span data-stu-id="c70cc-111">Take an existing PowerShell script, and save the script with a .psm1 extension.</span></span>

   <span data-ttu-id="c70cc-112">Сохранение скрипта с помощью .psm1 расширения означает, что можно использовать командлеты модуля, такие как [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), на нем.</span><span class="sxs-lookup"><span data-stu-id="c70cc-112">Saving a script with the .psm1 extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), on it.</span></span> <span data-ttu-id="c70cc-113">Эти командлеты существует, то, что вы можете легко импортировать и экспортировать код на компьютерах других пользователей.</span><span class="sxs-lookup"><span data-stu-id="c70cc-113">These cmdlets exist primarily so that you can easily import and export your code onto other user's systems.</span></span> <span data-ttu-id="c70cc-114">(Альтернативное решение следует загрузить код на других системах, а затем с точкой в активной памяти, который не является особенно масштабируемым решением.) Дополнительные сведения см. в разделе **командлеты модуля и переменные** статьи [модули Windows PowerShell](./understanding-a-windows-powershell-module.md) Обратите внимание, что, по умолчанию все функции в скрипте, доступны для пользователей, импортируйте файл .psm1 но свойства не являются.</span><span class="sxs-lookup"><span data-stu-id="c70cc-114">(The alternate solution would be to load up your code on other systems and then dot-source it into active memory, which isn't a particularly scalable solution.) For more information see the **Module Cmdlets and Variables** section in [Windows PowerShell Modules](./understanding-a-windows-powershell-module.md) Note that, by default, all functions in your script are accessible to users who import your .psm1 file, but properties are not.</span></span>

   <span data-ttu-id="c70cc-115">Пример сценария PowerShell, имеют право `Show-Calendar`, доступна в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c70cc-115">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this topic.</span></span>

   ```powershell
   function Show-Calendar {
   param(
       [DateTime] $start = [DateTime]::Today,
       [DateTime] $end = $start,
       $firstDayOfWeek,
       [int[]] $highlightDay,
       [string[]] $highlightDate = [DateTime]::Today.ToString()
       )

       #actual code for the function goes here see the end of the topic for the complete code sample
   }
   ```

2. <span data-ttu-id="c70cc-116">Для управления доступом пользователей к определенным функции или свойства, вызовите [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="c70cc-116">To control user access to certain functions or properties, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="c70cc-117">В примере кода, в нижней части страницы имеет только одну функцию, которая по умолчанию предоставлялась бы.</span><span class="sxs-lookup"><span data-stu-id="c70cc-117">The example code at the bottom of the page has only one function, which by default would be exposed.</span></span> <span data-ttu-id="c70cc-118">Тем не менее рекомендуется явно вызывать out какие функции, которую нужно предоставить, как описано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c70cc-118">However, it is recommended that you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="c70cc-119">Также можно ограничить, что импортируется с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="c70cc-119">You can also restrict what is imported using a module manifest.</span></span> <span data-ttu-id="c70cc-120">Дополнительные сведения см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md) и [как написание манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="c70cc-120">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="c70cc-121">Если у вас есть собственный модуль, необходимые для загрузки модулей, их можно использовать с вызовом `Import-Module`, в верхней части своего модуля.</span><span class="sxs-lookup"><span data-stu-id="c70cc-121">If you have modules that your own module needs to have loaded, you can use them with a call to `Import-Module`, at the top of your own module.</span></span>

   <span data-ttu-id="c70cc-122">`Import-Module` — Это командлет, который импортирует модуль целевой системе.</span><span class="sxs-lookup"><span data-stu-id="c70cc-122">`Import-Module` is a cmdlet that imports a targeted module onto a system.</span></span> <span data-ttu-id="c70cc-123">Таким образом он также используется позже в процедуре для установки также собственный модуль.</span><span class="sxs-lookup"><span data-stu-id="c70cc-123">As such, it is also used at a later point in the procedure to install your own module as well.</span></span> <span data-ttu-id="c70cc-124">Пример кода, в нижней части этой страницы не использует каких-либо импорт модулей.</span><span class="sxs-lookup"><span data-stu-id="c70cc-124">The sample code at the bottom of this page does not use any import modules.</span></span> <span data-ttu-id="c70cc-125">Если они были, тем не менее, они будут перечислены в верхней части файла, как описано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c70cc-125">If it did, however, they would be listed at the top of the file, as described in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="c70cc-126">Для описания вашего модуля в PowerShell справочную систему, можно использовать комментарии Стандартная Справка внутри файла или создать дополнительный файл справки.</span><span class="sxs-lookup"><span data-stu-id="c70cc-126">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="c70cc-127">Пример кода в конце этого раздела включает справочные сведения в комментариях.</span><span class="sxs-lookup"><span data-stu-id="c70cc-127">The code sample at the bottom of this topic includes the help information in the comments.</span></span> <span data-ttu-id="c70cc-128">Можно также написать извлеченные файлы XML, содержащие дополнительное содержимое справки.</span><span class="sxs-lookup"><span data-stu-id="c70cc-128">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="c70cc-129">Дополнительные сведения см. в разделе [написание справки для Windows PowerShell модулей](./writing-help-for-windows-powershell-modules.md).</span><span class="sxs-lookup"><span data-stu-id="c70cc-129">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="c70cc-130">Если у вас есть дополнительные модули, XML-файлы или другие сведения, которые вы хотите упаковать с модулем, это можно сделать с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="c70cc-130">If you have additional modules, XML files, or other content you want to package up with your module, you can do so with a module manifest.</span></span>

   <span data-ttu-id="c70cc-131">Манифест модуля — это файл, который содержит имена других модулей, макеты каталогов, управление версиями чисел, автор данных и другие фрагменты данных.</span><span class="sxs-lookup"><span data-stu-id="c70cc-131">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="c70cc-132">PowerShell использует файл манифеста модуля для организации и развертывания решения.</span><span class="sxs-lookup"><span data-stu-id="c70cc-132">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="c70cc-133">Тем не менее из-за относительно простым устройством в этом примере, файл манифеста не требовалось.</span><span class="sxs-lookup"><span data-stu-id="c70cc-133">However, due to the relatively simple nature of this example, a manifest file was not needed.</span></span> <span data-ttu-id="c70cc-134">Дополнительные сведения см. в разделе [манифесты модуля](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="c70cc-134">For more information, see [Module Manifests](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="c70cc-135">Для установки и запуска вашего модуля, сохраните модуль соответствующие пути PowerShell и вызвать `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="c70cc-135">To install and run your module, save the module to one of the appropriate PowerShell paths, and make a call to `Import-Module`.</span></span>

   <span data-ttu-id="c70cc-136">Пути, где можно установить модуль, находятся в `$env:PSModulePath` глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c70cc-136">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="c70cc-137">Например, общий путь для сохранения модуля в системе будет `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span><span class="sxs-lookup"><span data-stu-id="c70cc-137">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="c70cc-138">Не забудьте создать папку для вашего модуля должно существовать, даже если это только один .psm1 файл.</span><span class="sxs-lookup"><span data-stu-id="c70cc-138">Be sure to create a folder for your module to exist in, even if it is only a single .psm1 file.</span></span> <span data-ttu-id="c70cc-139">Если вы не сохраняли вашего модуля к одному из этих путей, пришлось бы передать в расположение модуля в вызове `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="c70cc-139">If you did not save your module to one of these paths, you would have to pass in the location of your module in the call to `Import-Module`.</span></span> <span data-ttu-id="c70cc-140">(В противном случае PowerShell не сможет найти его.) Начиная с PowerShell 3.0, если вы разместили вашего модуля в одном из пути к модулям PowerShell, вы не обязательно должны явно импортирующих его.</span><span class="sxs-lookup"><span data-stu-id="c70cc-140">(Otherwise, PowerShell would not be able to find it.) Starting with PowerShell 3.0, if you have placed your module in one of the PowerShell module paths, you do not need to explicitly import it.</span></span> <span data-ttu-id="c70cc-141">Вы модуль загружается автоматически в том случае, когда пользователь вызывает функции.</span><span class="sxs-lookup"><span data-stu-id="c70cc-141">You module is automatically loaded when a user calls your function.</span></span>
   <span data-ttu-id="c70cc-142">Дополнительные сведения о пути к модулю, см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md) и [переменной среды PSModulePath](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="c70cc-142">For more information on the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [PSModulePath Environment Variable](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="c70cc-143">Чтобы удалить модуль из активной службой, сделать вызов к [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="c70cc-143">To remove a module from active service, make a call to [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   <span data-ttu-id="c70cc-144">Обратите внимание, что [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) удаляет модуль из активной памяти — он фактически не удаляются его из которых были сохранены файлы модуля.</span><span class="sxs-lookup"><span data-stu-id="c70cc-144">Note that [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) removes your module from active memory - it does not actually delete it from where you saved the module files.</span></span>

### <a name="show-calendar-code-example"></a><span data-ttu-id="c70cc-145">Пример кода show-Calendar</span><span class="sxs-lookup"><span data-stu-id="c70cc-145">Show-Calendar code example</span></span>

<span data-ttu-id="c70cc-146">Ниже приведен простой сценарий модуль, содержащий одну функцию с именем `Show-Calendar`.</span><span class="sxs-lookup"><span data-stu-id="c70cc-146">The following example is a simple script module that contains a single function named `Show-Calendar`.</span></span>
<span data-ttu-id="c70cc-147">Эта функция отображает визуальное представление календаря.</span><span class="sxs-lookup"><span data-stu-id="c70cc-147">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="c70cc-148">Кроме того пример содержит строки справки PowerShell краткий обзор, описание и значения параметров, а также пример.</span><span class="sxs-lookup"><span data-stu-id="c70cc-148">In addition, the sample contains the PowerShell Help strings for the synopsis, description, parameter values, and example.</span></span> <span data-ttu-id="c70cc-149">Обратите внимание, что последняя строка кода гарантирует, что `Show-Calendar` функция экспортируется как член модуля при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="c70cc-149">Note that the last line of code ensures that the `Show-Calendar` function is exported as a module member when the module is imported.</span></span>

```powershell
<#
 .Synopsis
  Displays a visual representation of a calendar.

 .Description
  Displays a visual representation of a calendar. This function supports multiple months
  and lets you highlight specific date ranges or days.

 .Parameter Start
  The first month to display.

 .Parameter End
  The last month to display.

 .Parameter FirstDayOfWeek
  The day of the month on which the week begins.

 .Parameter HighlightDay
  Specific days (numbered) to highlight. Used for date ranges like (25..31).
  Date ranges are specified by the Windows PowerShell range syntax. These dates are
  enclosed in square brackets.

 .Parameter HighlightDate
  Specific days (named) to highlight. These dates are surrounded by asterisks.

 .Example
   # Show a default display of this month.
   Show-Calendar

 .Example
   # Display a date range.
   Show-Calendar -Start "March, 2010" -End "May, 2010"

 .Example
   # Highlight a range of days.
   Show-Calendar -HighlightDay (1..10 + 22) -HighlightDate "December 25, 2008"
#>
function Show-Calendar {
param(
    [DateTime] $start = [DateTime]::Today,
    [DateTime] $end = $start,
    $firstDayOfWeek,
    [int[]] $highlightDay,
    [string[]] $highlightDate = [DateTime]::Today.ToString()
    )

## Determine the first day of the start and end months.
$start = New-Object DateTime $start.Year,$start.Month,1
$end = New-Object DateTime $end.Year,$end.Month,1

## Convert the highlighted dates into real dates.
[DateTime[]] $highlightDate = [DateTime[]] $highlightDate

## Retrieve the DateTimeFormat information so that the
## calendar can be manipulated.
$dateTimeFormat  = (Get-Culture).DateTimeFormat
if($firstDayOfWeek)
{
    $dateTimeFormat.FirstDayOfWeek = $firstDayOfWeek
}

$currentDay = $start

## Process the requested months.
while($start -le $end)
{
    ## Return to an earlier point in the function if the first day of the month
    ## is in the middle of the week.
    while($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek)
    {
        $currentDay = $currentDay.AddDays(-1)
    }

    ## Prepare to store information about this date range.
    $currentWeek = New-Object PsObject
    $dayNames = @()
    $weeks = @()

    ## Continue processing dates until the function reaches the end of the month.
    ## The function continues until the week is completed with
    ## days from the next month.
    while(($currentDay -lt $start.AddMonths(1)) -or
        ($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek))
    {
        ## Determine the day names to use to label the columns.
        $dayName = "{0:ddd}" -f $currentDay
        if($dayNames -notcontains $dayName)
        {
            $dayNames += $dayName
        }

        ## Pad the day number for display, highlighting if necessary.
        $displayDay = " {0,2} " -f $currentDay.Day

        ## Determine whether to highlight a specific date.
        if($highlightDate)
        {
            $compareDate = New-Object DateTime $currentDay.Year,
                $currentDay.Month,$currentDay.Day
            if($highlightDate -contains $compareDate)
            {
                $displayDay = "*" + ("{0,2}" -f $currentDay.Day) + "*"
            }
        }

        ## Otherwise, highlight as part of a date range.
        if($highlightDay -and ($highlightDay[0] -eq $currentDay.Day))
        {
            $displayDay = "[" + ("{0,2}" -f $currentDay.Day) + "]"
            $null,$highlightDay = $highlightDay
        }

        ## Add the day of the week and the day of the month as note properties.
        $currentWeek | Add-Member NoteProperty $dayName $displayDay

        ## Move to the next day of the month.
        $currentDay = $currentDay.AddDays(1)

        ## If the function reaches the next week, store the current week
        ## in the week list and continue.
        if($currentDay.DayOfWeek -eq $dateTimeFormat.FirstDayOfWeek)
        {
            $weeks += $currentWeek
            $currentWeek = New-Object PsObject
        }
    }

    ## Format the weeks as a table.
    $calendar = $weeks | Format-Table $dayNames -AutoSize | Out-String

    ## Add a centered header.
    $width = ($calendar.Split("`n") | Measure-Object -Maximum Length).Maximum
    $header = "{0:MMMM yyyy}" -f $start
    $padding = " " * (($width - $header.Length) / 2)
    $displayCalendar = " `n" + $padding + $header + "`n " + $calendar
    $displayCalendar.TrimEnd()

    ## Move to the next month.
    $start = $start.AddMonths(1)

}
}
Export-ModuleMember -Function Show-Calendar
```
