---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227437"
---
# <span data-ttu-id="ce62b-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ce62b-102">Enable-PSTrace</span></span>

## <span data-ttu-id="ce62b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ce62b-103">SYNOPSIS</span></span>
<span data-ttu-id="ce62b-104">Включает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce62b-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="ce62b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce62b-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="ce62b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce62b-106">DESCRIPTION</span></span>

<span data-ttu-id="ce62b-107">Этот командлет включает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce62b-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="ce62b-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ce62b-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ce62b-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="ce62b-109">EXAMPLES</span></span>

### <span data-ttu-id="ce62b-110">Пример 1. Включение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce62b-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="ce62b-111">В следующем примере включается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce62b-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="ce62b-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce62b-112">PARAMETERS</span></span>

### <span data-ttu-id="ce62b-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="ce62b-113">-AnalyticOnly</span></span>

<span data-ttu-id="ce62b-114">При использовании этого параметра командлет включает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce62b-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="ce62b-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="ce62b-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="ce62b-116">-Force</span><span class="sxs-lookup"><span data-stu-id="ce62b-116">-Force</span></span>

<span data-ttu-id="ce62b-117">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="ce62b-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="ce62b-118">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ce62b-118">INPUTS</span></span>

### <span data-ttu-id="ce62b-119">Нет</span><span class="sxs-lookup"><span data-stu-id="ce62b-119">None</span></span>

## <span data-ttu-id="ce62b-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ce62b-120">OUTPUTS</span></span>

### <span data-ttu-id="ce62b-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="ce62b-121">System.Object</span></span>

## <span data-ttu-id="ce62b-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ce62b-122">NOTES</span></span>

<span data-ttu-id="ce62b-123">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="ce62b-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="ce62b-124">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ce62b-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ce62b-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ce62b-125">RELATED LINKS</span></span>

[<span data-ttu-id="ce62b-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ce62b-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="ce62b-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ce62b-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="ce62b-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ce62b-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
