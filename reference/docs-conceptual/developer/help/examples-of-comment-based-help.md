---
title: Примеры справки на основе комментариев
ms.date: 09/12/2016
ms.openlocfilehash: 3858fa7f15d71c505dacaf9679910d45ef4640e5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893498"
---
# <a name="examples-of-comment-based-help"></a><span data-ttu-id="1b85b-102">Примеры справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="1b85b-102">Examples of Comment-Based Help</span></span>

<span data-ttu-id="1b85b-103">Этот раздел содержит пример, демонстрирующий использование справки на основе комментариев для скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="1b85b-103">This topic includes example that demonstrate how to use comment-based help for scripts and functions.</span></span>

## <a name="example-1-comment-based-help-for-a-function"></a><span data-ttu-id="1b85b-104">Пример 1. Справка на основе комментариев для функции</span><span class="sxs-lookup"><span data-stu-id="1b85b-104">Example 1: Comment-Based Help for a Function</span></span>

 <span data-ttu-id="1b85b-105">Следующий пример функции включает в себя справку на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="1b85b-105">The following sample function includes comment-based Help.</span></span>

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
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

<span data-ttu-id="1b85b-106">В следующем выводе показаны результаты `Get-Help` команды, которая отображает справку для `Add-Extension` функции.</span><span class="sxs-lookup"><span data-stu-id="1b85b-106">The following output shows the results of a `Get-Help` command that displays the help for the `Add-Extension` function.</span></span>

```powershell
C:\PS> get-help add-extension -full
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

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a><span data-ttu-id="1b85b-107">Пример 2. Справка на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="1b85b-107">Example 2: Comment-Based Help for a Script</span></span>

<span data-ttu-id="1b85b-108">Следующий пример функции включает в себя справку на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="1b85b-108">The following sample function includes comment-based Help.</span></span>

<span data-ttu-id="1b85b-109">Обратите внимание на пустые строки между закрывающим **#>** и `Param` оператором.</span><span class="sxs-lookup"><span data-stu-id="1b85b-109">Notice the blank lines between the closing **#>** and the `Param` statement.</span></span> <span data-ttu-id="1b85b-110">В скрипте, не имеющем `Param` оператора, в разделе справки и первом объявлении функции должно быть по крайней мере две пустые строки между последним комментарием.</span><span class="sxs-lookup"><span data-stu-id="1b85b-110">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the Help topic and the first function declaration.</span></span> <span data-ttu-id="1b85b-111">Без этих пустых строк `Get-Help` связывает раздел справки с функцией, а не со сценарием.</span><span class="sxs-lookup"><span data-stu-id="1b85b-111">Without these blank lines, `Get-Help` associates the Help topic with the function, instead of the script.</span></span>

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
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

<span data-ttu-id="1b85b-112">Следующая команда получает справку по скрипту.</span><span class="sxs-lookup"><span data-stu-id="1b85b-112">The following command gets the script Help.</span></span> <span data-ttu-id="1b85b-113">Так как скрипт не находится в каталоге, указанном в переменной среды PATH, `Get-Help` команда, которая получает справку по скрипту, должна указывать путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="1b85b-113">Because the script is not in a directory that is listed in the Path environment variable, the `Get-Help` command that gets the script Help must specify the script path.</span></span>

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
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

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a><span data-ttu-id="1b85b-114">Пример 3. описания параметров в операторе param</span><span class="sxs-lookup"><span data-stu-id="1b85b-114">Example 3: Parameter Descriptions in a Param Statement</span></span>

<span data-ttu-id="1b85b-115">В этом примере показано, как вставлять описания параметров в `Param` операторе функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="1b85b-115">This example shows how to insert parameter descriptions in the `Param` statement of a function or script.</span></span> <span data-ttu-id="1b85b-116">Этот формат наиболее удобен, если описания параметров являются краткими.</span><span class="sxs-lookup"><span data-stu-id="1b85b-116">This format is most useful when the parameter descriptions are brief.</span></span>

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

<span data-ttu-id="1b85b-117">Результаты совпадают с результатами примера 1.</span><span class="sxs-lookup"><span data-stu-id="1b85b-117">The results are the same as the results for Example 1.</span></span> <span data-ttu-id="1b85b-118">`Get-Help`интерпретирует описания параметров так, как если бы они были снабжены `.Parameter` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="1b85b-118">`Get-Help` interprets the parameter descriptions as though they were accompanied by the `.Parameter` keyword.</span></span>

## <a name="example-4--redirecting-to-an-xml-file"></a><span data-ttu-id="1b85b-119">Пример 4. перенаправление в XML-файл</span><span class="sxs-lookup"><span data-stu-id="1b85b-119">Example 4:  Redirecting to an XML File</span></span>

<span data-ttu-id="1b85b-120">Вы можете писать разделы справки на основе XML для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="1b85b-120">You can write XML-based Help topics for functions and scripts.</span></span> <span data-ttu-id="1b85b-121">Несмотря на то, что справку на основе комментариев проще реализовать, Справка на основе XML необходима, если требуется более точное управление содержимым справки или при преобразовании разделов справки на несколько языков. В следующем примере показаны первые несколько строк `Update-Month.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="1b85b-121">Although comment-based Help is easier to implement, XML-based Help is required if you want more precise control over Help content or if you are translating Help topics into multiple languages.The following example shows the first few lines of the `Update-Month.ps1` script.</span></span> <span data-ttu-id="1b85b-122">В скрипте используется `.ExternalHelp` ключевое слово, чтобы указать путь к разделу справки на основе XML для скрипта.</span><span class="sxs-lookup"><span data-stu-id="1b85b-122">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based Help topic for the script.</span></span>

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

<span data-ttu-id="1b85b-123">В следующем примере показано использование `.ExternalHelp` ключевого слова в функции.</span><span class="sxs-lookup"><span data-stu-id="1b85b-123">The following example shows the use of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a><span data-ttu-id="1b85b-124">Пример 5. перенаправление на другой раздел справки</span><span class="sxs-lookup"><span data-stu-id="1b85b-124">Example 5:  Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="1b85b-125">Следующий код является выдержкой из начала встроенной `Help` функции в PowerShell, которая отображает один экран текста справки за раз.</span><span class="sxs-lookup"><span data-stu-id="1b85b-125">The following code is an excerpt from the beginning of the built-in `Help` function in PowerShell, which displays one screen of Help text at a time.</span></span> <span data-ttu-id="1b85b-126">Поскольку раздел справки для командлета Get-Help описывает функцию Help, функция Help использует `.ForwardHelpTargetName` `.ForwardHelpCategory` Ключевые слова и для перенаправления пользователя в раздел справки по командлету Get-Help.</span><span class="sxs-lookup"><span data-stu-id="1b85b-126">Because the Help topic for the Get-Help cmdlet describes the Help function, the Help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the Get-Help cmdlet Help topic.</span></span>

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

<span data-ttu-id="1b85b-127">Эта функция используется в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="1b85b-127">The following command uses this feature.</span></span> <span data-ttu-id="1b85b-128">Когда пользователь вводит `Get-Help` команду для `Help` функции, `Get-Help` выводит раздел справки для `Get-Help` командлета.</span><span class="sxs-lookup"><span data-stu-id="1b85b-128">When a user types a `Get-Help` command for the `Help` function, `Get-Help` displays the Help topic for the `Get-Help` cmdlet.</span></span>

```powershell
C:\PS> get-help help
```

```Output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```
