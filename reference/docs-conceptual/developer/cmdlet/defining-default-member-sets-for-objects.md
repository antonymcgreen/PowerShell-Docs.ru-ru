---
ms.date: 09/13/2016
ms.topic: reference
title: Определение наборов элементов по умолчанию для объектов
description: Определение наборов элементов по умолчанию для объектов
ms.openlocfilehash: 919f7ba65322c6a56a27e046fb211bde151abf7d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653118"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="9cc28-103">Определение наборов элементов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="9cc28-103">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="9cc28-104">Набор элементов Псстандардмемберс используется Windows PowerShell для определения наборов свойств по умолчанию для объекта.</span><span class="sxs-lookup"><span data-stu-id="9cc28-104">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="9cc28-105">Наборы свойств по умолчанию могут использоваться командами, такими как командлеты форматирования для вывода только тех свойств, которые определены в наборе свойств.</span><span class="sxs-lookup"><span data-stu-id="9cc28-105">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="9cc28-106">Наборы свойств по умолчанию включают Дефаултдисплайпроперти, Дефаултдисплайпропертисет и Дефаулткэйпропертисет.</span><span class="sxs-lookup"><span data-stu-id="9cc28-106">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="9cc28-107">Windows PowerShell игнорирует все остальные наборы элементов и другие наборы свойств, добавленные в набор элементов Псстандардмемберс.</span><span class="sxs-lookup"><span data-stu-id="9cc28-107">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="9cc28-108">Набор элементов для System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="9cc28-108">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="9cc28-109">В следующем примере набор элементов Псстандардмемберс определяет свойство Дефаултдисплайпропертисет, заданное для объектов [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="9cc28-109">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="9cc28-110">Этот набор свойств используется командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="9cc28-110">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

<span data-ttu-id="9cc28-111">Следующие выходные данные показывают свойства по умолчанию, возвращаемые командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="9cc28-111">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="9cc28-112">`Id` `Handles` `CPU` `Name` Для каждого объекта процесса возвращаются только свойства,, и.</span><span class="sxs-lookup"><span data-stu-id="9cc28-112">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a><span data-ttu-id="9cc28-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9cc28-113">See Also</span></span>

[<span data-ttu-id="9cc28-114">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cc28-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
