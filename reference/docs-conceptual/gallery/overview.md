---
ms.date: 12/01/2020
title: Коллекция PowerShell
description: Коллекция PowerShell — это центральный репозиторий для хранения модулей, скриптов PowerShell и ресурсов DSC.
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470321"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="5cf1d-103">Коллекция PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cf1d-103">The PowerShell Gallery</span></span>

<span data-ttu-id="5cf1d-104">Коллекция PowerShell — это центральный репозиторий для хранения содержимого PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="5cf1d-105">В ней можно найти полезные модули PowerShell с командами и ресурсы настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="5cf1d-106">Здесь также представлены скрипты PowerShell, некоторые из которых могут содержать рабочие процессы PowerShell. Они описывают набор задач и реализуют конвейер для их выполнения.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="5cf1d-107">Некоторые из этих пакетов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="5cf1d-108">Обзор PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5cf1d-108">PowerShellGet Overview</span></span>

<span data-ttu-id="5cf1d-109">Модуль PowerShellGet содержит командлеты для обнаружения, установки, обновления и публикации пакетов PowerShell, которые содержат такие артефакты, как модули, ресурсы DSC, возможности ролей и скрипты из [коллекции PowerShell](https://www.PowerShellGallery.com) и других частных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="5cf1d-110">Начало работы с коллекцией</span><span class="sxs-lookup"><span data-stu-id="5cf1d-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="5cf1d-111">Для установки пакетов из коллекции требуется последняя версия модуля PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="5cf1d-112">Полные инструкции по установке см. в разделе [Установка PowerShellGet](installing-psget.md).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="5cf1d-113">Дополнительные сведения об использовании команд PowerShellGet при работе с коллекцией см. в статье [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="5cf1d-114">Вы также можете запустить командлет *Update-Help -Module PowerShellGet*, чтобы установить локальную справку по этим командам.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="5cf1d-115">Поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="5cf1d-115">Supported Operating Systems</span></span>

<span data-ttu-id="5cf1d-116">Для модуля **PowerShellGet** требуется **PowerShell 3.0 или более поздней версии**.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="5cf1d-117">Для **PowerShellGet** требуется .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="5cf1d-118">См. дополнительные сведения об [установке .NET Framework для разработчиков](/dotnet/framework/install/guide-for-developers).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-118">For more information, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

<span data-ttu-id="5cf1d-119">Так как **PowerShell Core** является кроссплатформенным решением, которое работает в Windows, Linux и MacOS, это также означает поддержку **PowerShellGet** в этих системах.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="5cf1d-120">Полный список систем, поддерживаемых **PowerShell Core**, см. в руководстве по [установке PowerShell](/powershell/scripting/install/installing-powershell).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="5cf1d-121">Много модулей, размещенных в коллекции, поддерживают различные ОС и имеют дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="5cf1d-122">Дополнительные сведения см. в документации по модулям.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="5cf1d-123">Возник вопрос?</span><span class="sxs-lookup"><span data-stu-id="5cf1d-123">Got a question?</span></span> <span data-ttu-id="5cf1d-124">Хотите поделиться мнением?</span><span class="sxs-lookup"><span data-stu-id="5cf1d-124">Have feedback?</span></span>

<span data-ttu-id="5cf1d-125">Дополнительные сведения о коллекции PowerShell и PowerShellGet см. на странице [Начало работы](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span>

<span data-ttu-id="5cf1d-126">Сведения о текущем состоянии служб коллекции PowerShell см. на странице [Состояние коллекции PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="5cf1d-126">To see the current status of the PowerShell Gallery services, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>

<span data-ttu-id="5cf1d-127">Оставить отзыв или сообщить о проблеме можно в [репозитории GitHub](https://github.com/PowerShell/PowerShellGallery/issues).</span><span class="sxs-lookup"><span data-stu-id="5cf1d-127">Please provide feedback and report issues the [GitHub repository](https://github.com/PowerShell/PowerShellGallery/issues).</span></span>
