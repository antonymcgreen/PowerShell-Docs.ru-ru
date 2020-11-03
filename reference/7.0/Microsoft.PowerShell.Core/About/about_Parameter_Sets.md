---
description: Описывает, как определять и использовать наборы параметров в дополнительных функциях.
title: about_Parameter_Sets
ms.date: 02/11/2020
ms.openlocfilehash: e4cfbc13f981bcc93c8a0a3c799851e83df7746c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232569"
---
# <a name="about-parameter-sets"></a>О наборах параметров

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает, как определять и использовать наборы параметров в дополнительных функциях.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

В PowerShell используются наборы параметров, позволяющие написать одну функцию, которая может выполнять различные действия в различных сценариях. Наборы параметров позволяют предоставлять пользователю различные параметры. И, чтобы получить различные сведения на основе параметров, указанных пользователем.

## <a name="parameter-set-requirements"></a>Требования к наборам параметров

Следующие требования применяются ко всем наборам параметров.

- Каждый набор параметров должен иметь по крайней мере один уникальный параметр. Если это возможно, присвоить этому параметру обязательный параметр.

- Набор параметров, содержащий несколько позиционированных параметров, должен определять уникальные позиции для каждого параметра. Ни один из двух параметров позиционирования не может указывать одну и ту же точку.

- Только один параметр в наборе может объявить `ValueFromPipeline` ключевое слово со значением `true` . Несколько параметров могут определять `ValueFromPipelineByPropertyName` ключевое слово со значением `true` .

- Если для параметра не задан набор параметров, параметр относится ко всем наборам параметров.

> [!NOTE]
> Существует ограничение в 32 наборов параметров.

## <a name="default-parameter-sets"></a>Наборы параметров по умолчанию

Если определено несколько наборов параметров, `DefaultParameterSetName` ключевое слово атрибута **CmdletBinding** задает набор параметров по умолчанию.
PowerShell использует набор параметров по умолчанию, если не может определить набор параметров, используемый на основе сведений, предоставленных команде. Дополнительные сведения об атрибуте **CmdletBinding** см. в разделе [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).

## <a name="declaring-parameter-sets"></a>Объявление наборов параметров

Чтобы создать набор параметров, необходимо указать `ParameterSetName` ключевое слово атрибута **Parameter** для каждого параметра в наборе параметров. Для параметров, принадлежащих к нескольким наборам параметров, добавьте атрибут **параметра** для каждого набора параметров.

Атрибут **Parameter** позволяет определить параметр по-разному для каждого набора параметров. Например, можно определить параметр как обязательный в одном наборе и необязательный в другом. Однако каждый набор параметров должен содержать по крайней мере один уникальный параметр.

Параметры, которым не назначено имя набора параметров, принадлежат ко всем наборам параметров.

### <a name="example"></a>Пример

В следующем примере функции подсчитывается число строк, символов и слов в текстовом файле. С помощью параметров можно указать, какие значения должны возвращаться и какие файлы необходимо измерить. Определены четыре набора параметров:

- Путь
- пасалл
- LiteralPath
- литералпасалл

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

Каждый набор параметров должен иметь уникальный параметр или уникальное сочетание параметров. `Path` `PathAll` Наборы параметров и очень похожи, но параметр **ALL** уникален для `PathAll` набора параметров. То же самое справедливо и к `LiteralPath` `LiteralPathAll` наборам параметров и. Несмотря на то, что `PathAll` `LiteralPathAll` оба набора параметров и имеют параметр **ALL** , параметры **path** и **LiteralPath** отличают их.

Используется для `Get-Command -Syntax` отображения синтаксиса каждого набора параметров. Однако он не отображает имя набора параметров. В следующем примере показано, какие параметры можно использовать в каждом наборе параметров.

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

### <a name="parameter-sets-in-action"></a>Наборы параметров в действии

В этом примере мы используем `PathAll` набор параметров.

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
