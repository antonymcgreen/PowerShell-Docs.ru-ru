---
description: Описывает, как определять и использовать наборы параметров в дополнительных функциях.
title: about_Parameter_Sets
ms.date: 01/05/2021
ms.openlocfilehash: 8f3a33345a8e2fa19810c8ebd527d9a7dca7dec5
ms.sourcegitcommit: eb7ad1850550032880f5529b4e4281514cba1673
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97917865"
---
# <a name="about-parameter-sets"></a><span data-ttu-id="fb27c-103">О наборах параметров</span><span class="sxs-lookup"><span data-stu-id="fb27c-103">About parameter sets</span></span>

## <a name="short-description"></a><span data-ttu-id="fb27c-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fb27c-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="fb27c-105">Описывает, как определять и использовать наборы параметров в дополнительных функциях.</span><span class="sxs-lookup"><span data-stu-id="fb27c-105">Describes how to define and use parameter sets in advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="fb27c-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fb27c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="fb27c-107">В PowerShell используются наборы параметров, позволяющие написать одну функцию, которая может выполнять различные действия в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="fb27c-107">PowerShell uses parameter sets to enable you to write a single function that can do different actions for different scenarios.</span></span> <span data-ttu-id="fb27c-108">Наборы параметров позволяют предоставлять пользователю различные параметры.</span><span class="sxs-lookup"><span data-stu-id="fb27c-108">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="fb27c-109">И, чтобы получить различные сведения на основе параметров, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="fb27c-109">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="parameter-set-requirements"></a><span data-ttu-id="fb27c-110">Требования к наборам параметров</span><span class="sxs-lookup"><span data-stu-id="fb27c-110">Parameter set requirements</span></span>

<span data-ttu-id="fb27c-111">Следующие требования применяются ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-111">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="fb27c-112">Каждый набор параметров должен иметь уникальное сочетание параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-112">Each parameter set must have a unique combination of parameters.</span></span> <span data-ttu-id="fb27c-113">По возможности, по крайней мере один из уникальных параметров должен быть обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="fb27c-113">If possible, at least one of the unique parameters should be a mandatory parameter.</span></span>

- <span data-ttu-id="fb27c-114">Набор параметров, содержащий несколько позиционированных параметров, должен определять уникальные позиции для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="fb27c-114">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="fb27c-115">Ни один из двух параметров позиционирования не может указывать одну и ту же точку.</span><span class="sxs-lookup"><span data-stu-id="fb27c-115">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="fb27c-116">Только один параметр в наборе может объявить `ValueFromPipeline` ключевое слово со значением `true` .</span><span class="sxs-lookup"><span data-stu-id="fb27c-116">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="fb27c-117">Несколько параметров могут определять `ValueFromPipelineByPropertyName` ключевое слово со значением `true` .</span><span class="sxs-lookup"><span data-stu-id="fb27c-117">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="fb27c-118">Если для параметра не задан набор параметров, параметр относится ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-118">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="fb27c-119">Существует ограничение в 32 наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-119">There is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="fb27c-120">Наборы параметров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb27c-120">Default parameter sets</span></span>

<span data-ttu-id="fb27c-121">Если определено несколько наборов параметров, `DefaultParameterSetName` ключевое слово атрибута **CmdletBinding** задает набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fb27c-121">When multiple parameter sets are defined, the `DefaultParameterSetName` keyword of the **CmdletBinding** attribute specifies the default parameter set.</span></span>
<span data-ttu-id="fb27c-122">PowerShell использует набор параметров по умолчанию, если не может определить набор параметров, используемый на основе сведений, предоставленных команде.</span><span class="sxs-lookup"><span data-stu-id="fb27c-122">PowerShell uses the default parameter set when it can't determine the parameter set to use based on the information provided to the command.</span></span> <span data-ttu-id="fb27c-123">Дополнительные сведения об атрибуте **CmdletBinding** см. в разделе [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span><span class="sxs-lookup"><span data-stu-id="fb27c-123">For more information about the **CmdletBinding** attribute, see [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="fb27c-124">Объявление наборов параметров</span><span class="sxs-lookup"><span data-stu-id="fb27c-124">Declaring parameter sets</span></span>

