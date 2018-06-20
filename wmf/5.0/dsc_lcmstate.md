---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: db9b48c188b3bfe2e20c06875606a285922f55a6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219867"
---
# <a name="detailed-information-about-lcm-state"></a>Подробные сведения о состоянии LCM

Мы внесли улучшения процесс предоставления сведений о состоянии LCM. LCMState, возвращаемый Get-DscLocalConfigurationManager, теперь может содержать следующие значения:

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

Мы также добавили свойство LCMStateDetail, содержащее дополнительные сведения о состоянии.
