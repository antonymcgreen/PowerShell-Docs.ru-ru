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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065671"
---
# <a name="formatting-displayed-data"></a>Форматирование отображаемых данных

Можно указать способ отображения отдельных точках данных списка, таблицы или широкое представление. Можно использовать `FormatString` элемент при определении элементов представления, или можно использовать `ScriptBlock` элемент для вызова `FormatString` метод данных.

## <a name="using-the-formatstring-element"></a>Используя элемент FormatString

В следующем примере значение из `TotalProcessorTime` свойство [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта имеет формат, используя элемент FormatString. `TotalProcessorTime` Свойство

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```



