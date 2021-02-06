---
description: Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600483"
---
# <a name="about-telemetry"></a><span data-ttu-id="18160-103">Сведения о телеметрии</span><span class="sxs-lookup"><span data-stu-id="18160-103">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="18160-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="18160-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="18160-105">Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.</span><span class="sxs-lookup"><span data-stu-id="18160-105">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="18160-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="18160-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="18160-107">PowerShell отправляет базовые данные телеметрии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="18160-107">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="18160-108">Они позволяют нам лучше понимать среды, где используется PowerShell, а также приоритизировать новые функции и исправления.</span><span class="sxs-lookup"><span data-stu-id="18160-108">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="18160-109">Записываются следующие точки телеметрии:</span><span class="sxs-lookup"><span data-stu-id="18160-109">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="18160-110">Число запусков PowerShell по типу (консоль API VS)</span><span class="sxs-lookup"><span data-stu-id="18160-110">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="18160-111">Число уникальных использований PowerShell</span><span class="sxs-lookup"><span data-stu-id="18160-111">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="18160-112">Число следующих типов выполнения:</span><span class="sxs-lookup"><span data-stu-id="18160-112">Count of the following execution types:</span></span>
  - <span data-ttu-id="18160-113">Приложение (собственные команды)</span><span class="sxs-lookup"><span data-stu-id="18160-113">Application (native commands)</span></span>
  - <span data-ttu-id="18160-114">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="18160-114">ExternalScript</span></span>
  - <span data-ttu-id="18160-115">Скрипт</span><span class="sxs-lookup"><span data-stu-id="18160-115">Script</span></span>
  - <span data-ttu-id="18160-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="18160-116">Function</span></span>
  - <span data-ttu-id="18160-117">Командлет</span><span class="sxs-lookup"><span data-stu-id="18160-117">Cmdlet</span></span>
- <span data-ttu-id="18160-118">Число включенных экспериментальных функций Майкрософт или экспериментальных функций, поставляемых с PowerShell</span><span class="sxs-lookup"><span data-stu-id="18160-118">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="18160-119">Число размещенных сеансов</span><span class="sxs-lookup"><span data-stu-id="18160-119">Count of hosted sessions</span></span>
- <span data-ttu-id="18160-120">Число загруженных модулей, принадлежащих корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="18160-120">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="18160-121">Эти данные включают имя ОС, версию ОС, версию PowerShell и канал распространения.</span><span class="sxs-lookup"><span data-stu-id="18160-121">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="18160-122">Чтобы отказаться от этой телеметрии, задайте для переменной среды POWERSHELL_TELEMETRY_OPTOUT значение true, да или 1.</span><span class="sxs-lookup"><span data-stu-id="18160-122">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