<span data-ttu-id="fb27c-125">Чтобы создать набор параметров, необходимо указать `ParameterSetName` ключевое слово атрибута **Parameter** для каждого параметра в наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-125">To create a parameter set, you must specify the `ParameterSetName` keyword of the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="fb27c-126">Для параметров, принадлежащих к нескольким наборам параметров, добавьте атрибут **параметра** для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-126">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span>

<span data-ttu-id="fb27c-127">Атрибут **Parameter** позволяет определить параметр по-разному для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-127">The **Parameter** attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="fb27c-128">Например, можно определить параметр как обязательный в одном наборе и необязательный в другом.</span><span class="sxs-lookup"><span data-stu-id="fb27c-128">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="fb27c-129">Однако каждый набор параметров должен содержать по крайней мере один уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="fb27c-129">However, each parameter set must contain at least one unique parameter.</span></span>

<span data-ttu-id="fb27c-130">Параметры, которым не назначено имя набора параметров, принадлежат ко всем наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-130">Parameters that don't have an assigned parameter set name belong to all parameter sets.</span></span>

### <a name="example"></a><span data-ttu-id="fb27c-131">Пример</span><span class="sxs-lookup"><span data-stu-id="fb27c-131">Example</span></span>

<span data-ttu-id="fb27c-132">В следующем примере функции подсчитывается число строк, символов и слов в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="fb27c-132">The following example function counts the number lines, characters, and words in a text file.</span></span> <span data-ttu-id="fb27c-133">С помощью параметров можно указать, какие значения должны возвращаться и какие файлы необходимо измерить.</span><span class="sxs-lookup"><span data-stu-id="fb27c-133">Using parameters, you can specify which values you want returned and which files you want to measure.</span></span> <span data-ttu-id="fb27c-134">Определены четыре набора параметров:</span><span class="sxs-lookup"><span data-stu-id="fb27c-134">There are four parameter sets defined:</span></span>

- <span data-ttu-id="fb27c-135">Путь</span><span class="sxs-lookup"><span data-stu-id="fb27c-135">Path</span></span>
- <span data-ttu-id="fb27c-136">пасалл</span><span class="sxs-lookup"><span data-stu-id="fb27c-136">PathAll</span></span>
- <span data-ttu-id="fb27c-137">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fb27c-137">LiteralPath</span></span>
- <span data-ttu-id="fb27c-138">литералпасалл</span><span class="sxs-lookup"><span data-stu-id="fb27c-138">LiteralPathAll</span></span>

```powershell
function Measure-Lines {
    [CmdletBinding(DefaultParameterSetName = 'Path')]
    param (
        [Parameter(Mandatory = $true,
            ParameterSetName = 'Path',
            HelpMessage = 'Enter one or more filenames',
            Position = 0)]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'PathAll',
            Position = 0)]
        [string[]]$Path,

        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'LiteralPath',
            HelpMessage = 'Enter a single filename',
            ValueFromPipeline = $true)]
        [string]$LiteralPath,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Lines,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Words,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Characters,

        [Parameter(Mandatory = $true, ParameterSetName = 'PathAll')]
        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [switch]$All,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'PathAll')]
        [switch]$Recurse
    )

    begin {
        if ($All) {
            $Lines = $Words = $Characters = $true
        }
        elseif (($Words -eq $false) -and ($Characters -eq $false)) {
            $Lines = $true
        }

        if ($Path) {
            $Files = Get-ChildItem -Path $Path -Recurse:$Recurse
        }
        else {
            $Files = Get-ChildItem -LiteralPath $LiteralPath
        }
    }
    process {
        foreach ($file in $Files) {
            $result = [ordered]@{ }
            $result.Add('File', $file.fullname)

            $content = Get-Content -LiteralPath $file.fullname

            if ($Lines) { $result.Add('Lines', $content.Length) }

            if ($Words) {
                $wc = 0
                foreach ($line in $content) { $wc += $line.split(' ').Length }
                $result.Add('Words', $wc)
            }

            if ($Characters) {
                $cc = 0
                foreach ($line in $content) { $cc += $line.Length }
                $result.Add('Characters', $cc)
            }

            New-Object -TypeName psobject -Property $result
        }
    }
}
```

