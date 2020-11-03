---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: c872b57186a854a67908bb07daac7f1a31bbb995
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209275"
---
# <span data-ttu-id="296a5-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="296a5-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="296a5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="296a5-104">SYNOPSIS</span></span>
<span data-ttu-id="296a5-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="296a5-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="296a5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="296a5-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="296a5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="296a5-107">DESCRIPTION</span></span>
<span data-ttu-id="296a5-108">Этот командлет запускает сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="296a5-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="296a5-109">Включены следующие поставщики событий:</span><span class="sxs-lookup"><span data-stu-id="296a5-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="296a5-110">Пересылка событий</span><span class="sxs-lookup"><span data-stu-id="296a5-110">Event Forwarding</span></span>
- <span data-ttu-id="296a5-111">ипмидрв</span><span class="sxs-lookup"><span data-stu-id="296a5-111">IpmiDrv</span></span>
- <span data-ttu-id="296a5-112">ипмипрв</span><span class="sxs-lookup"><span data-stu-id="296a5-112">IPMIPrv</span></span>
- <span data-ttu-id="296a5-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="296a5-113">WinRM</span></span>
- <span data-ttu-id="296a5-114">винрскмд</span><span class="sxs-lookup"><span data-stu-id="296a5-114">WinrsCmd</span></span>
- <span data-ttu-id="296a5-115">винрсексе</span><span class="sxs-lookup"><span data-stu-id="296a5-115">WinrsExe</span></span>
- <span data-ttu-id="296a5-116">винрсмгр</span><span class="sxs-lookup"><span data-stu-id="296a5-116">WinrsMgr</span></span>
- <span data-ttu-id="296a5-117">всманпровхост</span><span class="sxs-lookup"><span data-stu-id="296a5-117">WSManProvHost</span></span>

<span data-ttu-id="296a5-118">Сеанс называется "всмлог".</span><span class="sxs-lookup"><span data-stu-id="296a5-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="296a5-119">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="296a5-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="296a5-120">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="296a5-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="296a5-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="296a5-121">EXAMPLES</span></span>

### <span data-ttu-id="296a5-122">Пример 1. Запуск сеанса ведения журнала WSMan.</span><span class="sxs-lookup"><span data-stu-id="296a5-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="296a5-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="296a5-123">PARAMETERS</span></span>

### <span data-ttu-id="296a5-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="296a5-124">CommonParameters</span></span>

<span data-ttu-id="296a5-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="296a5-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="296a5-126">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="296a5-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="296a5-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="296a5-127">INPUTS</span></span>

### <span data-ttu-id="296a5-128">Нет</span><span class="sxs-lookup"><span data-stu-id="296a5-128">None</span></span>

## <span data-ttu-id="296a5-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="296a5-129">OUTPUTS</span></span>

### <span data-ttu-id="296a5-130">Нет</span><span class="sxs-lookup"><span data-stu-id="296a5-130">None</span></span>

## <span data-ttu-id="296a5-131">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="296a5-131">NOTES</span></span>

## <span data-ttu-id="296a5-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="296a5-132">RELATED LINKS</span></span>

[<span data-ttu-id="296a5-133">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="296a5-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="296a5-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="296a5-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="296a5-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="296a5-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
