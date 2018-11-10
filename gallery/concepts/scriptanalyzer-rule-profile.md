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
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>Профиль правила ScriptAnalyzer для коллекции

Для обеспечения качества пакетов, опубликованных в коллекции PowerShell, запускаются правила [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer), чтобы определить наличие нарушений в отправленных скриптах.

Список правил, выполняемых в ScriptAnalyzer, можно найти на [странице GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).
По любым вопросам, связанным с применяемыми правилами, обращайтесь к администраторам коллекции PowerShell или создайте запрос в поддержку ScriptAnalzyer.

Результаты работы ScriptAnalyzer будут отображаться на каждой странице отдельного пакета в коллекции в готовящемся выпуске. Владельцам пакетов рекомендуется проверять опубликованные пакеты на наличие серьезных ошибок.
