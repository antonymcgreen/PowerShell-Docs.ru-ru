---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 3f99869825b2255d3f5487c48b6eaa90a4ae901f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226897"
---
# <span data-ttu-id="18d98-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="18d98-102">Disable-PSTrace</span></span>

## <span data-ttu-id="18d98-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="18d98-103">SYNOPSIS</span></span>
<span data-ttu-id="18d98-104">Отключает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d98-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="18d98-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18d98-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="18d98-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18d98-106">DESCRIPTION</span></span>

<span data-ttu-id="18d98-107">Этот командлет отключает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d98-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="18d98-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="18d98-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="18d98-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="18d98-109">EXAMPLES</span></span>

### <span data-ttu-id="18d98-110">Пример 1. Отключение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="18d98-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="18d98-111">В следующем примере отключается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d98-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="18d98-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18d98-112">PARAMETERS</span></span>

### <span data-ttu-id="18d98-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="18d98-113">-AnalyticOnly</span></span>

<span data-ttu-id="18d98-114">При использовании этого параметра командлет отключает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d98-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="18d98-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="18d98-115">The Operational event log is not changed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d98-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="18d98-116">CommonParameters</span></span>
<span data-ttu-id="18d98-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="18d98-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18d98-118">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="18d98-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18d98-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="18d98-119">INPUTS</span></span>

### <span data-ttu-id="18d98-120">Нет</span><span class="sxs-lookup"><span data-stu-id="18d98-120">None</span></span>

## <span data-ttu-id="18d98-121">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="18d98-121">OUTPUTS</span></span>

### <span data-ttu-id="18d98-122">Нет</span><span class="sxs-lookup"><span data-stu-id="18d98-122">None</span></span>

## <span data-ttu-id="18d98-123">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="18d98-123">NOTES</span></span>

<span data-ttu-id="18d98-124">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="18d98-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="18d98-125">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="18d98-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="18d98-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="18d98-126">RELATED LINKS</span></span>

[<span data-ttu-id="18d98-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="18d98-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="18d98-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="18d98-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="18d98-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="18d98-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)
