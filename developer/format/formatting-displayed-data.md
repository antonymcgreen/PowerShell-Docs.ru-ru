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
# <a name="formatting-displayed-data"></a><span data-ttu-id="34a4b-102">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="34a4b-102">Formatting Displayed Data</span></span>

<span data-ttu-id="34a4b-103">Можно указать способ отображения отдельных точках данных списка, таблицы или широкое представление.</span><span class="sxs-lookup"><span data-stu-id="34a4b-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="34a4b-104">Можно использовать `FormatString` элемент при определении элементов представления, или можно использовать `ScriptBlock` элемент для вызова `FormatString` метод данных.</span><span class="sxs-lookup"><span data-stu-id="34a4b-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="34a4b-105">Используя элемент FormatString</span><span class="sxs-lookup"><span data-stu-id="34a4b-105">Using the FormatString Element</span></span>

<span data-ttu-id="34a4b-106">В следующем примере значение из `TotalProcessorTime` свойство [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта имеет формат, используя элемент FormatString.</span><span class="sxs-lookup"><span data-stu-id="34a4b-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="34a4b-107">`TotalProcessorTime` Свойство</span><span class="sxs-lookup"><span data-stu-id="34a4b-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```



