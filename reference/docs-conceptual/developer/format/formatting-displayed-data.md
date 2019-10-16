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
ms.openlocfilehash: e915ac71feb50cb58cfa9195f0de94763affdb77
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363703"
---
# <a name="formatting-displayed-data"></a>Форматирование отображаемых данных

Можно указать способ отображения отдельных точек данных в списке, таблице или расширенном представлении. При определении элементов представления можно использовать элемент `FormatString`. также можно использовать элемент `ScriptBlock` для вызова метода `FormatString` для данных.

## <a name="using-the-formatstring-element"></a>Использование элемента FormatString

В следующем примере значение свойства `TotalProcessorTime` объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) форматируется с помощью элемента FormatString. Свойство `TotalProcessorTime`

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```



