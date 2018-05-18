---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery
title: Профиль правила ScriptAnalyzer для коллекции
ms.openlocfilehash: 22b95f0901fe95d5ad79df0e23e675ab52313fee
ms.sourcegitcommit: f8a37df92db22b9368469fb07378399b2ab90cea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2018
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="2ab14-103">Профиль правила ScriptAnalyzer для коллекции</span><span class="sxs-lookup"><span data-stu-id="2ab14-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="2ab14-104">Для обеспечения качества элементов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие любых нарушений в отправленных скриптах.</span><span class="sxs-lookup"><span data-stu-id="2ab14-104">To ensure the quality of items published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="2ab14-105">Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span><span class="sxs-lookup"><span data-stu-id="2ab14-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="2ab14-106">По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalzyer.</span><span class="sxs-lookup"><span data-stu-id="2ab14-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalzyer.</span></span>

<span data-ttu-id="2ab14-107">Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного элемента в коллекции в готовящемся выпуске.</span><span class="sxs-lookup"><span data-stu-id="2ab14-107">ScriptAnalyzer results will be displayed on each individual item page in Gallery in the coming release.</span></span> <span data-ttu-id="2ab14-108">Владельцам элементов рекомендуется проверять опубликованные элементы на наличие серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="2ab14-108">We encourage item owners to check their items to make sure there are no severe errors in published items.</span></span>