<span data-ttu-id="fb27c-139">Каждый набор параметров должен иметь уникальный параметр или уникальное сочетание параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-139">Each parameter set must have a unique parameter or a unique combination of parameters.</span></span> <span data-ttu-id="fb27c-140">`Path` `PathAll` Наборы параметров и очень похожи, но параметр **ALL** уникален для `PathAll` набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-140">The `Path` and `PathAll` parameter sets are very similar but the **All** parameter is unique to the `PathAll` parameter set.</span></span> <span data-ttu-id="fb27c-141">То же самое справедливо и к `LiteralPath` `LiteralPathAll` наборам параметров и.</span><span class="sxs-lookup"><span data-stu-id="fb27c-141">The same is true with the `LiteralPath` and `LiteralPathAll` parameter sets.</span></span> <span data-ttu-id="fb27c-142">Несмотря на то, что `PathAll` `LiteralPathAll` оба набора параметров и имеют параметр **ALL** , параметры **path** и **LiteralPath** отличают их.</span><span class="sxs-lookup"><span data-stu-id="fb27c-142">Even though the `PathAll` and `LiteralPathAll` parameter sets both have the **All** parameter, the **Path** and **LiteralPath** parameters differentiate them.</span></span>

<span data-ttu-id="fb27c-143">Используется для `Get-Command -Syntax` отображения синтаксиса каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-143">Use `Get-Command -Syntax` shows you the syntax of each parameter set.</span></span> <span data-ttu-id="fb27c-144">Однако он не отображает имя набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-144">However it does not show the name of the parameter set.</span></span> <span data-ttu-id="fb27c-145">В следующем примере показано, какие параметры можно использовать в каждом наборе параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-145">The following example shows which parameters can be used in each parameter set.</span></span>

```powershell
(Get-Command Measure-Lines).ParameterSets |
  Select-Object -Property @{n='ParameterSetName';e={$_.name}},
    @{n='Parameters';e={$_.ToString()}}
```

```Output
ParameterSetName Parameters
---------------- ----------
Path             [-Path] <string[]> [-Lines] [-Words] [-Characters] [-Recurse] [<CommonParameters>]
PathAll          [-Path] <string[]> -All [-Recurse] [<CommonParameters>]
LiteralPath      -LiteralPath <string> [-Lines] [-Words] [-Characters] [<CommonParameters>]
LiteralPathAll   -LiteralPath <string> -All [<CommonParameters>]
```

### <a name="parameter-sets-in-action"></a><span data-ttu-id="fb27c-146">Наборы параметров в действии</span><span class="sxs-lookup"><span data-stu-id="fb27c-146">Parameter sets in action</span></span>

<span data-ttu-id="fb27c-147">В этом примере мы используем `PathAll` набор параметров.</span><span class="sxs-lookup"><span data-stu-id="fb27c-147">In this example, we are using the `PathAll` parameter set.</span></span>

```powershell
Measure-Lines test* -All
```

```Output
File                       Lines Words Characters
----                       ----- ----- ----------
C:\temp\test\test.help.txt    31   562       2059
C:\temp\test\test.md          30  1527       3224
C:\temp\test\test.ps1          3     3         79
C:\temp\test\test[1].txt      31   562       2059
```
