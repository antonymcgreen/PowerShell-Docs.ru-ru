---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=855965
Help Version: 6.2.5.0
keywords: powershell,командлет
Locale: en-US
Module Guid: c61d6278-02a3-4618-ae37-a524d40a7f44
Module Name: PSDiagnostics
ms.date: 11/27/2018
schema: 2.0.0
title: Модуль PSDiagnostics
ms.openlocfilehash: 10bd2d740ce4b21b7e0867c870a55a01a94ee499
ms.sourcegitcommit: 3571b9e87e8881adbf7984cda46a63891039a987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "93209435"
---
# <span data-ttu-id="e5837-103">Модуль PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="e5837-103">PSDiagnostics Module</span></span>

## <span data-ttu-id="e5837-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e5837-104">Description</span></span>

<span data-ttu-id="e5837-105">Модуль диагностики PowerShell содержит набор командлетов, которые позволяют использовать трассировку ETW в PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="e5837-105">The PowerShell Diagnostics Module contains a set of cmdlets that enables the use of ETW tracing in PowerShell on Windows.</span></span>

## <span data-ttu-id="e5837-106">Командлеты PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="e5837-106">PSDiagnostics Cmdlets</span></span>

### [<span data-ttu-id="e5837-107">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-107">Disable-PSTrace</span></span>](Disable-PSTrace.md)
<span data-ttu-id="e5837-108">Отключает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5837-108">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="e5837-109">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-109">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
<span data-ttu-id="e5837-110">Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.</span><span class="sxs-lookup"><span data-stu-id="e5837-110">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

### [<span data-ttu-id="e5837-111">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-111">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
<span data-ttu-id="e5837-112">Останавливает сеанс ведения журнала WSMan, запущенный параметром enable-Всмантраце.</span><span class="sxs-lookup"><span data-stu-id="e5837-112">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

### [<span data-ttu-id="e5837-113">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-113">Enable-PSTrace</span></span>](Enable-PSTrace.md)
<span data-ttu-id="e5837-114">Включает журналы поставщика событий Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5837-114">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="e5837-115">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-115">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
<span data-ttu-id="e5837-116">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5837-116">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

### [<span data-ttu-id="e5837-117">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e5837-117">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
<span data-ttu-id="e5837-118">Запустите сеанс ведения журнала с включенными поставщиками WSMan.</span><span class="sxs-lookup"><span data-stu-id="e5837-118">Start a logging session with the WSMan providers enabled.</span></span>

### [<span data-ttu-id="e5837-119">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="e5837-119">Get-LogProperties</span></span>](Get-LogProperties.md)
<span data-ttu-id="e5837-120">Извлекает свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e5837-120">Retrieves the properties of a Windows event log.</span></span>

### [<span data-ttu-id="e5837-121">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="e5837-121">Set-LogProperties</span></span>](Set-LogProperties.md)
<span data-ttu-id="e5837-122">Изменяет свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e5837-122">Changes the properties of a Windows event log.</span></span>

### [<span data-ttu-id="e5837-123">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e5837-123">Start-Trace</span></span>](Start-Trace.md)
<span data-ttu-id="e5837-124">Запустите сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="e5837-124">Start an Event Trace logging session.</span></span>

### [<span data-ttu-id="e5837-125">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="e5837-125">Stop-Trace</span></span>](Stop-Trace.md)
<span data-ttu-id="e5837-126">Останавливает сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="e5837-126">Stop an Event Trace logging session.</span></span>
