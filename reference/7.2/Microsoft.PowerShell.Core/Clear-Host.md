---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host;
ms.openlocfilehash: de7dc6027653db063311bd34e1282e3cb5294e92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601606"
---
# <span data-ttu-id="d2db6-102">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="d2db6-102">Clear-Host</span></span>

## <span data-ttu-id="d2db6-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d2db6-103">SYNOPSIS</span></span>

<span data-ttu-id="d2db6-104">Удаляет отображаемые данные в основной программе.</span><span class="sxs-lookup"><span data-stu-id="d2db6-104">Clears the display in the host program.</span></span>

## <span data-ttu-id="d2db6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2db6-105">SYNTAX</span></span>

```
Clear-Host [<CommonParameters>]
```

## <span data-ttu-id="d2db6-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d2db6-106">DESCRIPTION</span></span>

<span data-ttu-id="d2db6-107">`Clear-Host`Функция удаляет весь текст из текущего экрана, включая команды и выходные данные, которые могли накапливаться.</span><span class="sxs-lookup"><span data-stu-id="d2db6-107">The `Clear-Host` function removes all text from the current display, including commands and output that might have accumulated.</span></span> <span data-ttu-id="d2db6-108">При выполнении этой команды отобразится командная строка.</span><span class="sxs-lookup"><span data-stu-id="d2db6-108">When complete, it displays the command prompt.</span></span> <span data-ttu-id="d2db6-109">Можно использовать имя функции или ее псевдоним, `cls` .</span><span class="sxs-lookup"><span data-stu-id="d2db6-109">You can use the function name or its alias, `cls`.</span></span>

<span data-ttu-id="d2db6-110">`Clear-Host` влияет только на текущее отображение.</span><span class="sxs-lookup"><span data-stu-id="d2db6-110">`Clear-Host` affects only the current display.</span></span> <span data-ttu-id="d2db6-111">Эта команда не удаляет сохраненные результаты или какие-либо элементы сеанса.</span><span class="sxs-lookup"><span data-stu-id="d2db6-111">It does not delete saved results or remove any items from the session.</span></span> <span data-ttu-id="d2db6-112">Эта функция не затрагивает специфические для сеанса элементы, такие как переменные или функции.</span><span class="sxs-lookup"><span data-stu-id="d2db6-112">Session-specific items, such as variables and functions, are not affected by this function.</span></span>

<span data-ttu-id="d2db6-113">Поскольку поведение `Clear-Host` функции определяется ведущим приложением, `Clear-Host` может работать по-разному в различных ведущих программах.</span><span class="sxs-lookup"><span data-stu-id="d2db6-113">Because the behavior of the `Clear-Host` function is determined by the host program, `Clear-Host` might work differently in different host programs.</span></span>

## <span data-ttu-id="d2db6-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2db6-114">EXAMPLES</span></span>

### <span data-ttu-id="d2db6-115">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d2db6-115">Example 1</span></span>

```
# Before

PS C:\> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    843      33    14428      22556    99    17.41   1688 CcmExec
     44       6     2196       4964    52     0.23    692 conhost
    646      12     2332       4896    49     1.12    388 csrss
    189      11     2860       7084   114     0.66   2896 csrss
     78      11     1876       4008    42     0.22   4000 csrss
     76       7     1848       5064    54     0.08   1028 dwm
    610      41    23952      44048   208     4.40   2080 explorer
      0       0        0         24     0               0 Idle
    182      32     7692      15980    91     0.23   3056 LogonUI
    186      25     7832      16068    91     0.27   3996 LogonUI
   1272      32    11512      20432    58    25.07    548 lsass
    267      10     3536       6736    34     0.80    556 lsm
    137      17     3520       7472    61     0.05   1220 msdtc
    447      31    70316      84476   201 1,429.67    836 MsMpEng
    265      18     7136      15628   134     2.20   3544 msseces
    248      16     6476       4076    76     0.22   1592 NisSrv
    368      25    61312      65508   614     1.78    848 powershell
    101       8     2304       6624    70     0.64   3648 rdpclip
    258      15     6804      12156    50     2.65    536 services
...

PS C:\> cls
#After

PS C:>
```

<span data-ttu-id="d2db6-116">Эта команда использует `cls` псевдоним `Clear-Host` для очистки текущего экрана.</span><span class="sxs-lookup"><span data-stu-id="d2db6-116">This command uses the `cls` alias of `Clear-Host` to clear the current display.</span></span>

## <span data-ttu-id="d2db6-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2db6-117">PARAMETERS</span></span>

### <span data-ttu-id="d2db6-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d2db6-118">CommonParameters</span></span>
<span data-ttu-id="d2db6-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d2db6-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d2db6-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d2db6-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d2db6-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d2db6-121">INPUTS</span></span>

### <span data-ttu-id="d2db6-122">None</span><span class="sxs-lookup"><span data-stu-id="d2db6-122">None</span></span>

<span data-ttu-id="d2db6-123">Вы не можете передать входные данные в `Clear-Host` .</span><span class="sxs-lookup"><span data-stu-id="d2db6-123">You cannot pipe input to `Clear-Host`.</span></span>

## <span data-ttu-id="d2db6-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d2db6-124">OUTPUTS</span></span>

### <span data-ttu-id="d2db6-125">None</span><span class="sxs-lookup"><span data-stu-id="d2db6-125">None</span></span>

<span data-ttu-id="d2db6-126">`Clear-Host` не создает никаких выходных данных</span><span class="sxs-lookup"><span data-stu-id="d2db6-126">`Clear-Host` does not generate any output</span></span>

## <span data-ttu-id="d2db6-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d2db6-127">NOTES</span></span>

<span data-ttu-id="d2db6-128">`Clear-Host` — Это простая функция, а не расширенная функция.</span><span class="sxs-lookup"><span data-stu-id="d2db6-128">`Clear-Host` is a simple function, not an advanced function.</span></span> <span data-ttu-id="d2db6-129">Таким образом, в команде нельзя использовать общие параметры, такие как **Debug** `Clear-Host` .</span><span class="sxs-lookup"><span data-stu-id="d2db6-129">As such, you cannot use common parameters, such as **Debug**, in a `Clear-Host` command.</span></span>

## <span data-ttu-id="d2db6-130">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d2db6-130">RELATED LINKS</span></span>

[<span data-ttu-id="d2db6-131">Get-Host</span><span class="sxs-lookup"><span data-stu-id="d2db6-131">Get-Host</span></span>](../Microsoft.PowerShell.Utility/Get-Host.md)

[<span data-ttu-id="d2db6-132">Out-Host</span><span class="sxs-lookup"><span data-stu-id="d2db6-132">Out-Host</span></span>](Out-Host.md)

[<span data-ttu-id="d2db6-133">Read-Host</span><span class="sxs-lookup"><span data-stu-id="d2db6-133">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

[<span data-ttu-id="d2db6-134">Write-Host</span><span class="sxs-lookup"><span data-stu-id="d2db6-134">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)

