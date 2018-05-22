---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: a3ac215396206fba62bce303733429d60722ee6b
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a>Частоты для RefreshMode и ConfigurationMode не должны быть кратными друг другу

В предыдущей версии DSC локальный диспетчер конфигураций рассматривал `RefreshFrequencyMins` и `ConfigurationModeFrequencyMins` как кратные друг другу. В WMF 5.0 RTM эти свойства обрабатываются независимо друг от друга.

Дополнительные сведения см. в разделе [Настройка локального диспетчера конфигураций](https://msdn.microsoft.com/powershell/dsc/metaconfig).
