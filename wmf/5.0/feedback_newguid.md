---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 2d6b4e3045bc8cff90576c345d1ccb97b2487426
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225595"
---
# <a name="new-guid"></a>New-Guid
Часто в сценарии (или при создании ресурсов DSC) требуется уникальный идентификатор. Здесь можно использовать GUID, для создания которых достаточно вызвать класс Guid платформы .NET Framework, однако наличие командлета делает этот процесс более очевидным и удобным для конечных пользователей, которые еще не знакомы с данным классом .NET Framework:

PS C:\\&gt; New-Guid

GUID

----

e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
