---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: f7ec371e0d9826dc095fbf71c4785cae2856875b
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209073"
---
# <span data-ttu-id="ab7f1-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ab7f1-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="ab7f1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ab7f1-104">SYNOPSIS</span></span>
<span data-ttu-id="ab7f1-105">Останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="ab7f1-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="ab7f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab7f1-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="ab7f1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab7f1-107">DESCRIPTION</span></span>
<span data-ttu-id="ab7f1-108">Этот командлет останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="ab7f1-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="ab7f1-109">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="ab7f1-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="ab7f1-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ab7f1-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ab7f1-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="ab7f1-111">EXAMPLES</span></span>

### <span data-ttu-id="ab7f1-112">Пример 1. Завершение трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="ab7f1-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="ab7f1-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab7f1-113">PARAMETERS</span></span>

### <span data-ttu-id="ab7f1-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ab7f1-114">CommonParameters</span></span>

<span data-ttu-id="ab7f1-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab7f1-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab7f1-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ab7f1-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab7f1-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ab7f1-117">INPUTS</span></span>

### <span data-ttu-id="ab7f1-118">Нет</span><span class="sxs-lookup"><span data-stu-id="ab7f1-118">None</span></span>

## <span data-ttu-id="ab7f1-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ab7f1-119">OUTPUTS</span></span>

### <span data-ttu-id="ab7f1-120">Нет</span><span class="sxs-lookup"><span data-stu-id="ab7f1-120">None</span></span>

## <span data-ttu-id="ab7f1-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ab7f1-121">NOTES</span></span>

## <span data-ttu-id="ab7f1-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ab7f1-122">RELATED LINKS</span></span>

[<span data-ttu-id="ab7f1-123">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="ab7f1-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="ab7f1-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="ab7f1-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="ab7f1-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ab7f1-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
