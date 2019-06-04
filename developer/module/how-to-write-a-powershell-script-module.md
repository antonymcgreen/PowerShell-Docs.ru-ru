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
# <a name="how-to-write-a-powershell-script-module"></a>Как написать модуль сценария PowerShell

Модуль сценария — по сути любой допустимый скрипт PowerShell сохранен в расширение .psm1. Это расширение позволяет модулю PowerShell для использования нескольких правил и командлеты для файла. Большинство из этих возможностей предназначены для установки кода в других системах, а также управлять области. Можно также использовать файл манифеста модуля, позволяют описывать еще более сложной установки и решений.

## <a name="writing-a-powershell-script-module"></a>Написание модуля сценария PowerShell

Создайте модуль сценария, сохранив это допустимый скрипт PowerShell в файле с расширением psm1, а затем сохраните этот файл в каталог где его можно найти PowerShell. В этой папке, их также можно разместить все ресурсы, необходимые для запуска скрипта а также файл манифеста, описывающий для PowerShell как работает модуль.

#### <a name="to-create-a-basic-powershell-module"></a>Чтобы создать базовый модуль PowerShell

1. Использовать существующий скрипт PowerShell и сохраните сценарий с расширением .psm1.

   Сохранение скрипта с помощью .psm1 расширения означает, что можно использовать командлеты модуля, такие как [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), на нем. Эти командлеты существует, то, что вы можете легко импортировать и экспортировать код на компьютерах других пользователей. (Альтернативное решение следует загрузить код на других системах, а затем с точкой в активной памяти, который не является особенно масштабируемым решением.) Дополнительные сведения см. в разделе **командлеты модуля и переменные** статьи [модули Windows PowerShell](./understanding-a-windows-powershell-module.md) Обратите внимание, что, по умолчанию все функции в скрипте, доступны для пользователей, импортируйте файл .psm1 но свойства не являются.

   Пример сценария PowerShell, имеют право `Show-Calendar`, доступна в конце этого раздела.

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

2. Для управления доступом пользователей к определенным функции или свойства, вызовите [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) в конце скрипта.

   В примере кода, в нижней части страницы имеет только одну функцию, которая по умолчанию предоставлялась бы. Тем не менее рекомендуется явно вызывать out какие функции, которую нужно предоставить, как описано в следующем коде:

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   Также можно ограничить, что импортируется с помощью манифеста модуля. Дополнительные сведения см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md) и [как написание манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).

3. Если у вас есть собственный модуль, необходимые для загрузки модулей, их можно использовать с вызовом `Import-Module`, в верхней части своего модуля.

   `Import-Module` — Это командлет, который импортирует модуль целевой системе. Таким образом он также используется позже в процедуре для установки также собственный модуль. Пример кода, в нижней части этой страницы не использует каких-либо импорт модулей. Если они были, тем не менее, они будут перечислены в верхней части файла, как описано в следующем коде:

   ```powershell
   Import-Module GenericModule
   ```

4. Для описания вашего модуля в PowerShell справочную систему, можно использовать комментарии Стандартная Справка внутри файла или создать дополнительный файл справки.

   Пример кода в конце этого раздела включает справочные сведения в комментариях. Можно также написать извлеченные файлы XML, содержащие дополнительное содержимое справки. Дополнительные сведения см. в разделе [написание справки для Windows PowerShell модулей](./writing-help-for-windows-powershell-modules.md).

5. Если у вас есть дополнительные модули, XML-файлы или другие сведения, которые вы хотите упаковать с модулем, это можно сделать с помощью манифеста модуля.

   Манифест модуля — это файл, который содержит имена других модулей, макеты каталогов, управление версиями чисел, автор данных и другие фрагменты данных. PowerShell использует файл манифеста модуля для организации и развертывания решения. Тем не менее из-за относительно простым устройством в этом примере, файл манифеста не требовалось. Дополнительные сведения см. в разделе [манифесты модуля](./how-to-write-a-powershell-module-manifest.md).

6. Для установки и запуска вашего модуля, сохраните модуль соответствующие пути PowerShell и вызвать `Import-Module`.

   Пути, где можно установить модуль, находятся в `$env:PSModulePath` глобальной переменной. Например, общий путь для сохранения модуля в системе будет `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`. Не забудьте создать папку для вашего модуля должно существовать, даже если это только один .psm1 файл. Если вы не сохраняли вашего модуля к одному из этих путей, пришлось бы передать в расположение модуля в вызове `Import-Module`. (В противном случае PowerShell не сможет найти его.) Начиная с PowerShell 3.0, если вы разместили вашего модуля в одном из пути к модулям PowerShell, вы не обязательно должны явно импортирующих его. Вы модуль загружается автоматически в том случае, когда пользователь вызывает функции.
   Дополнительные сведения о пути к модулю, см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md) и [переменной среды PSModulePath](./modifying-the-psmodulepath-installation-path.md).

7. Чтобы удалить модуль из активной службой, сделать вызов к [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).

   Обратите внимание, что [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) удаляет модуль из активной памяти — он фактически не удаляются его из которых были сохранены файлы модуля.

### <a name="show-calendar-code-example"></a>Пример кода show-Calendar

Ниже приведен простой сценарий модуль, содержащий одну функцию с именем `Show-Calendar`.
Эта функция отображает визуальное представление календаря. Кроме того пример содержит строки справки PowerShell краткий обзор, описание и значения параметров, а также пример. Обратите внимание, что последняя строка кода гарантирует, что `Show-Calendar` функция экспортируется как член модуля при импорте модуля.

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
