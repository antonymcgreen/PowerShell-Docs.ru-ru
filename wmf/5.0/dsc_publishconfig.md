---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: db4543b788ad0a5c7aa32706246446533b901d09
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085819"
---
# <a name="deliver-a-configuration-document-without-applying"></a>Доставка документа конфигурации без применения

Командлет [Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) копирует MOF-файл на целевой узел без применения конфигурации.
Конфигурация применяется во время следующей проверки согласованности или при запуске командлета [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx).
