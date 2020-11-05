---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Раздел реестра DSCAutomationHostEnabled
description: В этой статье определены значения, которые можно задать в разделе реестра DSCAutomationHostEnabled.
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656178"
---
# <a name="dscautomationhostenabled-registry-key"></a>Раздел реестра DSCAutomationHostEnabled

> Область применения: Windows PowerShell 5.0

DSC использует раздел реестра **DSCAutomationHostEnabled** в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** для включения конфигурации компьютера при начальной загрузке. **DSCAutomationHostEnabled** поддерживает три режима:

| Значение DSCAutomationHostEnabled |                                              Описание                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| 0                              | Отключение настройки компьютера при загрузке системы.                                                           |
| 1                              | Включение настройки компьютера при загрузке системы.                                                            |
| 2                              | Включение настройки компьютера, только если DSC находится в состоянии ожидания или в текущем состоянии. Это значение по умолчанию. |

## <a name="see-also"></a>См. также:

Пример использования этой функции для запуска конфигураций при начальной загрузке системы см. в разделе [Настройка виртуальных машин при начальной загрузке с помощью DSC](bootstrapDsc.md).
