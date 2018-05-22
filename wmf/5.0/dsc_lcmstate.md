---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: db9b48c188b3bfe2e20c06875606a285922f55a6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="fd5cd-102">Подробные сведения о состоянии LCM</span><span class="sxs-lookup"><span data-stu-id="fd5cd-102">Detailed information about LCM state</span></span>

<span data-ttu-id="fd5cd-103">Мы внесли улучшения процесс предоставления сведений о состоянии LCM.</span><span class="sxs-lookup"><span data-stu-id="fd5cd-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="fd5cd-104">LCMState, возвращаемый Get-DscLocalConfigurationManager, теперь может содержать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fd5cd-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="fd5cd-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="fd5cd-105">**Idle**</span></span>
* <span data-ttu-id="fd5cd-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="fd5cd-106">**Busy**</span></span>
* <span data-ttu-id="fd5cd-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="fd5cd-107">**PendingReboot**</span></span>
* <span data-ttu-id="fd5cd-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="fd5cd-108">**PendingConfiguration**</span></span>

<span data-ttu-id="fd5cd-109">Мы также добавили свойство LCMStateDetail, содержащее дополнительные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="fd5cd-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>
