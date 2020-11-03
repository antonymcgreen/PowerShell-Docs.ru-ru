---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 5e91477cd840e895c25207bd5355686e0c24d473
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209364"
---
# <span data-ttu-id="4c3a5-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4c3a5-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="4c3a5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4c3a5-104">SYNOPSIS</span></span>
<span data-ttu-id="4c3a5-105">Останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="4c3a5-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="4c3a5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c3a5-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="4c3a5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c3a5-107">DESCRIPTION</span></span>
<span data-ttu-id="4c3a5-108">Этот командлет останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="4c3a5-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="4c3a5-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="4c3a5-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="4c3a5-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="4c3a5-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4c3a5-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="4c3a5-111">EXAMPLES</span></span>

### <span data-ttu-id="4c3a5-112">Пример 1. Завершение трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="4c3a5-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="4c3a5-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c3a5-113">PARAMETERS</span></span>

### <span data-ttu-id="4c3a5-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4c3a5-114">CommonParameters</span></span>

<span data-ttu-id="4c3a5-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c3a5-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c3a5-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c3a5-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c3a5-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4c3a5-117">INPUTS</span></span>

### <span data-ttu-id="4c3a5-118">Нет</span><span class="sxs-lookup"><span data-stu-id="4c3a5-118">None</span></span>

## <span data-ttu-id="4c3a5-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4c3a5-119">OUTPUTS</span></span>

### <span data-ttu-id="4c3a5-120">Нет</span><span class="sxs-lookup"><span data-stu-id="4c3a5-120">None</span></span>

## <span data-ttu-id="4c3a5-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4c3a5-121">NOTES</span></span>

## <span data-ttu-id="4c3a5-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4c3a5-122">RELATED LINKS</span></span>

[<span data-ttu-id="4c3a5-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="4c3a5-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4c3a5-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4c3a5-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="4c3a5-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4c3a5-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
