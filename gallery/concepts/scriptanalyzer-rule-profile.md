---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Профиль правила ScriptAnalyzer для коллекции
ms.openlocfilehash: d91a88981cc2f3269a1f8b6ee864f8333a2f097c
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002502"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="73c22-103">Профиль правила ScriptAnalyzer для коллекции</span><span class="sxs-lookup"><span data-stu-id="73c22-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="73c22-104">Для обеспечения качества пакетов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие нарушений в отправленных скриптах.</span><span class="sxs-lookup"><span data-stu-id="73c22-104">To ensure the quality of packages published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="73c22-105">Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span><span class="sxs-lookup"><span data-stu-id="73c22-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="73c22-106">По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalzyer.</span><span class="sxs-lookup"><span data-stu-id="73c22-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalzyer.</span></span>

<span data-ttu-id="73c22-107">Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного пакета в коллекции в готовящемся выпуске.</span><span class="sxs-lookup"><span data-stu-id="73c22-107">ScriptAnalyzer results will be displayed on each individual package page in Gallery in the coming release.</span></span> <span data-ttu-id="73c22-108">Владельцам пакетов рекомендуется проверять опубликованные пакеты на наличие серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="73c22-108">We encourage package owners to check their packages to make sure there are no severe errors in published packages.</span></span>
