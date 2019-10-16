---
title: Примеры справки на основе комментариев | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 868194a2-17e9-4184-bc36-c04a33f26494
caps.latest.revision: 4
ms.openlocfilehash: 30e98bfcf06b1720005a73ee8294aeba7e1ae066
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367823"
---
# <a name="examples-of-comment-based-help"></a><span data-ttu-id="33788-102">Примеры справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="33788-102">Examples of Comment-Based Help</span></span>

<span data-ttu-id="33788-103">Этот раздел содержит пример, демонстрирующий использование справки на основе комментариев для скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="33788-103">This topic includes example that demonstrate how to use comment-based help for scripts and functions.</span></span>

## <a name="example-1-comment-based-help-for-a-function"></a><span data-ttu-id="33788-104">Пример 1. Справка на основе комментариев для функции</span><span class="sxs-lookup"><span data-stu-id="33788-104">Example 1: Comment-Based Help for a Function</span></span>

 <span data-ttu-id="33788-105">Следующий пример функции включает в себя справку на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="33788-105">The following sample function includes comment-based Help.</span></span>

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

<span data-ttu-id="33788-106">В следующем выводе показаны результаты команды Get-Help, в которой отображается справка по функции Add-Extension.</span><span class="sxs-lookup"><span data-stu-id="33788-106">The following output shows the results of a Get-Help command that displays the help for the Add-Extension function.</span></span>

```powershell
C:\PS> get-help add-extension -full
```

```output
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

## <a name="example-2-comment-based-help-for-a-script"></a><span data-ttu-id="33788-107">Пример 2. Справка на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="33788-107">Example 2: Comment-Based Help for a Script</span></span>

<span data-ttu-id="33788-108">Следующий пример функции включает в себя справку на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="33788-108">The following sample function includes comment-based Help.</span></span>

<span data-ttu-id="33788-109">Обратите внимание на пустые строки между закрывающим **#>** и оператором `Param`.</span><span class="sxs-lookup"><span data-stu-id="33788-109">Notice the blank lines between the closing **#>** and the `Param` statement.</span></span> <span data-ttu-id="33788-110">В скрипте, не имеющем оператора `Param`, между последним комментарием в разделе справки и первым объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="33788-110">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the Help topic and the first function declaration.</span></span> <span data-ttu-id="33788-111">Без этих пустых строк Get-Help связывает раздел справки с функцией, а не со сценарием.</span><span class="sxs-lookup"><span data-stu-id="33788-111">Without these blank lines, Get-Help associates the Help topic with the function, instead of the script.</span></span>

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

<span data-ttu-id="33788-112">Следующая команда получает справку по скрипту.</span><span class="sxs-lookup"><span data-stu-id="33788-112">The following command gets the script Help.</span></span> <span data-ttu-id="33788-113">Так как скрипт не имеет n каталога, указанного в переменной среды PATH, команда Get-Help, которая получает справку по скрипту, должна указать путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="33788-113">Because the script is not n a directory that is listed in the Path environment variable, the Get-Help command that gets the script Help must specify the script path.</span></span>

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```output
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

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a><span data-ttu-id="33788-114">Пример 3. описания параметров в операторе param</span><span class="sxs-lookup"><span data-stu-id="33788-114">Example 3: Parameter Descriptions in a Param Statement</span></span>

<span data-ttu-id="33788-115">В этом примере показано, как вставить параметердескриптионс в инструкцию `Param` функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="33788-115">This example show how to insert parameterdescriptions in the `Param` statement of a function or script.</span></span> <span data-ttu-id="33788-116">Этот формат наиболее удобен, если описания параметров являются краткими.</span><span class="sxs-lookup"><span data-stu-id="33788-116">This format is most useful when the parameter descriptions are brief.</span></span>

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

<span data-ttu-id="33788-117">Результаты совпадают с результатами примера 1.</span><span class="sxs-lookup"><span data-stu-id="33788-117">The results are the same as the results for Example 1.</span></span> <span data-ttu-id="33788-118">Командлет Get-Help интерпретирует описания параметров так, как будто они сопровождаются ключевым словом `.Parameter`.</span><span class="sxs-lookup"><span data-stu-id="33788-118">Get-Help interprets the parameter descriptions as though they were accompanied by the `.Parameter` keyword.</span></span>

## <a name="example-4--redirecting-to-an-xml-file"></a><span data-ttu-id="33788-119">Пример 4. перенаправление в XML-файл</span><span class="sxs-lookup"><span data-stu-id="33788-119">Example 4:  Redirecting to an XML File</span></span>

<span data-ttu-id="33788-120">Вы можете писать разделы справки на основе XML для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="33788-120">You can write XML-based Help topics for functions and scripts.</span></span> <span data-ttu-id="33788-121">Несмотря на то, что справку на основе комментариев проще реализовать, Справка на основе XML необходима, если требуется более точное управление содержимым справки или при преобразовании разделов справки на несколько языков. В следующем примере показаны первые несколько строк сценария Упдате-Монс. ps1.</span><span class="sxs-lookup"><span data-stu-id="33788-121">Although comment-based Help is easier to implement, XML-based Help is required if you want more precise control over Help content or if you are translating Help topics into multiple languages.The following example shows the first few lines of the Update-Month.ps1 script.</span></span> <span data-ttu-id="33788-122">В скрипте используется ключевое слово `.ExternalHelp`, чтобы указать путь к разделу справки на основе XML для скрипта.</span><span class="sxs-lookup"><span data-stu-id="33788-122">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based Help topic for the script.</span></span>

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

<span data-ttu-id="33788-123">В следующем примере показано использование ключевого слова `.ExternalHelp` в функции.</span><span class="sxs-lookup"><span data-stu-id="33788-123">The following example shows the use of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a><span data-ttu-id="33788-124">Пример 5. перенаправление на другой раздел справки</span><span class="sxs-lookup"><span data-stu-id="33788-124">Example 5:  Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="33788-125">Следующий код является выдержкой из начала встроенной функции `Help` в Windows PowerShell, которая отображает один экран текста справки за раз.</span><span class="sxs-lookup"><span data-stu-id="33788-125">The following code is an excerpt from the beginning of the built-in `Help` function in Windows PowerShell, which displays one screen of Help text at a time.</span></span> <span data-ttu-id="33788-126">Поскольку раздел справки для командлета Get-Help описывает функцию Help, функция Help использует ключевые слова `.ForwardHelpTargetName` и `.ForwardHelpCategory` для перенаправления пользователя в раздел справки по командлету Get-Help.</span><span class="sxs-lookup"><span data-stu-id="33788-126">Because the Help topic for the Get-Help cmdlet describes the Help function, the Help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the Get-Help cmdlet Help topic.</span></span>

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

<span data-ttu-id="33788-127">Эта функция используется в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="33788-127">The following command uses this feature.</span></span> <span data-ttu-id="33788-128">Когда пользователь вводит команду Get-Help для функции Help, команда Get-Help выводит раздел справки для командлета Get-Help.</span><span class="sxs-lookup"><span data-stu-id="33788-128">When a user types a Get-Help command for the Help function, Get-Help displays the Help topic for the Get-Help cmdlet.</span></span>

```powershell
C:\PS> get-help help
```

```output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```