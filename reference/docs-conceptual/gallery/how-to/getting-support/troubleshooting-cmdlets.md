---
ms.date: 12/01/2020
title: Командлеты для устранения неполадок
description: В этой статье приведены сведения и шаги по устранению ошибок с помощью коллекции PowerShell.
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913324"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="103eb-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="103eb-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="103eb-104">Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"</span><span class="sxs-lookup"><span data-stu-id="103eb-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="103eb-105">Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="103eb-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="103eb-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="103eb-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="103eb-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="103eb-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="103eb-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="103eb-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="103eb-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="103eb-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="103eb-110">Требуемые сетевые конечные точки</span><span class="sxs-lookup"><span data-stu-id="103eb-110">Required network endpoints</span></span>

<span data-ttu-id="103eb-111">Для командлетов Install и Update требуется доступ к Интернету для подключения к конечным точкам сети, используемым коллекцией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="103eb-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="103eb-112">Убедитесь, что политики сетевого доступа позволяют подключаться к приведенным ниже конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="103eb-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="103eb-113">`psg-prod-eastus.azureedge.net` — имя узла CDN;</span><span class="sxs-lookup"><span data-stu-id="103eb-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="103eb-114">`az818661.vo.msecnd.net` — имя узла CDN;</span><span class="sxs-lookup"><span data-stu-id="103eb-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="103eb-115">`devopsgallerystorage.blob.core.windows.net` — имя узла учетной записи хранения;</span><span class="sxs-lookup"><span data-stu-id="103eb-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="103eb-116">`*.powershellgallery.com` — веб-сайт;</span><span class="sxs-lookup"><span data-stu-id="103eb-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="103eb-117">`go.microsoft.com` — служба перенаправления.</span><span class="sxs-lookup"><span data-stu-id="103eb-117">`go.microsoft.com` - redirection service</span></span>

> [!NOTE]
> <span data-ttu-id="103eb-118">Если возникнет сбой служб коллекции PowerShell, командлеты, которые взаимодействуют с коллекцией PowerShell, могут привести к сбою с непредвиденными ошибками.</span><span class="sxs-lookup"><span data-stu-id="103eb-118">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="103eb-119">Сведения о текущем состоянии коллекции PowerShell см. на странице [Состояние коллекции PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="103eb-119">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
