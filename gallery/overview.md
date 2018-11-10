---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery,psget
title: Коллекция PowerShell
ms.openlocfilehash: d3e3b9d8bb3d6cefd3a3bfe79b012bb1dc1d8a2d
ms.sourcegitcommit: e76665315fd928bf85210778f1fea2be15264fea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50225624"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="db034-103">Коллекция PowerShell</span><span class="sxs-lookup"><span data-stu-id="db034-103">The PowerShell Gallery</span></span>

<span data-ttu-id="db034-104">Коллекция PowerShell — это центральный репозиторий для хранения содержимого PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db034-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="db034-105">В ней можно найти полезные модули PowerShell с командами и ресурсы настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="db034-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="db034-106">Здесь также представлены скрипты PowerShell, некоторые из которых могут содержать рабочие процессы PowerShell. Они описывают набор задач и реализуют конвейер для их выполнения.</span><span class="sxs-lookup"><span data-stu-id="db034-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="db034-107">Некоторые из этих пакетов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db034-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="db034-108">Обзор PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="db034-108">PowerShellGet Overview</span></span>

<span data-ttu-id="db034-109">Модуль PowerShellGet содержит командлеты для обнаружения, установки, обновления и публикации пакетов PowerShell, которые содержат такие артефакты, как модули, ресурсы DSC, возможности ролей и скрипты из [коллекции PowerShell](https://www.PowerShellGallery.com) и других частных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="db034-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="db034-110">Начало работы с коллекцией</span><span class="sxs-lookup"><span data-stu-id="db034-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="db034-111">Для установки пакетов из коллекции требуется последняя версия модуля PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="db034-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span>
<span data-ttu-id="db034-112">Полные инструкции по установке см. в разделе [Установка PowerShellGet](installing-psget.md).</span><span class="sxs-lookup"><span data-stu-id="db034-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="db034-113">Дополнительные сведения об использовании команд PowerShellGet при работе с коллекцией см. в статье [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="db034-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="db034-114">Вы также можете запустить командлет *Update-Help -Module PowerShellGet*, чтобы установить локальную справку по этим командам.</span><span class="sxs-lookup"><span data-stu-id="db034-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="db034-115">Поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="db034-115">Supported Operating Systems</span></span>

<span data-ttu-id="db034-116">Для модуля **PowerShellGet** требуется **Windows PowerShell версии 3.0 или более поздней** либо **PowerShell Core версии 6.0 или более поздней**.</span><span class="sxs-lookup"><span data-stu-id="db034-116">The **PowerShellGet** module requires **Windows PowerShell 3.0 or newer**, or **PowerShell Core 6.0 or newer**.</span></span>

<span data-ttu-id="db034-117">Подходящая версия **Windows PowerShell** доступна для следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="db034-117">A suitable version of **Windows PowerShell** is available for these operating systems:</span></span>

- <span data-ttu-id="db034-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db034-118">Windows 10</span></span>
- <span data-ttu-id="db034-119">Windows 8.1 Профессиональная</span><span class="sxs-lookup"><span data-stu-id="db034-119">Windows 8.1 Pro</span></span>
- <span data-ttu-id="db034-120">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="db034-120">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="db034-121">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="db034-121">Windows 7 SP1</span></span>
- <span data-ttu-id="db034-122">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="db034-122">Windows Server 2019</span></span>
- <span data-ttu-id="db034-123">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="db034-123">Windows Server 2016</span></span>
- <span data-ttu-id="db034-124">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="db034-124">Windows Server 2012 R2</span></span>
- <span data-ttu-id="db034-125">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="db034-125">Windows Server 2008 R2 SP1</span></span>

<span data-ttu-id="db034-126">Для **PowerShellGet** требуется .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="db034-126">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="db034-127">Установить .NET Framework 4.5 или более поздней версии можно [отсюда](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span><span class="sxs-lookup"><span data-stu-id="db034-127">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

<span data-ttu-id="db034-128">Так как **PowerShell Core** является кроссплатформенным решением, которое работает в Windows, Linux и MacOS, это также означает поддержку **PowerShellGet** в этих системах.</span><span class="sxs-lookup"><span data-stu-id="db034-128">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="db034-129">Полный список систем, поддерживаемых **PowerShell Core**, см. в руководстве по [установке PowerShell](/powershell/scripting/setup/installing-powershell).</span><span class="sxs-lookup"><span data-stu-id="db034-129">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/setup/installing-powershell).</span></span>

<span data-ttu-id="db034-130">Много модулей, размещенных в коллекции, поддерживают различные ОС и имеют дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="db034-130">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span> <span data-ttu-id="db034-131">Дополнительные сведения см. в документации по модулям.</span><span class="sxs-lookup"><span data-stu-id="db034-131">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="db034-132">Возник вопрос?</span><span class="sxs-lookup"><span data-stu-id="db034-132">Got a question?</span></span> <span data-ttu-id="db034-133">Хотите поделиться мнением?</span><span class="sxs-lookup"><span data-stu-id="db034-133">Have feedback?</span></span>

<span data-ttu-id="db034-134">Дополнительные сведения о коллекции PowerShell и PowerShellGet см. на странице [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="db034-134">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="db034-135">Оставить отзыв или сообщить о проблеме можно на сайте [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span><span class="sxs-lookup"><span data-stu-id="db034-135">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>
