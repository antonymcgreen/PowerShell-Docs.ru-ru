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
# <a name="formatting-displayed-data"></a><span data-ttu-id="4eda3-103">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="4eda3-103">Formatting Displayed Data</span></span>

<span data-ttu-id="4eda3-104">Можно указать способ отображения отдельных точек данных в списке, таблице или расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="4eda3-104">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="4eda3-105">Элемент можно использовать `FormatString` при определении элементов представления, или же элемент можно использовать `ScriptBlock` для вызова `FormatString` метода для данных.</span><span class="sxs-lookup"><span data-stu-id="4eda3-105">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="4eda3-106">Использование элемента FormatString</span><span class="sxs-lookup"><span data-stu-id="4eda3-106">Using the FormatString Element</span></span>

<span data-ttu-id="4eda3-107">В следующем примере значение `TotalProcessorTime` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) форматируется с помощью элемента FormatString.</span><span class="sxs-lookup"><span data-stu-id="4eda3-107">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="4eda3-108">`TotalProcessorTime`свойство</span><span class="sxs-lookup"><span data-stu-id="4eda3-108">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
