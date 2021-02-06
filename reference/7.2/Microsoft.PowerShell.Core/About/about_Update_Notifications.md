---
description: Уведомляет пользователей о запуске PowerShell о том, что была выпущена новая версия PowerShell.
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 1a9f8cfec15f83566fdb77175dcc1aed6d9e8c34
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604561"
---
# <a name="about-update-notifications"></a><span data-ttu-id="1511c-103">Уведомления об обновлениях</span><span class="sxs-lookup"><span data-stu-id="1511c-103">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="1511c-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1511c-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="1511c-105">Уведомляет пользователей о запуске PowerShell о том, что была выпущена новая версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1511c-105">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="1511c-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1511c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="1511c-107">Начиная с PowerShell 7,0, PowerShell использует уведомления об обновлениях для оповещения пользователей о существовании обновлений для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1511c-107">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="1511c-108">Раз в день PowerShell выполняет запрос к веб-службе, чтобы определить, доступна ли более новая версия.</span><span class="sxs-lookup"><span data-stu-id="1511c-108">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="1511c-109">Хотя проверка обновлений происходит во время первого сеанса в течение заданного 24-часового периода, по соображениям производительности уведомление будет отображаться только в начале последующих сеансов.</span><span class="sxs-lookup"><span data-stu-id="1511c-109">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="1511c-110">Кроме того, по соображениям производительности проверка не будет запускаться до начала сеанса по крайней мере через 3 секунды.</span><span class="sxs-lookup"><span data-stu-id="1511c-110">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="1511c-111">По умолчанию PowerShell подписывается на один из двух разных каналов уведомлений в зависимости от версии и ветви.</span><span class="sxs-lookup"><span data-stu-id="1511c-111">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="1511c-112">В поддерживаемых общедоступных (GA) версиях PowerShell уведомления возвращаются только для обновленных общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="1511c-112">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="1511c-113">В предварительных выпусках и релизах-кандидатах (RC) выводятся уведомления об обновлениях для предварительных выпусков, релизов-кандидатов и общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="1511c-113">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="1511c-114">Настроить уведомления об обновлениях можно с помощью переменной среды `POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="1511c-114">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="1511c-115">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="1511c-115">The following values are supported:</span></span>

- <span data-ttu-id="1511c-116">`Off` отключает функцию уведомления об обновлении</span><span class="sxs-lookup"><span data-stu-id="1511c-116">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="1511c-117">`Default` то же самое, что не определяет `POWERSHELL_UPDATECHECK` :</span><span class="sxs-lookup"><span data-stu-id="1511c-117">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="1511c-118">В общедоступных выпусках выводятся уведомления об обновлениях для общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="1511c-118">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="1511c-119">В предварительных выпусках и релизах-кандидатах выводятся уведомления об обновлениях для общедоступных и предварительных выпусков.</span><span class="sxs-lookup"><span data-stu-id="1511c-119">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="1511c-120">`LTS` уведомления об обновлениях только для выпусков долгосрочного обслуживания (LTS)</span><span class="sxs-lookup"><span data-stu-id="1511c-120">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="1511c-121">В настоящее время для определения последней версии каждого канала используются следующие конечные точки:</span><span class="sxs-lookup"><span data-stu-id="1511c-121">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="1511c-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="1511c-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="1511c-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="1511c-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="1511c-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="1511c-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="1511c-125">Уведомление об обновлении не предоставляет никакого способа автоматического обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1511c-125">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="1511c-126">В будущем могут возникать дополнительные инструкции или возможности для обновления с помощью PowerShell, но в настоящее время следует использовать тот же механизм установки, который использовался для установки PowerShell для обновления.</span><span class="sxs-lookup"><span data-stu-id="1511c-126">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>

