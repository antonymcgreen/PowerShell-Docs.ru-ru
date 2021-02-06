---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 231c2e3d2e28463be35ff1c9d5dab5a5d958f430
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604572"
---
# <span data-ttu-id="d60fb-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d60fb-102">Enable-PSTrace</span></span>

## <span data-ttu-id="d60fb-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d60fb-103">SYNOPSIS</span></span>
<span data-ttu-id="d60fb-104">Включает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d60fb-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="d60fb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d60fb-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="d60fb-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d60fb-106">DESCRIPTION</span></span>

<span data-ttu-id="d60fb-107">Этот командлет включает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d60fb-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="d60fb-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d60fb-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d60fb-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="d60fb-109">EXAMPLES</span></span>

### <span data-ttu-id="d60fb-110">Пример 1. Включение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="d60fb-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="d60fb-111">В следующем примере включается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d60fb-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="d60fb-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d60fb-112">PARAMETERS</span></span>

### <span data-ttu-id="d60fb-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="d60fb-113">-AnalyticOnly</span></span>

<span data-ttu-id="d60fb-114">При использовании этого параметра командлет включает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d60fb-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="d60fb-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="d60fb-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="d60fb-116">-Force</span><span class="sxs-lookup"><span data-stu-id="d60fb-116">-Force</span></span>

<span data-ttu-id="d60fb-117">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="d60fb-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="d60fb-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d60fb-118">CommonParameters</span></span>
<span data-ttu-id="d60fb-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d60fb-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d60fb-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d60fb-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d60fb-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d60fb-121">INPUTS</span></span>

### <span data-ttu-id="d60fb-122">None</span><span class="sxs-lookup"><span data-stu-id="d60fb-122">None</span></span>

## <span data-ttu-id="d60fb-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d60fb-123">OUTPUTS</span></span>

### <span data-ttu-id="d60fb-124">None</span><span class="sxs-lookup"><span data-stu-id="d60fb-124">None</span></span>

## <span data-ttu-id="d60fb-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d60fb-125">NOTES</span></span>

<span data-ttu-id="d60fb-126">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="d60fb-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="d60fb-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d60fb-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d60fb-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d60fb-128">RELATED LINKS</span></span>

[<span data-ttu-id="d60fb-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d60fb-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="d60fb-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d60fb-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="d60fb-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d60fb-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

