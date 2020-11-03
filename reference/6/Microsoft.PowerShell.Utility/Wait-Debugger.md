---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: 7c850b94e2c64d8beb72a83fe8ae503594d20864
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209137"
---
# <span data-ttu-id="4b98e-103">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="4b98e-103">Wait-Debugger</span></span>

## <span data-ttu-id="4b98e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b98e-104">SYNOPSIS</span></span>
<span data-ttu-id="4b98e-105">Останавливает скрипт в отладчике перед выполнением следующего оператора в скрипте.</span><span class="sxs-lookup"><span data-stu-id="4b98e-105">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="4b98e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b98e-106">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="4b98e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b98e-107">DESCRIPTION</span></span>

<span data-ttu-id="4b98e-108">Останавливает подсистему выполнения скриптов PowerShell в точке сразу после `Wait-Debugger` командлета и ожидает присоединения отладчика.</span><span class="sxs-lookup"><span data-stu-id="4b98e-108">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="4b98e-109">Это похоже на использование `Enable-RunspaceDebug -BreakAll` в ресурсе DSC, но прерывает выполнение в определенной точке скрипта.</span><span class="sxs-lookup"><span data-stu-id="4b98e-109">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="4b98e-110">Убедитесь, что вы удалили `Wait-Debugger` строки после завершения.</span><span class="sxs-lookup"><span data-stu-id="4b98e-110">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="4b98e-111">Работающий сценарий перестает быть зависла, когда он останавливается в `Wait-Debugger` .</span><span class="sxs-lookup"><span data-stu-id="4b98e-111">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="4b98e-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b98e-112">EXAMPLES</span></span>

### <span data-ttu-id="4b98e-113">Пример 1. Вставка точки останова для отладки</span><span class="sxs-lookup"><span data-stu-id="4b98e-113">Example 1: Insert breakpoint for debugging</span></span>

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

## <span data-ttu-id="4b98e-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b98e-114">PARAMETERS</span></span>

### <span data-ttu-id="4b98e-115">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b98e-115">CommonParameters</span></span>

<span data-ttu-id="4b98e-116">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b98e-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b98e-117">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4b98e-117">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4b98e-118">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b98e-118">INPUTS</span></span>

### <span data-ttu-id="4b98e-119">Нет</span><span class="sxs-lookup"><span data-stu-id="4b98e-119">None</span></span>

## <span data-ttu-id="4b98e-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b98e-120">OUTPUTS</span></span>

### <span data-ttu-id="4b98e-121">Нет</span><span class="sxs-lookup"><span data-stu-id="4b98e-121">None</span></span>

## <span data-ttu-id="4b98e-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b98e-122">NOTES</span></span>

## <span data-ttu-id="4b98e-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b98e-123">RELATED LINKS</span></span>

[<span data-ttu-id="4b98e-124">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="4b98e-124">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
