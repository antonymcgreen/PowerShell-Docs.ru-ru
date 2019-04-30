---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 90fd26f9f27d2398da839b309c17b921bb3b8521
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085332"
---
# <a name="new-guid"></a>New-Guid
Часто в сценарии (или при создании ресурсов DSC) требуется уникальный идентификатор. Здесь можно использовать GUID, для создания которых достаточно вызвать класс Guid платформы .NET Framework, однако наличие командлета делает этот процесс более очевидным и удобным для конечных пользователей, которые еще не знакомы с данным классом .NET Framework:

PS C:\\&gt; New-Guid

GUID

----

e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
