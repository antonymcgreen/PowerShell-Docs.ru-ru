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
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>Профиль правила ScriptAnalyzer для коллекции

Для обеспечения качества пакетов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие нарушений в отправленных скриптах.

Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).
По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalyzer.

Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного пакета в коллекции в готовящемся выпуске. Владельцам пакетов рекомендуется проверять опубликованные пакеты на наличие серьезных ошибок.
