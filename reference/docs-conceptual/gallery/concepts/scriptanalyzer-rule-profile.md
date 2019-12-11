---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Профиль правила ScriptAnalyzer для коллекции
ms.openlocfilehash: 939f01dece56b283dbe6e03c888f42ff866707af
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328475"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a><span data-ttu-id="16a4a-103">Профиль правила ScriptAnalyzer для коллекции</span><span class="sxs-lookup"><span data-stu-id="16a4a-103">ScriptAnalyzer rule profile for Gallery</span></span>

<span data-ttu-id="16a4a-104">Для обеспечения качества пакетов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие нарушений в отправленных скриптах.</span><span class="sxs-lookup"><span data-stu-id="16a4a-104">To ensure the quality of packages published to PowerShell Gallery, we run [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) rules to determine if there are any violations in the scripts submitted.</span></span>

<span data-ttu-id="16a4a-105">Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span><span class="sxs-lookup"><span data-stu-id="16a4a-105">You can find the list of rules we are running on ScriptAnalyzer [GitHub page](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).</span></span>
<span data-ttu-id="16a4a-106">По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalyzer.</span><span class="sxs-lookup"><span data-stu-id="16a4a-106">If you have any concerns regarding the rules we are running, please contact PowerShell Gallery Administrators, or open an issue for ScriptAnalyzer.</span></span>

<span data-ttu-id="16a4a-107">Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного пакета в коллекции в готовящемся выпуске.</span><span class="sxs-lookup"><span data-stu-id="16a4a-107">ScriptAnalyzer results will be displayed on each individual package page in Gallery in the coming release.</span></span> <span data-ttu-id="16a4a-108">Владельцам пакетов рекомендуется проверять опубликованные пакеты на наличие серьезных ошибок.</span><span class="sxs-lookup"><span data-stu-id="16a4a-108">We encourage package owners to check their packages to make sure there are no severe errors in published packages.</span></span>
