---
ms.date: 01/25/2021
title: Командлеты для устранения неполадок
description: В этой статье приведены сведения и шаги по устранению ошибок с помощью коллекции PowerShell.
ms.openlocfilehash: 8139147683b655b5f8532c3068387db6df12a98f
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771820"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="a05b0-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="a05b0-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="a05b0-104">Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"</span><span class="sxs-lookup"><span data-stu-id="a05b0-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="a05b0-105">Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a05b0-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="a05b0-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="a05b0-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="a05b0-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="a05b0-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="a05b0-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="a05b0-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="a05b0-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="a05b0-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="a05b0-110">Требуемые сетевые конечные точки</span><span class="sxs-lookup"><span data-stu-id="a05b0-110">Required network endpoints</span></span>

<span data-ttu-id="a05b0-111">Для командлетов Install и Update требуется доступ к Интернету для подключения к конечным точкам сети, используемым коллекцией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a05b0-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="a05b0-112">Убедитесь, что политики сетевого доступа позволяют подключаться к приведенным ниже конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="a05b0-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="a05b0-113">`psg-prod-eastus.azureedge.net` — имя узла CDN;</span><span class="sxs-lookup"><span data-stu-id="a05b0-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="a05b0-114">`az818661.vo.msecnd.net` — имя узла CDN;</span><span class="sxs-lookup"><span data-stu-id="a05b0-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="a05b0-115">`devopsgallerystorage.blob.core.windows.net` — имя узла учетной записи хранения;</span><span class="sxs-lookup"><span data-stu-id="a05b0-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="a05b0-116">`*.powershellgallery.com` — веб-сайт;</span><span class="sxs-lookup"><span data-stu-id="a05b0-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="a05b0-117">`go.microsoft.com` — служба перенаправления.</span><span class="sxs-lookup"><span data-stu-id="a05b0-117">`go.microsoft.com` - redirection service</span></span>
- <span data-ttu-id="a05b0-118">`onegetcdn.azureedge.net` — начальная загрузка поставщика NuGet в `PowerShellGet/PackageManagement`.</span><span class="sxs-lookup"><span data-stu-id="a05b0-118">`onegetcdn.azureedge.net` - bootstrap the NuGet Provider in `PowerShellGet/PackageManagement`</span></span>

> [!NOTE]
> <span data-ttu-id="a05b0-119">Если возникнет сбой служб коллекции PowerShell, командлеты, которые взаимодействуют с коллекцией PowerShell, могут привести к сбою с непредвиденными ошибками.</span><span class="sxs-lookup"><span data-stu-id="a05b0-119">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="a05b0-120">Сведения о текущем состоянии коллекции PowerShell см. на странице [Состояние коллекции PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="a05b0-120">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
