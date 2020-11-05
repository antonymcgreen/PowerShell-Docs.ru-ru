---
ms.date: 06/12/2017
title: Профиль правила ScriptAnalyzer для коллекции
description: В этой статье описывается, как PowerShell ScriptAnalyzer интегрируется с коллекцией PowerShell.
ms.openlocfilehash: 3af710e8811f0fabfb02f5317d5b4ff9c320f29a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646764"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="c9f6d-103">Профиль правила ScriptAnalyzer для коллекции</span><span class="sxs-lookup"><span data-stu-id="c9f6d-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="c9f6d-104">Для обеспечения качества пакетов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие нарушений в отправленных скриптах.</span><span class="sxs-lookup"><span data-stu-id="c9f6d-104">To ensure the quality of packages published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="c9f6d-105">Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span><span class="sxs-lookup"><span data-stu-id="c9f6d-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="c9f6d-106">По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalyzer.</span><span class="sxs-lookup"><span data-stu-id="c9f6d-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalyzer.</span></span>

<span data-ttu-id="c9f6d-107">Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного пакета в коллекции в готовящемся выпуске.</span><span class="sxs-lookup"><span data-stu-id="c9f6d-107">ScriptAnalyzer results will be displayed on each individual package page in Gallery in the coming release.</span></span> <span data-ttu-id="c9f6d-108">Владельцам пакетов рекомендуется проверять опубликованные пакеты на наличие серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="c9f6d-108">We encourage package owners to check their packages to make sure there are no severe errors in published packages.</span></span>
