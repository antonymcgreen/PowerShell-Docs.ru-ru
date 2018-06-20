---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 6d37fbc5091d69925d60349f3acbdecc92da1b95
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34220348"
---
# <a name="on-demand-pull-of-dsc-configurations"></a>Извлечение по запросу для конфигураций DSC

Новый командлет Update-DscConfiguration активирует извлечение с опрашивающих серверов, определенных в метаконфигурации. Такое поведение часто называется "оперативным извлечением".


После активации извлечение осуществляется точно так же, как и в обычном случае:

1. Контрольная сумма для текущей конфигурации сравнивается с контрольной суммой конфигурации на опрашивающем сервере.
2. Если они совпадают, процедура завершается успешно без применения конфигурации.
3. Если они различаются, конфигурация извлекается с опрашивающего сервера и применяется.

**Примечание.** Если Meta-Configuration RefreshMode = "Push", этот командлет возвращает ошибку, поэтому он всегда не выполняет никаких действий, когда целевой узел находится в режиме Push.

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
