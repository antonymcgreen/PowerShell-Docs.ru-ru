---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Раздел реестра DSCAutomationHostEnabled
ms.openlocfilehash: 0f35a798e5b7d51fdfb66e4e79ceab0e36ccea5b
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808339"
---
# <a name="dscautomationhostenabled-registry-key"></a>Раздел реестра DSCAutomationHostEnabled

> Область применения: Windows PowerShell 5.0

DSC использует раздел реестра **DSCAutomationHostEnabled** в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** для включения конфигурации компьютера при начальной загрузке.
**DSCAutomationHostEnabled** поддерживает три режима:

|  Значение DSCAutomationHostEnabled  |  Описание   |
|---|---|
0 | Отключение настройки компьютера при загрузке системы. |
1 | Включение настройки компьютера при загрузке системы. |
2 | Включение настройки компьютера, только если DSC находится в состоянии ожидания или в текущем состоянии. Это значение по умолчанию. |

## <a name="see-also"></a>См. также:

Пример использования этой функции для запуска конфигураций при начальной загрузке системы см. в разделе [Настройка виртуальных машин при начальной загрузке с помощью DSC](bootstrapDsc.md).
