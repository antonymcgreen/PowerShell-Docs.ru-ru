---
title: Форматирование отображаемых данных | Документация Майкрософт
ms.date: 09/12/2016
ms.openlocfilehash: 97d23b3079b2779e518b6b6d2f2ac0c5e9d1f3a3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781517"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="4f456-102">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="4f456-102">Formatting Displayed Data</span></span>

<span data-ttu-id="4f456-103">Можно указать способ отображения отдельных точек данных в списке, таблице или расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="4f456-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="4f456-104">Элемент можно использовать `FormatString` при определении элементов представления, или же элемент можно использовать `ScriptBlock` для вызова `FormatString` метода для данных.</span><span class="sxs-lookup"><span data-stu-id="4f456-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="4f456-105">Использование элемента FormatString</span><span class="sxs-lookup"><span data-stu-id="4f456-105">Using the FormatString Element</span></span>

<span data-ttu-id="4f456-106">В следующем примере значение `TotalProcessorTime` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) форматируется с помощью элемента FormatString.</span><span class="sxs-lookup"><span data-stu-id="4f456-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="4f456-107">`TotalProcessorTime`свойство</span><span class="sxs-lookup"><span data-stu-id="4f456-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
