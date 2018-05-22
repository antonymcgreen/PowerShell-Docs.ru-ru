---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: e8890cb6bbe661b8524d83cabf91483acbde8095
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="cc0cd-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="cc0cd-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="cc0cd-104">Как разрешить проблему "ПРЕДУПРЕЖДЕНИЕ. Не удалось скачать пакет "имя вашего пакета""?</span><span class="sxs-lookup"><span data-stu-id="cc0cd-104">How to resolve "WARNING: Package 'your package name' failed to download" issue?</span></span>

<span data-ttu-id="cc0cd-105">Нам известно, что на некоторых компьютерах командлеты Install-Module и Update-Module могут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cc0cd-105">It is reported that Install-Module or Update-Module sometimes fails on some machines.</span></span>
<span data-ttu-id="cc0cd-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="cc0cd-106">Based on our investigation, it is something to do with the networking connection.</span></span>
<span data-ttu-id="cc0cd-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="cc0cd-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span>
<span data-ttu-id="cc0cd-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="cc0cd-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span>
<span data-ttu-id="cc0cd-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="cc0cd-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```