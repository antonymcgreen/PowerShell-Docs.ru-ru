---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227446"
---
# <span data-ttu-id="750b9-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="750b9-102">Disable-PSTrace</span></span>

## <span data-ttu-id="750b9-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="750b9-103">SYNOPSIS</span></span>
<span data-ttu-id="750b9-104">Отключает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="750b9-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="750b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="750b9-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="750b9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="750b9-106">DESCRIPTION</span></span>

<span data-ttu-id="750b9-107">Этот командлет отключает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="750b9-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="750b9-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="750b9-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="750b9-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="750b9-109">EXAMPLES</span></span>

### <span data-ttu-id="750b9-110">Пример 1. Отключение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="750b9-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="750b9-111">В следующем примере отключается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="750b9-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="750b9-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="750b9-112">PARAMETERS</span></span>

### <span data-ttu-id="750b9-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="750b9-113">-AnalyticOnly</span></span>

<span data-ttu-id="750b9-114">При использовании этого параметра командлет отключает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="750b9-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="750b9-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="750b9-115">The Operational event log is not changed.</span></span>

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

## <span data-ttu-id="750b9-116">Входные данные</span><span class="sxs-lookup"><span data-stu-id="750b9-116">INPUTS</span></span>

### <span data-ttu-id="750b9-117">Нет</span><span class="sxs-lookup"><span data-stu-id="750b9-117">None</span></span>

## <span data-ttu-id="750b9-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="750b9-118">OUTPUTS</span></span>

### <span data-ttu-id="750b9-119">System.Object</span><span class="sxs-lookup"><span data-stu-id="750b9-119">System.Object</span></span>

## <span data-ttu-id="750b9-120">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="750b9-120">NOTES</span></span>

<span data-ttu-id="750b9-121">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="750b9-121">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="750b9-122">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="750b9-122">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="750b9-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="750b9-123">RELATED LINKS</span></span>

[<span data-ttu-id="750b9-124">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="750b9-124">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="750b9-125">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="750b9-125">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="750b9-126">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="750b9-126">Enable-PSTrace</span></span>](Enable-PSTrace.md)
