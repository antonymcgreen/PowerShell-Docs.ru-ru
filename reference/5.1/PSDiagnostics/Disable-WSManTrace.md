---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 90cb571f93243e6fbc59970e5602911e17e25ec7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227438"
---
# <span data-ttu-id="a3cc5-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a3cc5-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="a3cc5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a3cc5-104">SYNOPSIS</span></span>
<span data-ttu-id="a3cc5-105">Останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="a3cc5-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="a3cc5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3cc5-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="a3cc5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3cc5-107">DESCRIPTION</span></span>
<span data-ttu-id="a3cc5-108">Этот командлет останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="a3cc5-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="a3cc5-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="a3cc5-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="a3cc5-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a3cc5-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a3cc5-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="a3cc5-111">EXAMPLES</span></span>

### <span data-ttu-id="a3cc5-112">Пример 1. Завершение трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="a3cc5-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="a3cc5-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3cc5-113">PARAMETERS</span></span>

### <span data-ttu-id="a3cc5-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a3cc5-114">CommonParameters</span></span>

<span data-ttu-id="a3cc5-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3cc5-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3cc5-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3cc5-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3cc5-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a3cc5-117">INPUTS</span></span>

### <span data-ttu-id="a3cc5-118">Нет</span><span class="sxs-lookup"><span data-stu-id="a3cc5-118">None</span></span>

## <span data-ttu-id="a3cc5-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a3cc5-119">OUTPUTS</span></span>

### <span data-ttu-id="a3cc5-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="a3cc5-120">System.Object</span></span>

## <span data-ttu-id="a3cc5-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a3cc5-121">NOTES</span></span>

## <span data-ttu-id="a3cc5-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a3cc5-122">RELATED LINKS</span></span>

[<span data-ttu-id="a3cc5-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="a3cc5-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a3cc5-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="a3cc5-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="a3cc5-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a3cc5-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
