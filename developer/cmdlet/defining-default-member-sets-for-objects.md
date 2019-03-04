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
ms.openlocfilehash: e8185eb7221a3be0445eddc537dbca89478c74f2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859800"
---
# <a name="defining-default-member-sets-for-objects"></a>Определение наборов элементов по умолчанию для объектов

Набор элементов PSStandardMembers используется Windows PowerShell для определения наборов свойств по умолчанию для объекта. Наборы свойств по умолчанию может использоваться таких командлетов форматирования команд для отображения только этих свойств, которые определяются в набор свойств. Наборы свойств по умолчанию включают DefaultDisplayProperty DefaultDisplayPropertySet и DefaultKeyPropertySet. Windows PowerShell игнорирует все остальные наборы элементов и других наборов свойств, добавляемый в набор элементов PSStandardMembers.

## <a name="member-set-for-systemdiagnosticsprocess"></a>Набор элементов для System.Diagnostics.Process

В следующем примере набор элементов PSStandardMembers определяет набор свойств DefaultDisplayPropertySet [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объектов. Если это свойство задано, используется [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета.
В следующем примере набор элементов PSStandardMembers определяет набор свойств DefaultDisplayPropertySet [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объектов. Если это свойство задано, используется [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета.

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

В следующем примере вывод свойства по умолчанию, возвращенный [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета. Только `Id`, `Handles`, `CPU`, и `Name` свойства, возвращаемые для каждого объекта процесса.
В следующем примере вывод свойства по умолчанию, возвращенный [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) командлета. Только `Id`, `Handles`, `CPU`, и `Name` свойства, возвращаемые для каждого объекта процесса.

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
