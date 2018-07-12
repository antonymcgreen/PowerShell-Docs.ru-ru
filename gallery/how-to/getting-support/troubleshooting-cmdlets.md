---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Командлеты для устранения неполадок
ms.openlocfilehash: c0a1fbcafd8c4443dc9d628c54c4c525d9701861
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892480"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="b4600-103">Командлеты для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="b4600-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="b4600-104">Как разрешить проблему "ПРЕДУПРЕЖДЕНИЕ. Не удалось скачать пакет "имя пакета"</span><span class="sxs-lookup"><span data-stu-id="b4600-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="b4600-105">Нам известно, что на некоторых компьютерах выполнение командлетов `Install-Module` и `Update-Module` может завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b4600-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span>
<span data-ttu-id="b4600-106">По результатам нашего расследования это связано с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="b4600-106">Based on our investigation, it is something to do with the networking connection.</span></span>
<span data-ttu-id="b4600-107">Недавно мы обновили поставщик NuGet, чтобы он смог надежно скачивать пакеты.</span><span class="sxs-lookup"><span data-stu-id="b4600-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span>
<span data-ttu-id="b4600-108">Выполните описанные ниже инструкции, чтобы установить последнюю сборку поставщика NuGet, а затем установите или обновите свой модуль.</span><span class="sxs-lookup"><span data-stu-id="b4600-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span>
<span data-ttu-id="b4600-109">Для примера возьмем модуль Azure.</span><span class="sxs-lookup"><span data-stu-id="b4600-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```