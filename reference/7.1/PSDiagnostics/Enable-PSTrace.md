---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: cc94d85e48849d47531ac0a83527f3c68c21377e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229330"
---
# <span data-ttu-id="01979-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="01979-102">Enable-PSTrace</span></span>

## <span data-ttu-id="01979-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="01979-103">SYNOPSIS</span></span>
<span data-ttu-id="01979-104">Включает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01979-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="01979-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01979-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="01979-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01979-106">DESCRIPTION</span></span>

<span data-ttu-id="01979-107">Этот командлет включает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01979-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="01979-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="01979-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="01979-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="01979-109">EXAMPLES</span></span>

### <span data-ttu-id="01979-110">Пример 1. Включение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="01979-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="01979-111">В следующем примере включается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01979-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="01979-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01979-112">PARAMETERS</span></span>

### <span data-ttu-id="01979-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="01979-113">-AnalyticOnly</span></span>

<span data-ttu-id="01979-114">При использовании этого параметра командлет включает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01979-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="01979-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="01979-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="01979-116">-Force</span><span class="sxs-lookup"><span data-stu-id="01979-116">-Force</span></span>

<span data-ttu-id="01979-117">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="01979-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="01979-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="01979-118">CommonParameters</span></span>
<span data-ttu-id="01979-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01979-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01979-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01979-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01979-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="01979-121">INPUTS</span></span>

### <span data-ttu-id="01979-122">Нет</span><span class="sxs-lookup"><span data-stu-id="01979-122">None</span></span>

## <span data-ttu-id="01979-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="01979-123">OUTPUTS</span></span>

### <span data-ttu-id="01979-124">Нет</span><span class="sxs-lookup"><span data-stu-id="01979-124">None</span></span>

## <span data-ttu-id="01979-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="01979-125">NOTES</span></span>

<span data-ttu-id="01979-126">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="01979-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="01979-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="01979-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="01979-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="01979-128">RELATED LINKS</span></span>

[<span data-ttu-id="01979-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="01979-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="01979-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="01979-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="01979-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="01979-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

