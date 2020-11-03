---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: dc817a2f8629744ce4bdcf428530713e76c3d044
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209081"
---
# <span data-ttu-id="14b70-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="14b70-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="14b70-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="14b70-104">SYNOPSIS</span></span>
<span data-ttu-id="14b70-105">Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.</span><span class="sxs-lookup"><span data-stu-id="14b70-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="14b70-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14b70-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="14b70-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14b70-107">DESCRIPTION</span></span>

<span data-ttu-id="14b70-108">Этот командлет останавливает сеанс ведения журнала, запущенный `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="14b70-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="14b70-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="14b70-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="14b70-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="14b70-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="14b70-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="14b70-111">EXAMPLES</span></span>

### <span data-ttu-id="14b70-112">Пример 1. Отключение Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="14b70-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="14b70-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14b70-113">PARAMETERS</span></span>

### <span data-ttu-id="14b70-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="14b70-114">CommonParameters</span></span>

<span data-ttu-id="14b70-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14b70-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14b70-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="14b70-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14b70-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="14b70-117">INPUTS</span></span>

### <span data-ttu-id="14b70-118">Нет</span><span class="sxs-lookup"><span data-stu-id="14b70-118">None</span></span>

## <span data-ttu-id="14b70-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="14b70-119">OUTPUTS</span></span>

### <span data-ttu-id="14b70-120">Нет</span><span class="sxs-lookup"><span data-stu-id="14b70-120">None</span></span>

## <span data-ttu-id="14b70-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="14b70-121">NOTES</span></span>

## <span data-ttu-id="14b70-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="14b70-122">RELATED LINKS</span></span>

[<span data-ttu-id="14b70-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="14b70-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="14b70-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="14b70-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="14b70-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="14b70-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
