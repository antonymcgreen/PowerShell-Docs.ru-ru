---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a98941de072b9b57b89a25bc180c0ee391d8b63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227445"
---
# <span data-ttu-id="94c1e-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="94c1e-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="94c1e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="94c1e-104">SYNOPSIS</span></span>
<span data-ttu-id="94c1e-105">Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.</span><span class="sxs-lookup"><span data-stu-id="94c1e-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="94c1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94c1e-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="94c1e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94c1e-107">DESCRIPTION</span></span>

<span data-ttu-id="94c1e-108">Этот командлет останавливает сеанс ведения журнала, запущенный `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="94c1e-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="94c1e-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="94c1e-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="94c1e-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="94c1e-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="94c1e-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="94c1e-111">EXAMPLES</span></span>

### <span data-ttu-id="94c1e-112">Пример 1. Отключение Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="94c1e-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="94c1e-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94c1e-113">PARAMETERS</span></span>

### <span data-ttu-id="94c1e-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="94c1e-114">CommonParameters</span></span>

<span data-ttu-id="94c1e-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="94c1e-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94c1e-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="94c1e-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94c1e-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="94c1e-117">INPUTS</span></span>

### <span data-ttu-id="94c1e-118">Нет</span><span class="sxs-lookup"><span data-stu-id="94c1e-118">None</span></span>

## <span data-ttu-id="94c1e-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="94c1e-119">OUTPUTS</span></span>

### <span data-ttu-id="94c1e-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="94c1e-120">System.Object</span></span>

## <span data-ttu-id="94c1e-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="94c1e-121">NOTES</span></span>

## <span data-ttu-id="94c1e-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="94c1e-122">RELATED LINKS</span></span>

[<span data-ttu-id="94c1e-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="94c1e-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="94c1e-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="94c1e-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="94c1e-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="94c1e-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
