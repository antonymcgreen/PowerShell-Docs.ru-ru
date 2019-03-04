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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854990"
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



