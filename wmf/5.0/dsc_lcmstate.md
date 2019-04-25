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
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="0c331-102">Подробные сведения о состоянии LCM</span><span class="sxs-lookup"><span data-stu-id="0c331-102">Detailed information about LCM state</span></span>

<span data-ttu-id="0c331-103">Мы внесли улучшения процесс предоставления сведений о состоянии LCM.</span><span class="sxs-lookup"><span data-stu-id="0c331-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="0c331-104">LCMState, возвращаемый Get-DscLocalConfigurationManager, теперь может содержать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0c331-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="0c331-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="0c331-105">**Idle**</span></span>
* <span data-ttu-id="0c331-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="0c331-106">**Busy**</span></span>
* <span data-ttu-id="0c331-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="0c331-107">**PendingReboot**</span></span>
* <span data-ttu-id="0c331-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="0c331-108">**PendingConfiguration**</span></span>

<span data-ttu-id="0c331-109">Мы также добавили свойство LCMStateDetail, содержащее дополнительные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="0c331-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>
