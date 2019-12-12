---
title: Определение наборов элементов по умолчанию для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369783"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="22767-102">Определение наборов элементов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="22767-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="22767-103">Набор элементов Псстандардмемберс используется Windows PowerShell для определения наборов свойств по умолчанию для объекта.</span><span class="sxs-lookup"><span data-stu-id="22767-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="22767-104">Наборы свойств по умолчанию могут использоваться командами, такими как командлеты форматирования для вывода только тех свойств, которые определены в наборе свойств.</span><span class="sxs-lookup"><span data-stu-id="22767-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="22767-105">Наборы свойств по умолчанию включают Дефаултдисплайпроперти, Дефаултдисплайпропертисет и Дефаулткэйпропертисет.</span><span class="sxs-lookup"><span data-stu-id="22767-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="22767-106">Windows PowerShell игнорирует все остальные наборы элементов и другие наборы свойств, добавленные в набор элементов Псстандардмемберс.</span><span class="sxs-lookup"><span data-stu-id="22767-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="22767-107">Набор элементов для System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="22767-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="22767-108">В следующем примере набор элементов Псстандардмемберс определяет свойство Дефаултдисплайпропертисет, заданное для объектов [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="22767-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="22767-109">Этот набор свойств используется командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="22767-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="22767-110">Следующие выходные данные показывают свойства по умолчанию, возвращаемые командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .</span><span class="sxs-lookup"><span data-stu-id="22767-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="22767-111">Для каждого объекта процесса возвращаются только свойства `Id`, `Handles`, `CPU`и `Name`.</span><span class="sxs-lookup"><span data-stu-id="22767-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="22767-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="22767-112">See Also</span></span>

[<span data-ttu-id="22767-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22767-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
