---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: f5cd9c0cc23fef5891bf02c10b6541ab0f9d418a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084187"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="f59ea-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="f59ea-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="f59ea-104">Как разрешить проблему "Предупреждение. Не удалось скачать пакет "имя пакета"</span><span class="sxs-lookup"><span data-stu-id="f59ea-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="f59ea-105">Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f59ea-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span>
<span data-ttu-id="f59ea-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="f59ea-106">Based on our investigation, it is something to do with the networking connection.</span></span>
<span data-ttu-id="f59ea-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="f59ea-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span>
<span data-ttu-id="f59ea-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="f59ea-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span>
<span data-ttu-id="f59ea-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="f59ea-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```
