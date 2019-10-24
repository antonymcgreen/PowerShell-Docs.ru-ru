---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72352110"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="794db-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="794db-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="794db-104">Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"</span><span class="sxs-lookup"><span data-stu-id="794db-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="794db-105">Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="794db-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="794db-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="794db-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="794db-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="794db-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="794db-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="794db-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="794db-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="794db-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a><span data-ttu-id="794db-110">Требуемые сетевые конечные точки</span><span class="sxs-lookup"><span data-stu-id="794db-110">Required network endpoints</span></span>

<span data-ttu-id="794db-111">Для командлетов Install и Update требуется доступ к Интернету для подключения к конечным точкам сети, используемым коллекцией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="794db-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="794db-112">Убедитесь, что политики сетевого доступа позволяют подключаться к приведенным ниже конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="794db-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="794db-113">oneget.org</span><span class="sxs-lookup"><span data-stu-id="794db-113">oneget.org</span></span>
- <span data-ttu-id="794db-114">go.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="794db-114">go.microsoft.com</span></span>
- <span data-ttu-id="794db-115">az818661.vo.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="794db-115">az818661.vo.msecnd.net</span></span>
- <span data-ttu-id="794db-116">[www.powershellgallery.com](www.powershellgallery.com)</span><span class="sxs-lookup"><span data-stu-id="794db-116">www.powershellgallery.com</span></span>
- <span data-ttu-id="794db-117">devopsgallerystorage.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="794db-117">devopsgallerystorage.blob.core.windows.net</span></span>
