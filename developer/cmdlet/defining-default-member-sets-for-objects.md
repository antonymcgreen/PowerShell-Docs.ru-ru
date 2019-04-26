---
title: Определение элемента по умолчанию устанавливает для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068255"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="72da9-102">Определение наборов элементов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="72da9-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="72da9-103">Набор элементов PSStandardMembers используется Windows PowerShell для определения наборов свойств по умолчанию для объекта.</span><span class="sxs-lookup"><span data-stu-id="72da9-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="72da9-104">Наборы свойств по умолчанию может использоваться таких командлетов форматирования команд для отображения только этих свойств, которые определяются в набор свойств.</span><span class="sxs-lookup"><span data-stu-id="72da9-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="72da9-105">Наборы свойств по умолчанию включают DefaultDisplayProperty DefaultDisplayPropertySet и DefaultKeyPropertySet.</span><span class="sxs-lookup"><span data-stu-id="72da9-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="72da9-106">Windows PowerShell игнорирует все остальные наборы элементов и других наборов свойств, добавляемый в набор элементов PSStandardMembers.</span><span class="sxs-lookup"><span data-stu-id="72da9-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="72da9-107">Набор элементов для System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="72da9-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="72da9-108">В следующем примере набор элементов PSStandardMembers определяет набор свойств DefaultDisplayPropertySet [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объектов.</span><span class="sxs-lookup"><span data-stu-id="72da9-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="72da9-109">Если это свойство задано, используется [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета.</span><span class="sxs-lookup"><span data-stu-id="72da9-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="72da9-110">В следующем примере вывод свойства по умолчанию, возвращенный [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета.</span><span class="sxs-lookup"><span data-stu-id="72da9-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="72da9-111">Только `Id`, `Handles`, `CPU`, и `Name` свойства, возвращаемые для каждого объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="72da9-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72da9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="72da9-112">See Also</span></span>

[<span data-ttu-id="72da9-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72da9-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
