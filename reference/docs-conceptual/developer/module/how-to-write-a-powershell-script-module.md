---
title: Написание модуля скрипта PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 11/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: 7742eedd67283535b9e5898adc74d0d48faf68fe
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416261"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="dbcb6-102">Как написать модуль сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbcb6-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="dbcb6-103">Модуль скрипта — это любой допустимый сценарий PowerShell, сохраненный в расширении `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-103">A script module is any valid PowerShell script saved in a `.psm1` extension.</span></span> <span data-ttu-id="dbcb6-104">Это расширение позволяет подсистеме PowerShell использовать правила и командлеты модуля в файле.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-104">This extension allows the PowerShell engine to use rules and module cmdlets on your file.</span></span> <span data-ttu-id="dbcb6-105">Большая часть этих возможностей заключается в том, чтобы помочь вам установить код в других системах, а также управлять областями.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="dbcb6-106">Можно также использовать файл манифеста модуля, который описывает более сложные установки и решения.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-106">You can also use a module manifest file, which describes more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="dbcb6-107">Написание модуля скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbcb6-107">Writing a PowerShell script module</span></span>

<span data-ttu-id="dbcb6-108">Чтобы создать модуль скрипта, сохраните допустимый скрипт PowerShell в файл `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-108">To create a script module, save a valid PowerShell script to a `.psm1` file.</span></span> <span data-ttu-id="dbcb6-109">Скрипт и каталог, в котором он хранится, должны использовать одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-109">The script and the directory where it's stored must use the same name.</span></span> <span data-ttu-id="dbcb6-110">Например, сценарий с именем `MyPsScript.psm1` хранится в каталоге с именем `MyPsScript`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-110">For example, a script named `MyPsScript.psm1` is stored in a directory named `MyPsScript`.</span></span>

<span data-ttu-id="dbcb6-111">Каталог модуля должен находиться в пути, указанном в `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-111">The module's directory needs to be in a path specified in `$env:PSModulePath`.</span></span> <span data-ttu-id="dbcb6-112">Каталог модуля может содержать любые ресурсы, необходимые для выполнения скрипта, и файл манифеста модуля, который описывает, как работает ваш модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-112">The module's directory can contain any resources that are needed to run the script, and a module manifest file that describes to PowerShell how your module works.</span></span>

## <a name="create-a-basic-powershell-module"></a><span data-ttu-id="dbcb6-113">Создание базового модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbcb6-113">Create a basic PowerShell module</span></span>

<span data-ttu-id="dbcb6-114">Следующие шаги описывают создание модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-114">The following steps describe how to create a PowerShell module.</span></span>

