---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 10f8dd0f5097260eb4a8516f9662df3d219bdfe5
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34187567"
---
# <a name="test-dscconfiguration-cmdlet-supports-reference-configurations"></a><span data-ttu-id="11506-102">Командлет Test-DscConfiguration поддерживает проектные конфигурации</span><span class="sxs-lookup"><span data-stu-id="11506-102">Test-DscConfiguration cmdlet supports Reference Configurations</span></span>

<span data-ttu-id="11506-103">Командлет Test-DscConfiguration был обновлен, чтобы обеспечить тестирование требуемого состояния конфигурации для одного или нескольких целевых узлов путем указания документа проектной конфигурации для сравнения.</span><span class="sxs-lookup"><span data-stu-id="11506-103">The Test-DscConfiguration cmdlet has been updated to allow testing of desired configuration state of one or more target nodes by specifying a reference configuration document to compare against.</span></span>

<span data-ttu-id="11506-104">Приведенные ниже новые наборы параметров используют конфигурации DSC по указанному пути только для тестирования и никогда не применяют их к указанным целевым узлам.</span><span class="sxs-lookup"><span data-stu-id="11506-104">The following new parameter sets use DSC configurations in the path specified to only test and never apply each configuration on the specified target node(s).</span></span> <span data-ttu-id="11506-105">Как и в случае с Start-DscConfiguration и другими командлетами DSC, имя каждого MOF-файла позволяет определить, для какого целевого узла требуется протестировать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="11506-105">As with Start-DscConfiguration and other DSC cmdlets, the name of each MOF is used to determine which target node to test the configuration on.</span></span>

```powershell
Test-DscConfiguration   [-Path] <string>
                        [[-ComputerName] <string[]>]
                        [-Credential <pscredential>]
                        [-ThrottleLimit <int>]
                        [-AsJob]
                        [<CommonParameters>]

Test-DscConfiguration   [-Path] <string>
                        -CimSession <CimSession[]>
                        [-ThrottleLimit <int>]
                        [-AsJob]
                        [<CommonParameters>]
```

<span data-ttu-id="11506-106">Приведенные ниже новые наборы параметров используют отдельную конфигурацию DSC только для тестирования и никогда не применяют ее к указанным целевым узлам.</span><span class="sxs-lookup"><span data-stu-id="11506-106">The following new parameter sets use a single DSC configuration to only test and never apply the configuration on the specified target node(s).</span></span>

```powershell
Test-DscConfiguration   -ReferenceConfiguration <string>
                        [[-ComputerName] <string[]>]
                        [-Credential <pscredential>]
                        [-ThrottleLimit <int>]
                        [-AsJob]
                        [<CommonParameters>]

Test-DscConfiguration   -ReferenceConfiguration <string>
                        -CimSession <CimSession[]>
                        [-ThrottleLimit <int>]
                        [-AsJob]
                        [<CommonParameters>]
```
