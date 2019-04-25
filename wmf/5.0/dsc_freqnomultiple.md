---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 23a5c8832f7c2888880a1ee846d75feaa95ebe47
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058409"
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a><span data-ttu-id="73695-102">Частоты для RefreshMode и ConfigurationMode не должны быть кратными друг другу</span><span class="sxs-lookup"><span data-stu-id="73695-102">Frequencies for RefreshMode and ConfigurationMode don't need to be multiples of each other</span></span>

<span data-ttu-id="73695-103">В предыдущей версии DSC локальный диспетчер конфигураций рассматривал `RefreshFrequencyMins` и `ConfigurationModeFrequencyMins` как кратные друг другу.</span><span class="sxs-lookup"><span data-stu-id="73695-103">In the previous version of DSC, the LCM would treat `RefreshFrequencyMins` and `ConfigurationModeFrequencyMins` as multiples of each other.</span></span> <span data-ttu-id="73695-104">В WMF 5.0 RTM эти свойства обрабатываются независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="73695-104">In WMF 5.0 RTM, these properties are processed independent of each other.</span></span>

<span data-ttu-id="73695-105">Дополнительные сведения см. в разделе [Настройка локального диспетчера конфигураций](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span><span class="sxs-lookup"><span data-stu-id="73695-105">For more information, see [Configuring the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span></span>
