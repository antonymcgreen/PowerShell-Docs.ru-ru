---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085802"
---
# <a name="detailed-information-about-lcm-state"></a>Подробные сведения о состоянии LCM

Мы внесли улучшения процесс предоставления сведений о состоянии LCM. LCMState, возвращаемый Get-DscLocalConfigurationManager, теперь может содержать следующие значения:

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

Мы также добавили свойство LCMStateDetail, содержащее дополнительные сведения о состоянии.
