---
title: Форматирование отображаемых данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38971643-2a3d-4f5b-a1fa-6334c162b8ed
caps.latest.revision: 4
ms.openlocfilehash: 9f3a3176ae16ac7c014cadce6b4e856f9bd3b5da
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560395"
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
