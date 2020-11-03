---
description: Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231834"
---
# <a name="about-telemetry"></a><span data-ttu-id="a17b6-104">Сведения о телеметрии</span><span class="sxs-lookup"><span data-stu-id="a17b6-104">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="a17b6-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a17b6-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a17b6-106">Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.</span><span class="sxs-lookup"><span data-stu-id="a17b6-106">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="a17b6-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a17b6-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a17b6-108">PowerShell отправляет базовые данные телеметрии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a17b6-108">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="a17b6-109">Они позволяют нам лучше понимать среды, где используется PowerShell, а также приоритизировать новые функции и исправления.</span><span class="sxs-lookup"><span data-stu-id="a17b6-109">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="a17b6-110">Записываются следующие точки телеметрии:</span><span class="sxs-lookup"><span data-stu-id="a17b6-110">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="a17b6-111">Число запусков PowerShell по типу (консоль API VS)</span><span class="sxs-lookup"><span data-stu-id="a17b6-111">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="a17b6-112">Число уникальных использований PowerShell</span><span class="sxs-lookup"><span data-stu-id="a17b6-112">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="a17b6-113">Число следующих типов выполнения:</span><span class="sxs-lookup"><span data-stu-id="a17b6-113">Count of the following execution types:</span></span>
  - <span data-ttu-id="a17b6-114">Приложение (собственные команды)</span><span class="sxs-lookup"><span data-stu-id="a17b6-114">Application (native commands)</span></span>
  - <span data-ttu-id="a17b6-115">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="a17b6-115">ExternalScript</span></span>
  - <span data-ttu-id="a17b6-116">Сценарий</span><span class="sxs-lookup"><span data-stu-id="a17b6-116">Script</span></span>
  - <span data-ttu-id="a17b6-117">Компонент</span><span class="sxs-lookup"><span data-stu-id="a17b6-117">Function</span></span>
  - <span data-ttu-id="a17b6-118">Командлет</span><span class="sxs-lookup"><span data-stu-id="a17b6-118">Cmdlet</span></span>
- <span data-ttu-id="a17b6-119">Число включенных экспериментальных функций Майкрософт или экспериментальных функций, поставляемых с PowerShell</span><span class="sxs-lookup"><span data-stu-id="a17b6-119">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="a17b6-120">Число размещенных сеансов</span><span class="sxs-lookup"><span data-stu-id="a17b6-120">Count of hosted sessions</span></span>
- <span data-ttu-id="a17b6-121">Число загруженных модулей, принадлежащих корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a17b6-121">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="a17b6-122">Эти данные включают имя ОС, версию ОС, версию PowerShell и канал распространения.</span><span class="sxs-lookup"><span data-stu-id="a17b6-122">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="a17b6-123">Чтобы отказаться от этой телеметрии, задайте для переменной среды POWERSHELL_TELEMETRY_OPTOUT значение true, да или 1.</span><span class="sxs-lookup"><span data-stu-id="a17b6-123">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

