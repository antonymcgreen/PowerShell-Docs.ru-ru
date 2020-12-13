---
ms.date: 09/12/2016
ms.topic: reference
title: Форматирование отображаемых данных
description: Форматирование отображаемых данных
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667867"
---
# <a name="formatting-displayed-data"></a>Форматирование отображаемых данных

Можно указать способ отображения отдельных точек данных в списке, таблице или расширенном представлении. Элемент можно использовать `FormatString` при определении элементов представления, или же элемент можно использовать `ScriptBlock` для вызова `FormatString` метода для данных.

## <a name="using-the-formatstring-element"></a>Использование элемента FormatString

В следующем примере значение `TotalProcessorTime` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) форматируется с помощью элемента FormatString. `TotalProcessorTime`свойство

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
