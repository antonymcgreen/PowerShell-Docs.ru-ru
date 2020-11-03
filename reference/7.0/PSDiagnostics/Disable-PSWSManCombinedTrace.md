---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a00b843e5e4ec73cf98f4c924ca24a3e1ee0700
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209365"
---
# <span data-ttu-id="3e903-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="3e903-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="3e903-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3e903-104">SYNOPSIS</span></span>
<span data-ttu-id="3e903-105">Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.</span><span class="sxs-lookup"><span data-stu-id="3e903-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="3e903-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3e903-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="3e903-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e903-107">DESCRIPTION</span></span>

<span data-ttu-id="3e903-108">Этот командлет останавливает сеанс ведения журнала, запущенный `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="3e903-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="3e903-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="3e903-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="3e903-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="3e903-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="3e903-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3e903-111">EXAMPLES</span></span>

### <span data-ttu-id="3e903-112">Пример 1. Отключение Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="3e903-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="3e903-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3e903-113">PARAMETERS</span></span>

### <span data-ttu-id="3e903-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3e903-114">CommonParameters</span></span>

<span data-ttu-id="3e903-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3e903-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3e903-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3e903-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e903-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3e903-117">INPUTS</span></span>

### <span data-ttu-id="3e903-118">Нет</span><span class="sxs-lookup"><span data-stu-id="3e903-118">None</span></span>

## <span data-ttu-id="3e903-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3e903-119">OUTPUTS</span></span>

### <span data-ttu-id="3e903-120">Нет</span><span class="sxs-lookup"><span data-stu-id="3e903-120">None</span></span>

## <span data-ttu-id="3e903-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3e903-121">NOTES</span></span>

## <span data-ttu-id="3e903-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3e903-122">RELATED LINKS</span></span>

[<span data-ttu-id="3e903-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="3e903-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="3e903-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="3e903-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="3e903-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="3e903-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
