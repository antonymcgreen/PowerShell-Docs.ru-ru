---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 647a7676eddf2175bf29e02b3482cc9c7c4d8ebe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604563"
---
# <span data-ttu-id="cbeea-102">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="cbeea-102">Disable-WSManTrace</span></span>

## <span data-ttu-id="cbeea-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbeea-103">SYNOPSIS</span></span>
<span data-ttu-id="cbeea-104">Останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="cbeea-104">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="cbeea-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cbeea-105">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="cbeea-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cbeea-106">DESCRIPTION</span></span>
<span data-ttu-id="cbeea-107">Этот командлет останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="cbeea-107">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="cbeea-108">Этот командлет использует `Stop-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="cbeea-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="cbeea-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="cbeea-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="cbeea-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="cbeea-110">EXAMPLES</span></span>

### <span data-ttu-id="cbeea-111">Пример 1. Завершение трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="cbeea-111">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="cbeea-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cbeea-112">PARAMETERS</span></span>

### <span data-ttu-id="cbeea-113">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cbeea-113">CommonParameters</span></span>

<span data-ttu-id="cbeea-114">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cbeea-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cbeea-115">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cbeea-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cbeea-116">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cbeea-116">INPUTS</span></span>

### <span data-ttu-id="cbeea-117">None</span><span class="sxs-lookup"><span data-stu-id="cbeea-117">None</span></span>

## <span data-ttu-id="cbeea-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cbeea-118">OUTPUTS</span></span>

### <span data-ttu-id="cbeea-119">None</span><span class="sxs-lookup"><span data-stu-id="cbeea-119">None</span></span>

## <span data-ttu-id="cbeea-120">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cbeea-120">NOTES</span></span>

## <span data-ttu-id="cbeea-121">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cbeea-121">RELATED LINKS</span></span>

[<span data-ttu-id="cbeea-122">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="cbeea-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="cbeea-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="cbeea-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="cbeea-124">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="cbeea-124">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

