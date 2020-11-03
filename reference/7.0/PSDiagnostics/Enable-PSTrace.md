---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: fea84d9ae83eae88f9a665e8a49aaf2e6743127d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226345"
---
# <span data-ttu-id="d0314-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d0314-102">Enable-PSTrace</span></span>

## <span data-ttu-id="d0314-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d0314-103">SYNOPSIS</span></span>
<span data-ttu-id="d0314-104">Включает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0314-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="d0314-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0314-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="d0314-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0314-106">DESCRIPTION</span></span>

<span data-ttu-id="d0314-107">Этот командлет включает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0314-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="d0314-108">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d0314-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d0314-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="d0314-109">EXAMPLES</span></span>

### <span data-ttu-id="d0314-110">Пример 1. Включение журнала аналитических событий для PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0314-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="d0314-111">В следующем примере включается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0314-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="d0314-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0314-112">PARAMETERS</span></span>

### <span data-ttu-id="d0314-113">-Аналитиконли</span><span class="sxs-lookup"><span data-stu-id="d0314-113">-AnalyticOnly</span></span>

<span data-ttu-id="d0314-114">При использовании этого параметра командлет включает журнал аналитических событий поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0314-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="d0314-115">Журнал рабочих событий не изменяется.</span><span class="sxs-lookup"><span data-stu-id="d0314-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="d0314-116">-Force</span><span class="sxs-lookup"><span data-stu-id="d0314-116">-Force</span></span>

<span data-ttu-id="d0314-117">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="d0314-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="d0314-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d0314-118">CommonParameters</span></span>
<span data-ttu-id="d0314-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d0314-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0314-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d0314-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0314-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d0314-121">INPUTS</span></span>

### <span data-ttu-id="d0314-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d0314-122">None</span></span>

## <span data-ttu-id="d0314-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d0314-123">OUTPUTS</span></span>

### <span data-ttu-id="d0314-124">Нет</span><span class="sxs-lookup"><span data-stu-id="d0314-124">None</span></span>

## <span data-ttu-id="d0314-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d0314-125">NOTES</span></span>

<span data-ttu-id="d0314-126">Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="d0314-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="d0314-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d0314-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d0314-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d0314-128">RELATED LINKS</span></span>

[<span data-ttu-id="d0314-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d0314-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="d0314-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d0314-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="d0314-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d0314-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
