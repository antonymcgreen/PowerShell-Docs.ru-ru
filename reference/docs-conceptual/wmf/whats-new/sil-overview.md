---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Инвентаризация программного обеспечения (SIL)
ms.openlocfilehash: b12cfc4ae1e505bbc4d47596bed9352ce53a98f2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71147784"
---
# <a name="software-inventory-logging-sil"></a>Инвентаризация программного обеспечения (SIL)

> [!IMPORTANT]
> При установке WMF 5.x на сервере Windows Server 2012 R2, где уже выполняется SIL, необходимо один раз запустить командлет Start-SilLogging после установки WMF, так как процесс установки ошибочно остановит функцию инвентаризации программного обеспечения.

Инвентаризация программного обеспечения помогает сократить эксплуатационные расходы на получение точной информации о программном обеспечении Майкрософт, локально установленном на сервере, особенно на множестве серверов в ИТ-среде (при условии, что ПО установлено и работает в ИТ-среде). После настройки этого компонента вы можете перенаправлять эти данные на сервер агрегирования и собирать данные журналов в одном месте с помощью универсальной автоматической процедуры.

Несмотря на то, что данные об инвентаризации можно собрать путем прямого запроса каждого из компьютеров, инвентаризация программного обеспечения при использовании архитектуры перенаправления (по сети), запускаемой на каждом сервере, позволяет устранить множество серверов с обнаружением компьютеров, типичных для многих сценариев инвентаризации программного обеспечения и управления ресурсами. Инвентаризация программного обеспечения использует SSL для защиты данных, передаваемых на сервер агрегирования по протоколу HTTPS. Хранение всех данных в одном месте упрощает их анализ, совместное использование и обработку.

Ни один фрагмент этих данных не передается в корпорацию Майкрософт в процессе работы компонента. Компонент ведения журнала инвентаризации программного обеспечения и предоставляемые им функции предназначены исключительно для использования владельцем и администраторами лицензированного серверного программного обеспечения.

Подробные сведения и документацию о командлетах для инвентаризации программного обеспечения см. в статье [Manage Software Inventory Logging in Windows Server 2012 R2](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383584(v=ws.11)) (Управление инвентаризацией программного обеспечения в Windows Server 2012 R2).