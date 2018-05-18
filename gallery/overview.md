---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery,psget
title: Коллекция PowerShell
ms.openlocfilehash: cffb2f0182ffe9072f9fbbc7f4cdfcf28de276db
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="43389-103">Коллекция PowerShell</span><span class="sxs-lookup"><span data-stu-id="43389-103">The PowerShell Gallery</span></span>

<span data-ttu-id="43389-104">Коллекция PowerShell — это центральный репозиторий для хранения содержимого PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43389-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="43389-105">В ней можно найти полезные модули PowerShell с командами и ресурсы настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="43389-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="43389-106">Здесь также представлены скрипты PowerShell, некоторые из которых могут содержать рабочие процессы PowerShell. Они описывают набор задач и реализуют конвейер для их выполнения.</span><span class="sxs-lookup"><span data-stu-id="43389-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="43389-107">Некоторые из этих элементов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43389-107">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="43389-108">Обзор PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="43389-108">PowerShellGet Overview</span></span>

<span data-ttu-id="43389-109">Модуль PowerShellGet содержит командлеты для обнаружения, установки, обновления и публикации артефактов PowerShell, таких как модули, ресурсы DSC, возможности ролей и скрипты из [коллекции PowerShell](https://www.PowerShellGallery.com) и других частных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="43389-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="43389-110">Начало работы с коллекцией</span><span class="sxs-lookup"><span data-stu-id="43389-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="43389-111">Для установки элементов из коллекции требуется последняя версия модуля PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="43389-111">Installing items from the Gallery requires the latest version of the PowerShellGet module.</span></span>
<span data-ttu-id="43389-112">Полные инструкции по установке см. в разделе [Установка PowerShellGet](installing-psget.md).</span><span class="sxs-lookup"><span data-stu-id="43389-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="43389-113">Дополнительные сведения об использовании команд PowerShellGet при работе с коллекцией см. в статье [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="43389-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="43389-114">Вы также можете запустить командлет *Update-Help -Module PowerShellGet*, чтобы установить локальную справку по этим командам.</span><span class="sxs-lookup"><span data-stu-id="43389-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="43389-115">Поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="43389-115">Supported Operating Systems</span></span>

<span data-ttu-id="43389-116">Для модуля **PowerShellGet** требуется **PowerShell 3.0 или более поздней версии**.</span><span class="sxs-lookup"><span data-stu-id="43389-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="43389-117">Таким образом, для **PowerShellGet** требуется одна из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="43389-117">Therefore, **PowerShellGet** requires one of the following operating systems:</span></span>

- <span data-ttu-id="43389-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="43389-118">Windows 10</span></span>
- <span data-ttu-id="43389-119">Windows 8.1 Профессиональная</span><span class="sxs-lookup"><span data-stu-id="43389-119">Windows 8.1 Pro</span></span>
- <span data-ttu-id="43389-120">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="43389-120">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="43389-121">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="43389-121">Windows 7 SP1</span></span>
- <span data-ttu-id="43389-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="43389-122">Windows Server 2016</span></span>
- <span data-ttu-id="43389-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="43389-123">Windows Server 2012 R2</span></span>
- <span data-ttu-id="43389-124">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="43389-124">Windows Server 2008 R2 SP1</span></span>

<span data-ttu-id="43389-125">Для **PowerShellGet** также требуется .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="43389-125">**PowerShellGet** also requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="43389-126">Установить .NET Framework 4.5 или более поздней версии можно [отсюда](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span><span class="sxs-lookup"><span data-stu-id="43389-126">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="43389-127">Возник вопрос?</span><span class="sxs-lookup"><span data-stu-id="43389-127">Got a question?</span></span> <span data-ttu-id="43389-128">Хотите поделиться мнением?</span><span class="sxs-lookup"><span data-stu-id="43389-128">Have feedback?</span></span>

<span data-ttu-id="43389-129">Дополнительные сведения о коллекции PowerShell и PowerShellGet см. на странице [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="43389-129">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="43389-130">Оставить отзыв или сообщить о проблеме можно на сайте [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span><span class="sxs-lookup"><span data-stu-id="43389-130">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>