---
ms.date: 11/21/2019
ms.topic: reference
title: Как написать модуль сценария PowerShell
description: Как написать модуль сценария PowerShell
ms.openlocfilehash: c44b09a915501fb10773ab11cf13136d5035ba69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649142"
---
# <a name="how-to-write-a-powershell-script-module"></a>Как написать модуль сценария PowerShell

Модуль скрипта — это любой допустимый сценарий PowerShell, сохраненный в `.psm1` расширении. Это расширение позволяет подсистеме PowerShell использовать правила и командлеты модуля в файле. Большая часть этих возможностей заключается в том, чтобы помочь вам установить код в других системах, а также управлять областями. Можно также использовать файл манифеста модуля, который описывает более сложные установки и решения.

## <a name="writing-a-powershell-script-module"></a>Написание модуля скрипта PowerShell

Чтобы создать модуль скрипта, сохраните в файл допустимый сценарий PowerShell `.psm1` . Скрипт и каталог, в котором он хранится, должны использовать одно и то же имя. Например, сценарий с именем `MyPsScript.psm1` хранится в каталоге с именем `MyPsScript` .

Каталог модуля должен находиться в пути, указанном в `$env:PSModulePath` . Каталог модуля может содержать любые ресурсы, необходимые для выполнения скрипта, и файл манифеста модуля, который описывает, как работает ваш модуль PowerShell.

## <a name="create-a-basic-powershell-module"></a>Создание базового модуля PowerShell

Следующие шаги описывают создание модуля PowerShell.

1. Сохраните сценарий PowerShell с `.psm1` расширением. Используйте то же имя для скрипта и каталога, в котором сохранен скрипт.

   Сохранение скрипта с `.psm1` расширением означает, что вы можете использовать командлеты модуля, такие как [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module). Командлеты модуля существуют главным образом, чтобы можно было импортировать и экспортировать код в системы других пользователей. Альтернативное решение — загрузить код в другие системы, а затем попытаться передать его в активную память, что не является масштабируемым решением. Дополнительные сведения см. [в разделе понятие о модуле Windows PowerShell](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).
   По умолчанию, когда пользователь импортирует `.psm1` файл, все функции в скрипте доступны, но переменные нет.

   Пример сценария PowerShell, озаглавленный `Show-Calendar` , доступен в конце этой статьи.

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

2. Чтобы управлять доступом пользователей к определенным функциям или переменным, вызовите [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) в конце скрипта.

   В примере кода в нижней части статьи имеется только одна функция, которая по умолчанию будет предоставляться. Однако рекомендуется явно вызывать функции, которые необходимо предоставить, как описано в следующем коде:

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   Вы можете ограничить импортируемые объекты с помощью манифеста модуля. Дополнительные сведения см. в статьях [Импорт модуля PowerShell](./importing-a-powershell-module.md) и [написание манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).

3. Если у вас есть модули, необходимые для загрузки вашего модуля, `Import-Module` в верхней части модуля можно использовать.

   `Import-Module`Командлет импортирует целевой модуль в систему и может использоваться позднее в процедуре установки собственного модуля. В примере кода в нижней части этой статьи не используются модули импорта. Но если это так, они будут перечислены в верхней части файла, как показано в следующем коде:

   ```powershell
   Import-Module GenericModule
   ```

4. Чтобы описать модуль в справочной системе PowerShell, можно либо использовать стандартные комментарии в файле справки, либо создать дополнительный файл справки.

   Пример кода в нижней части этой статьи содержит справочную информацию в комментариях. Можно также написать развернутые XML-файлы, содержащие дополнительное содержимое справки. Дополнительные сведения см. в разделе [Создание справки для модулей Windows PowerShell](./writing-help-for-windows-powershell-modules.md).

5. Если у вас есть дополнительные модули, файлы XML или другое содержимое, которое нужно упаковать с модулем, можно использовать манифест модуля.

   Манифест модуля — это файл, содержащий имена других модулей, макетов каталогов, Номера версий, данные автора и другие сведения. PowerShell использует файл манифеста модуля для Организации и развертывания решения. Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](./how-to-write-a-powershell-module-manifest.md).

6. Чтобы установить и запустить модуль, сохраните модуль в один из соответствующих путей PowerShell и используйте `Import-Module` .

   Пути, по которым можно установить модуль, находятся в `$env:PSModulePath` глобальной переменной. Например, общий путь для сохранения модуля в системе — `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>` . Не забудьте создать каталог для модуля, который использует то же имя, что и модуль скрипта, даже если это единственный `.psm1` файл. Если модуль не был сохранен по одному из этих путей, необходимо указать расположение модуля в `Import-Module` команде. В противном случае PowerShell не сможет найти модуль.

   Начиная с PowerShell 3,0, если модуль помещен в один из путей модуля PowerShell, его не нужно явным образом импортировать. Модуль автоматически загружается, когда пользователь вызывает функцию. Дополнительные сведения о пути к модулю см. в разделе [Импорт модуля PowerShell](./importing-a-powershell-module.md) и [изменение пути установки PSModulePath](./modifying-the-psmodulepath-installation-path.md).

7. Чтобы удалить модуль из активной службы в текущем сеансе PowerShell, используйте [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).

   > [!NOTE]
   > `Remove-Module` Удаление модуля из текущего сеанса PowerShell, но не удаление модуля или файлов модуля.

## <a name="show-calendar-code-example"></a>Пример кода Show-Calendar

В следующем примере представлен модуль скрипта, содержащий одну функцию с именем `Show-Calendar` . Эта функция отображает визуальное представление календаря. Образец содержит строки справки PowerShell для кратких сведений, описания, значений параметров и кода. При импорте модуля `Export-ModuleMember` команда обеспечивает `Show-Calendar` экспорт функции в качестве члена модуля.

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
