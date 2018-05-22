---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: f929ce4684bb53c3039238ecd465f1c0e432f741
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="deliver-a-configuration-document-without-applying"></a>Доставка документа конфигурации без применения

Командлет [Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) копирует MOF-файл на целевой узел без применения конфигурации.
Конфигурация применяется во время следующей проверки согласованности или при запуске командлета [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx).
