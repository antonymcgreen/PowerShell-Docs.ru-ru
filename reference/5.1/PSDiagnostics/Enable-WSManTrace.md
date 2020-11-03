---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 08c9d61f210761e2ed7a3a5014812b2bd362201b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227433"
---
# <span data-ttu-id="a4397-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a4397-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="a4397-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a4397-104">SYNOPSIS</span></span>
<span data-ttu-id="a4397-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="a4397-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="a4397-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4397-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="a4397-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4397-107">DESCRIPTION</span></span>
<span data-ttu-id="a4397-108">Этот командлет запускает сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="a4397-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="a4397-109">Включены следующие поставщики событий:</span><span class="sxs-lookup"><span data-stu-id="a4397-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="a4397-110">Пересылка событий</span><span class="sxs-lookup"><span data-stu-id="a4397-110">Event Forwarding</span></span>
- <span data-ttu-id="a4397-111">ипмидрв</span><span class="sxs-lookup"><span data-stu-id="a4397-111">IpmiDrv</span></span>
- <span data-ttu-id="a4397-112">ипмипрв</span><span class="sxs-lookup"><span data-stu-id="a4397-112">IPMIPrv</span></span>
- <span data-ttu-id="a4397-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="a4397-113">WinRM</span></span>
- <span data-ttu-id="a4397-114">винрскмд</span><span class="sxs-lookup"><span data-stu-id="a4397-114">WinrsCmd</span></span>
- <span data-ttu-id="a4397-115">винрсексе</span><span class="sxs-lookup"><span data-stu-id="a4397-115">WinrsExe</span></span>
- <span data-ttu-id="a4397-116">винрсмгр</span><span class="sxs-lookup"><span data-stu-id="a4397-116">WinrsMgr</span></span>
- <span data-ttu-id="a4397-117">всманпровхост</span><span class="sxs-lookup"><span data-stu-id="a4397-117">WSManProvHost</span></span>

<span data-ttu-id="a4397-118">Сеанс называется "всмлог".</span><span class="sxs-lookup"><span data-stu-id="a4397-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="a4397-119">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="a4397-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="a4397-120">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a4397-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a4397-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="a4397-121">EXAMPLES</span></span>

### <span data-ttu-id="a4397-122">Пример 1. Запуск сеанса ведения журнала WSMan.</span><span class="sxs-lookup"><span data-stu-id="a4397-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="a4397-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4397-123">PARAMETERS</span></span>

### <span data-ttu-id="a4397-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a4397-124">CommonParameters</span></span>

<span data-ttu-id="a4397-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a4397-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4397-126">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a4397-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4397-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a4397-127">INPUTS</span></span>

### <span data-ttu-id="a4397-128">Нет</span><span class="sxs-lookup"><span data-stu-id="a4397-128">None</span></span>

## <span data-ttu-id="a4397-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a4397-129">OUTPUTS</span></span>

### <span data-ttu-id="a4397-130">System.Object</span><span class="sxs-lookup"><span data-stu-id="a4397-130">System.Object</span></span>

## <span data-ttu-id="a4397-131">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a4397-131">NOTES</span></span>

## <span data-ttu-id="a4397-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a4397-132">RELATED LINKS</span></span>

[<span data-ttu-id="a4397-133">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="a4397-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a4397-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="a4397-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="a4397-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a4397-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
