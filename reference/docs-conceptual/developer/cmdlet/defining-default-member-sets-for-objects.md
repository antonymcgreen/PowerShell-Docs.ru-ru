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
# <a name="defining-default-member-sets-for-objects"></a>Определение наборов элементов по умолчанию для объектов

Набор элементов Псстандардмемберс используется Windows PowerShell для определения наборов свойств по умолчанию для объекта. Наборы свойств по умолчанию могут использоваться командами, такими как командлеты форматирования для вывода только тех свойств, которые определены в наборе свойств. Наборы свойств по умолчанию включают Дефаултдисплайпроперти, Дефаултдисплайпропертисет и Дефаулткэйпропертисет. Windows PowerShell игнорирует все остальные наборы элементов и другие наборы свойств, добавленные в набор элементов Псстандардмемберс.

## <a name="member-set-for-systemdiagnosticsprocess"></a>Набор элементов для System. Diagnostics. Process

В следующем примере набор элементов Псстандардмемберс определяет свойство Дефаултдисплайпропертисет, заданное для объектов [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) . Этот набор свойств используется командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) .

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

Следующие выходные данные показывают свойства по умолчанию, возвращаемые командлетом [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) . `Id` `Handles` `CPU` `Name` Для каждого объекта процесса возвращаются только свойства,, и.

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
