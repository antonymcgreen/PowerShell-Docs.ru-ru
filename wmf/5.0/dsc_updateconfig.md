---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 31fde15e644455dbe77f68bca713bf026544fdc7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057576"
---
# <a name="on-demand-pull-of-dsc-configurations"></a><span data-ttu-id="bb1c8-102">Извлечение по запросу для конфигураций DSC</span><span class="sxs-lookup"><span data-stu-id="bb1c8-102">On-demand PULL of DSC Configurations</span></span>

<span data-ttu-id="bb1c8-103">Новый командлет Update-DscConfiguration активирует извлечение с опрашивающих серверов, определенных в метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="bb1c8-103">The new Update-DscConfiguration cmdlet triggers a pull from the pull server(s) defined in the meta-configuration.</span></span> <span data-ttu-id="bb1c8-104">Такое поведение часто называется "оперативным извлечением".</span><span class="sxs-lookup"><span data-stu-id="bb1c8-104">The behavior is often referred to as 'Pull Now'.</span></span>


<span data-ttu-id="bb1c8-105">После активации извлечение осуществляется точно так же, как и в обычном случае:</span><span class="sxs-lookup"><span data-stu-id="bb1c8-105">Once triggered, the pull behaves exactly the same as it would have when triggered during the regular frequency:</span></span>

1. <span data-ttu-id="bb1c8-106">Контрольная сумма для текущей конфигурации сравнивается с контрольной суммой конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="bb1c8-106">The checksum for current configuration is compared to the checksum for the configuration on the pull server.</span></span>
2. <span data-ttu-id="bb1c8-107">Если они совпадают, процедура завершается успешно без применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bb1c8-107">If they are the same, it completes successfully without applying the configuration.</span></span>
3. <span data-ttu-id="bb1c8-108">Если они различаются, конфигурация извлекается с опрашивающего сервера и применяется.</span><span class="sxs-lookup"><span data-stu-id="bb1c8-108">If they are different, the configuration is pulled down from the pull server and applied.</span></span>

<span data-ttu-id="bb1c8-109">**Примечание**. Если Meta-Configuration RefreshMode = "Push", этот командлет возвращает ошибку, поэтому он не выполняет никаких действий, когда целевой узел находится в режиме Push.</span><span class="sxs-lookup"><span data-stu-id="bb1c8-109">**Note:** If the Meta-Configuration RefreshMode = 'Push' an error is returned by this cmdlet so this cmdlet will always do nothing when a target node is in 'Push' Mode.</span></span>

```powershell
Update-DscConfiguration     [[-ComputerName] <string[]>]
                            [-Wait]
                            [-Force]
                            [-JobName <string>]
                            [-Credential<pscredential>]
                            [-ThrottleLimit <int>]
                            [-WhatIf]
                            [-Confirm]
                            [<CommonParameters>]

Update-DscConfiguration     -CimSession <CimSession[]>
                            [-Wait]
                            [-Force]
                            [-JobName <string>]
                            [-ThrottleLimit <int>]
                            [-WhatIf]
                            [-Confirm]
                            [<CommonParameters>]
```
