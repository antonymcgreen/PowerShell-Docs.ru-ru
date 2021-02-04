---
ms.date: 01/11/2021
ms.topic: reference
title: Примеры справки на основе комментариев
description: Примеры справки на основе комментариев
ms.openlocfilehash: 237e65c59cc3b35f48b6d667c8fb297994b03638
ms.sourcegitcommit: 4879b9cdfa3f03b04a07b84442dc1ca9ae0f6b46
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "98105168"
---
# <a name="examples-of-comment-based-help"></a>Примеры справки на основе комментариев

Этот раздел содержит пример, демонстрирующий использование справки на основе комментариев для скриптов и функций.

## <a name="example-1-comment-based-help-for-a-function"></a>Пример 1. Comment-Based справки по функции

 Следующий пример функции включает в себя справку на основе комментариев.

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        PS> extension -name "File"
        File.txt

        .EXAMPLE
        PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

В следующем выводе показаны результаты `Get-Help` команды, которая отображает справку для `Add-Extension` функции.

```powershell
PS> Get-Help Add-Extension -full
```

```Output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a>Пример 2. Comment-Based справки по сценарию

Следующий пример функции включает в себя справку на основе комментариев.

Обратите внимание на пустые строки между закрывающим **#>** и `Param` оператором. В скрипте, не имеющем `Param` оператора, в разделе справки и первом объявлении функции должно быть по крайней мере две пустые строки между последним комментарием. Без этих пустых строк `Get-Help` связывает раздел справки с функцией, а не со сценарием.

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  PS> .\Update-Month.ps1

  .EXAMPLE
  PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

Следующая команда получает справку по скрипту. Так как скрипт не находится в каталоге, указанном в переменной среды PATH, `Get-Help` команда, которая получает справку по скрипту, должна указывать путь к скрипту.

```powershell
PS> Get-Help c:\ps-test\update-month.ps1 -full
```

```Output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a>Пример 3. описания параметров в операторе param

В этом примере показано, как вставлять описания параметров в `Param` операторе функции или скрипта. Этот формат наиболее удобен, если описания параметров являются краткими.

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

Результаты совпадают с результатами примера 1. `Get-Help` интерпретирует описания параметров так, как если бы они были снабжены `.Parameter` ключевым словом.

## <a name="example-4--redirecting-to-an-xml-file"></a>Пример 4. перенаправление в XML-файл

Вы можете писать разделы справки на основе XML для функций и скриптов. Несмотря на то, что справку на основе комментариев проще реализовать, Справка на основе XML необходима, если требуется более точное управление содержимым справки или при преобразовании разделов справки на несколько языков. В следующем примере показаны первые несколько строк `Update-Month.ps1` скрипта. В скрипте используется `.ExternalHelp` ключевое слово, чтобы указать путь к разделу справки на основе XML для скрипта.

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

В следующем примере показано использование `.ExternalHelp` ключевого слова в функции.

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a>Пример 5. перенаправление на другой раздел справки

Следующий код является выдержкой из начала встроенной `Help` функции в PowerShell, которая отображает один экран текста справки за раз. Поскольку в разделе справки для командлета Get-Help описана функция справки, функция Help использует `.ForwardHelpTargetName` `.ForwardHelpCategory` Ключевые слова и для перенаправления пользователя в раздел справки по командлету Get-Help.

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

Эта функция используется в следующей команде. Когда пользователь вводит `Get-Help` команду для `Help` функции, `Get-Help` выводит раздел справки для `Get-Help` командлета.

```powershell
PS> get-help help
```

```Output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```