1. <span data-ttu-id="dbcb6-115">Сохраните скрипт PowerShell с расширением `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-115">Save a PowerShell script with a `.psm1` extension.</span></span> <span data-ttu-id="dbcb6-116">Используйте то же имя для скрипта и каталога, в котором сохранен скрипт.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-116">Use the same name for the script and the directory where the script is saved.</span></span>

   <span data-ttu-id="dbcb6-117">Сохранение скрипта с расширением `.psm1` означает, что можно использовать командлеты модуля, такие как [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-117">Saving a script with the `.psm1` extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span> <span data-ttu-id="dbcb6-118">Командлеты модуля существуют главным образом, чтобы можно было импортировать и экспортировать код в системы других пользователей.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-118">The module cmdlets exist primarily so that you can import and export your code onto other user's systems.</span></span> <span data-ttu-id="dbcb6-119">Альтернативное решение — загрузить код в другие системы, а затем попытаться передать его в активную память, что не является масштабируемым решением.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-119">The alternate solution would be to load your code on other systems and then dot-source it into active memory, which isn't a scalable solution.</span></span> <span data-ttu-id="dbcb6-120">Дополнительные сведения см. [в разделе понятие о модуле Windows PowerShell](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-120">For more information, see [Understanding a Windows PowerShell Module](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).</span></span>
   <span data-ttu-id="dbcb6-121">По умолчанию, когда пользователи импортируют файл `.psm1`, все функции в скрипте доступны, но переменные нет.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-121">By default, when users import your `.psm1` file, all functions in your script are accessible, but variables aren't.</span></span>

   <span data-ttu-id="dbcb6-122">Пример скрипта PowerShell, озаглавленный `Show-Calendar`, можно найти в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-122">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this article.</span></span>

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

2. <span data-ttu-id="dbcb6-123">Чтобы управлять доступом пользователей к определенным функциям или переменным, вызовите [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-123">To control user access to certain functions or variables, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="dbcb6-124">В примере кода в нижней части статьи имеется только одна функция, которая по умолчанию будет предоставляться.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-124">The example code at the bottom of the article has only one function, which by default would be exposed.</span></span> <span data-ttu-id="dbcb6-125">Однако рекомендуется явно вызывать функции, которые необходимо предоставить, как описано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="dbcb6-125">However, it's recommended you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="dbcb6-126">Вы можете ограничить импортируемые объекты с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-126">You can restrict what's imported using a module manifest.</span></span> <span data-ttu-id="dbcb6-127">Дополнительные сведения см. в статьях [Импорт модуля PowerShell](./importing-a-powershell-module.md) и [написание манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-127">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="dbcb6-128">Если у вас есть модули, необходимые для загрузки вашего модуля, можно использовать `Import-Module`в верхней части модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-128">If you have modules that your own module needs to load, you can use `Import-Module`, at the top of your module.</span></span>

   <span data-ttu-id="dbcb6-129">Командлет `Import-Module` импортирует целевой модуль в систему и может использоваться позднее в процедуре установки собственного модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-129">The `Import-Module` cmdlet imports a targeted module onto a system, and can be used at a later point in the procedure to install your own module.</span></span> <span data-ttu-id="dbcb6-130">В примере кода в нижней части этой статьи не используются модули импорта.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-130">The sample code at the bottom of this article doesn't use any import modules.</span></span> <span data-ttu-id="dbcb6-131">Но если это так, они будут перечислены в верхней части файла, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="dbcb6-131">But if it did, they would be listed at the top of the file, as shown in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="dbcb6-132">Чтобы описать модуль в справочной системе PowerShell, можно либо использовать стандартные комментарии в файле справки, либо создать дополнительный файл справки.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-132">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="dbcb6-133">Пример кода в нижней части этой статьи содержит справочную информацию в комментариях.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-133">The code sample at the bottom of this article includes the help information in the comments.</span></span> <span data-ttu-id="dbcb6-134">Можно также написать развернутые XML-файлы, содержащие дополнительное содержимое справки.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-134">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="dbcb6-135">Дополнительные сведения см. в разделе [Создание справки для модулей Windows PowerShell](./writing-help-for-windows-powershell-modules.md).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-135">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="dbcb6-136">Если у вас есть дополнительные модули, файлы XML или другое содержимое, которое нужно упаковать с модулем, можно использовать манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-136">If you have additional modules, XML files, or other content you want to package with your module, you can use a module manifest.</span></span>

   <span data-ttu-id="dbcb6-137">Манифест модуля — это файл, содержащий имена других модулей, макетов каталогов, Номера версий, данные автора и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-137">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="dbcb6-138">PowerShell использует файл манифеста модуля для Организации и развертывания решения.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-138">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="dbcb6-139">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-139">For more information, see [How to write a PowerShell module manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="dbcb6-140">Чтобы установить и запустить модуль, сохраните модуль в один из соответствующих путей PowerShell и используйте `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-140">To install and run your module, save the module to one of the appropriate PowerShell paths, and use `Import-Module`.</span></span>

   <span data-ttu-id="dbcb6-141">Пути, по которым можно установить модуль, находятся в глобальной переменной `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-141">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="dbcb6-142">Например, общий путь для сохранения модуля в системе будет `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-142">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="dbcb6-143">Не забудьте создать каталог для модуля, который использует то же имя, что и модуль скрипта, даже если это единственный файл `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-143">Be sure to create a directory for your module that uses the same name as the script module, even if it's only a single `.psm1` file.</span></span> <span data-ttu-id="dbcb6-144">Если модуль не был сохранен по одному из этих путей, необходимо указать расположение модуля в команде `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-144">If you didn't save your module to one of these paths, you would have to specify the module's location in the `Import-Module` command.</span></span> <span data-ttu-id="dbcb6-145">В противном случае PowerShell не сможет найти модуль.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-145">Otherwise, PowerShell wouldn't be able to find the module.</span></span>

   <span data-ttu-id="dbcb6-146">Начиная с PowerShell 3,0, если модуль помещен в один из путей модуля PowerShell, его не нужно явным образом импортировать.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-146">Starting with PowerShell 3.0, if you've placed your module in one of the PowerShell module paths, you don't need to explicitly import it.</span></span> <span data-ttu-id="dbcb6-147">Модуль автоматически загружается, когда пользователь вызывает функцию.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-147">Your module is automatically loaded when a user calls your function.</span></span> <span data-ttu-id="dbcb6-148">Дополнительные сведения о пути к модулю см. в разделе [Импорт модуля PowerShell](./importing-a-powershell-module.md) и [изменение пути установки PSModulePath](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-148">For more information about the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [Modifying the PSModulePath Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="dbcb6-149">Чтобы удалить модуль из активной службы в текущем сеансе PowerShell, используйте [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="dbcb6-149">To remove a module from active service in the current PowerShell session, use [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   > [!NOTE]
   > <span data-ttu-id="dbcb6-150">`Remove-Module` удалит модуль из текущего сеанса PowerShell, но не удаляет модуль или файлы модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-150">`Remove-Module` removes a module from the current PowerShell session, but doesn't uninstall the module or delete the module's files.</span></span>

## <a name="show-calendar-code-example"></a><span data-ttu-id="dbcb6-151">Пример кода для показа календаря</span><span class="sxs-lookup"><span data-stu-id="dbcb6-151">Show-Calendar code example</span></span>

<span data-ttu-id="dbcb6-152">В следующем примере представлен модуль скрипта, содержащий одну функцию с именем `Show-Calendar`.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-152">The following example is a script module that contains a single function named `Show-Calendar`.</span></span> <span data-ttu-id="dbcb6-153">Эта функция отображает визуальное представление календаря.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-153">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="dbcb6-154">Образец содержит строки справки PowerShell для кратких сведений, описания, значений параметров и кода.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-154">The sample contains the PowerShell Help strings for the synopsis, description, parameter values, and code.</span></span> <span data-ttu-id="dbcb6-155">При импорте модуля команда `Export-ModuleMember` гарантирует, что функция `Show-Calendar` будет экспортирована в качестве члена модуля.</span><span class="sxs-lookup"><span data-stu-id="dbcb6-155">When the module is imported, the `Export-ModuleMember` command ensures that the `Show-Calendar` function is exported as a module member.</span></span>

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
