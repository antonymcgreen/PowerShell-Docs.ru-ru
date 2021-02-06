---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 690a8b050fd0e16033a585df210db340f41a83a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600668"
---
# <span data-ttu-id="22997-102">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="22997-102">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="22997-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="22997-103">SYNOPSIS</span></span>
<span data-ttu-id="22997-104">Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.</span><span class="sxs-lookup"><span data-stu-id="22997-104">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="22997-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22997-105">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="22997-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="22997-106">DESCRIPTION</span></span>

<span data-ttu-id="22997-107">Этот командлет останавливает сеанс ведения журнала, запущенный `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="22997-107">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="22997-108">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="22997-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="22997-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="22997-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="22997-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="22997-110">EXAMPLES</span></span>

### <span data-ttu-id="22997-111">Пример 1. Отключение Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="22997-111">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="22997-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22997-112">PARAMETERS</span></span>

### <span data-ttu-id="22997-113">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="22997-113">CommonParameters</span></span>

<span data-ttu-id="22997-114">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22997-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22997-115">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="22997-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22997-116">Входные данные</span><span class="sxs-lookup"><span data-stu-id="22997-116">INPUTS</span></span>

### <span data-ttu-id="22997-117">None</span><span class="sxs-lookup"><span data-stu-id="22997-117">None</span></span>

## <span data-ttu-id="22997-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="22997-118">OUTPUTS</span></span>

### <span data-ttu-id="22997-119">None</span><span class="sxs-lookup"><span data-stu-id="22997-119">None</span></span>

## <span data-ttu-id="22997-120">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="22997-120">NOTES</span></span>

## <span data-ttu-id="22997-121">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="22997-121">RELATED LINKS</span></span>

[<span data-ttu-id="22997-122">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="22997-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="22997-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="22997-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="22997-124">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="22997-124">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

