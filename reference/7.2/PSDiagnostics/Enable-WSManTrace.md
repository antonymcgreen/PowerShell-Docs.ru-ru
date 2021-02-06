---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: a9d91eab94666186c13f8d5c928d83055f6dbefa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601495"
---
# <span data-ttu-id="a401a-102">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a401a-102">Enable-WSManTrace</span></span>

## <span data-ttu-id="a401a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a401a-103">SYNOPSIS</span></span>
<span data-ttu-id="a401a-104">Запустите сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="a401a-104">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="a401a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a401a-105">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="a401a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a401a-106">DESCRIPTION</span></span>
<span data-ttu-id="a401a-107">Этот командлет запускает сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="a401a-107">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="a401a-108">Включены следующие поставщики событий:</span><span class="sxs-lookup"><span data-stu-id="a401a-108">The following event providers are enabled:</span></span>

- <span data-ttu-id="a401a-109">Пересылка событий</span><span class="sxs-lookup"><span data-stu-id="a401a-109">Event Forwarding</span></span>
- <span data-ttu-id="a401a-110">ипмидрв</span><span class="sxs-lookup"><span data-stu-id="a401a-110">IpmiDrv</span></span>
- <span data-ttu-id="a401a-111">ипмипрв</span><span class="sxs-lookup"><span data-stu-id="a401a-111">IPMIPrv</span></span>
- <span data-ttu-id="a401a-112">WinRM</span><span class="sxs-lookup"><span data-stu-id="a401a-112">WinRM</span></span>
- <span data-ttu-id="a401a-113">винрскмд</span><span class="sxs-lookup"><span data-stu-id="a401a-113">WinrsCmd</span></span>
- <span data-ttu-id="a401a-114">винрсексе</span><span class="sxs-lookup"><span data-stu-id="a401a-114">WinrsExe</span></span>
- <span data-ttu-id="a401a-115">винрсмгр</span><span class="sxs-lookup"><span data-stu-id="a401a-115">WinrsMgr</span></span>
- <span data-ttu-id="a401a-116">всманпровхост</span><span class="sxs-lookup"><span data-stu-id="a401a-116">WSManProvHost</span></span>

<span data-ttu-id="a401a-117">Сеанс называется "всмлог".</span><span class="sxs-lookup"><span data-stu-id="a401a-117">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="a401a-118">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="a401a-118">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="a401a-119">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a401a-119">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a401a-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="a401a-120">EXAMPLES</span></span>

### <span data-ttu-id="a401a-121">Пример 1. Запуск сеанса ведения журнала WSMan.</span><span class="sxs-lookup"><span data-stu-id="a401a-121">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="a401a-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a401a-122">PARAMETERS</span></span>

### <span data-ttu-id="a401a-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a401a-123">CommonParameters</span></span>

<span data-ttu-id="a401a-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a401a-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a401a-125">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a401a-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a401a-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a401a-126">INPUTS</span></span>

### <span data-ttu-id="a401a-127">None</span><span class="sxs-lookup"><span data-stu-id="a401a-127">None</span></span>

## <span data-ttu-id="a401a-128">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a401a-128">OUTPUTS</span></span>

### <span data-ttu-id="a401a-129">None</span><span class="sxs-lookup"><span data-stu-id="a401a-129">None</span></span>

## <span data-ttu-id="a401a-130">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a401a-130">NOTES</span></span>

## <span data-ttu-id="a401a-131">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a401a-131">RELATED LINKS</span></span>

[<span data-ttu-id="a401a-132">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="a401a-132">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a401a-133">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="a401a-133">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="a401a-134">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a401a-134">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

