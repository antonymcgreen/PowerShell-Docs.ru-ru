---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: a2ef114a43a63b18f5dc2d28acf7cbc0de8392bd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599802"
---
# <span data-ttu-id="67cc0-102">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="67cc0-102">Wait-Debugger</span></span>

## <span data-ttu-id="67cc0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="67cc0-103">SYNOPSIS</span></span>
<span data-ttu-id="67cc0-104">Останавливает скрипт в отладчике перед выполнением следующего оператора в скрипте.</span><span class="sxs-lookup"><span data-stu-id="67cc0-104">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="67cc0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67cc0-105">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="67cc0-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67cc0-106">DESCRIPTION</span></span>

<span data-ttu-id="67cc0-107">Останавливает подсистему выполнения скриптов PowerShell в точке сразу после `Wait-Debugger` командлета и ожидает присоединения отладчика.</span><span class="sxs-lookup"><span data-stu-id="67cc0-107">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="67cc0-108">Это похоже на использование `Enable-RunspaceDebug -BreakAll` в ресурсе DSC, но прерывает выполнение в определенной точке скрипта.</span><span class="sxs-lookup"><span data-stu-id="67cc0-108">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="67cc0-109">Убедитесь, что вы удалили `Wait-Debugger` строки после завершения.</span><span class="sxs-lookup"><span data-stu-id="67cc0-109">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="67cc0-110">Работающий сценарий перестает быть зависла, когда он останавливается в `Wait-Debugger` .</span><span class="sxs-lookup"><span data-stu-id="67cc0-110">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="67cc0-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="67cc0-111">EXAMPLES</span></span>

### <span data-ttu-id="67cc0-112">Пример 1. Вставка точки останова для отладки</span><span class="sxs-lookup"><span data-stu-id="67cc0-112">Example 1: Insert breakpoint for debugging</span></span>

```
[DscResource()]
class FileResource
{
    [DscProperty(Key)]
    [string] $Path

    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    [DscProperty(Mandatory)]
    [string] $SourcePath

    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime


    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (! $fileExists)
            {
               $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    [bool] Test()
    {
        $present = Test-Path -LiteralPath $this.Path

        if ($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
        {
            return (! $present)
        }
    }

    [FileResource] Get()
    {
        $present = Test-Path -Path $this.Path

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }

        return $this
    }

    [void] CopyFile()
    {
        # Testing only - Remove before deployment!
        Wait-Debugger

        if (! (Test-Path -LiteralPath $this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose "Copying $($this.SourcePath) to $($this.Path)"

        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <span data-ttu-id="67cc0-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67cc0-113">PARAMETERS</span></span>

### <span data-ttu-id="67cc0-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="67cc0-114">CommonParameters</span></span>

<span data-ttu-id="67cc0-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="67cc0-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="67cc0-116">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="67cc0-116">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="67cc0-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="67cc0-117">INPUTS</span></span>

### <span data-ttu-id="67cc0-118">None</span><span class="sxs-lookup"><span data-stu-id="67cc0-118">None</span></span>

## <span data-ttu-id="67cc0-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="67cc0-119">OUTPUTS</span></span>

### <span data-ttu-id="67cc0-120">None</span><span class="sxs-lookup"><span data-stu-id="67cc0-120">None</span></span>

## <span data-ttu-id="67cc0-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="67cc0-121">NOTES</span></span>

## <span data-ttu-id="67cc0-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="67cc0-122">RELATED LINKS</span></span>

[<span data-ttu-id="67cc0-123">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="67cc0-123">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)

