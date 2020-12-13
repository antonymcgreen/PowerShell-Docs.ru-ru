---
ms.date: 09/13/2016
ms.topic: reference
title: Пользовательские файлы форматирования
description: Пользовательские файлы форматирования
ms.openlocfilehash: 16e1c1046e25b35ff346585a5fd930c449c04bf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653240"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="8706b-103">Пользовательские файлы форматирования</span><span class="sxs-lookup"><span data-stu-id="8706b-103">Custom Formatting Files</span></span>

<span data-ttu-id="8706b-104">Формат вывода объектов, возвращаемых командлетами, функциями и скриптами, определяется с помощью файлов форматирования (format.ps1XML-файлов).</span><span class="sxs-lookup"><span data-stu-id="8706b-104">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="8706b-105">Некоторые из этих файлов предоставляются Windows PowerShell, чтобы определить формат представления по умолчанию для объектов, возвращаемых командлетами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8706b-105">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="8706b-106">Однако можно также создать собственные файлы форматирования, чтобы перезаписать форматы вывода по умолчанию или определить отображение объектов, возвращаемых собственными командами.</span><span class="sxs-lookup"><span data-stu-id="8706b-106">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="8706b-107">Windows PowerShell использует данные в этих файлах форматирования для определения того, что отображается и как форматируются данные.</span><span class="sxs-lookup"><span data-stu-id="8706b-107">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="8706b-108">Отображаемые данные могут включать свойства объекта или значение блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="8706b-108">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="8706b-109">Блоки сценариев используются, если требуется отобразить какое-либо значение, недоступное непосредственно из свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="8706b-109">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="8706b-110">Например, может потребоваться добавить значение двух свойств объекта и отобразить сумму в виде отдельного фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="8706b-110">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="8706b-111">При написании собственного файла форматирования необходимо определить *представления* для объектов, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="8706b-111">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="8706b-112">Можно определить одно представление для каждого объекта, можно определить одно представление для нескольких объектов или определить несколько представлений для одного и того же объекта.</span><span class="sxs-lookup"><span data-stu-id="8706b-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="8706b-113">Количество представлений, которые можно определить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="8706b-113">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8706b-114">Файлы форматирования не определяют элементы объекта, возвращаемого в конвейер.</span><span class="sxs-lookup"><span data-stu-id="8706b-114">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="8706b-115">При возврате объекта в конвейер все члены этого объекта становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="8706b-115">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="8706b-116">Формат представления</span><span class="sxs-lookup"><span data-stu-id="8706b-116">Format Views</span></span>

<span data-ttu-id="8706b-117">Представления форматирования могут отображать объекты в табличном формате, формате списка, расширенном формате и пользовательском формате.</span><span class="sxs-lookup"><span data-stu-id="8706b-117">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="8706b-118">В большей части каждое определение форматирования описывается набором XML-тегов, описывающих представление.</span><span class="sxs-lookup"><span data-stu-id="8706b-118">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="8706b-119">Каждое представление содержит имя представления, объекты, использующие представление, и элементы представления, такие как сведения о столбцах и строках для табличного представления.</span><span class="sxs-lookup"><span data-stu-id="8706b-119">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="8706b-120">Доступны следующие представления.</span><span class="sxs-lookup"><span data-stu-id="8706b-120">The following views are available.</span></span>

<span data-ttu-id="8706b-121">Табличное представление содержит список свойств объекта или значения блока скрипта в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="8706b-121">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="8706b-122">Каждый столбец представляет свойство объекта или значение блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="8706b-122">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="8706b-123">Можно определить табличное представление, в котором отображаются все свойства объекта, подмножество свойств объекта или сочетание свойств и значений блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="8706b-123">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="8706b-124">Каждая строка таблицы представляет возвращаемый объект.</span><span class="sxs-lookup"><span data-stu-id="8706b-124">Each row of the table represents a returned object.</span></span> <span data-ttu-id="8706b-125">Дополнительные сведения об этом представлении см. в разделе [табличное представление](../format/creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="8706b-125">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="8706b-126">Представление списка содержит свойства объекта или значения блока скрипта в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="8706b-126">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="8706b-127">В каждой строке списка отображается необязательная метка или имя свойства, за которым следует значение свойства или блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="8706b-127">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="8706b-128">Дополнительные сведения об этом представлении см. в разделе [представление списка](../format/creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8706b-128">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="8706b-129">Расширенное представление перечисляет одно свойство объекта или значение блока скрипта в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="8706b-129">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="8706b-130">Для этого представления отсутствует метка или заголовок.</span><span class="sxs-lookup"><span data-stu-id="8706b-130">There is no label or header for this view.</span></span> <span data-ttu-id="8706b-131">Дополнительные сведения об этом представлении см. в разделе [широкие представления](../format/creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="8706b-131">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="8706b-132">Настраиваемое представление отображает настраиваемое представление свойств объекта или значений блока скрипта, которые не соответствуют жестким структурам табличных представлений, представлений списков или расширенных представлений.</span><span class="sxs-lookup"><span data-stu-id="8706b-132">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="8706b-133">Можно определить отдельное пользовательское представление или определить пользовательское представление, используемое другим представлением, например табличное представление или представление списка.</span><span class="sxs-lookup"><span data-stu-id="8706b-133">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="8706b-134">Дополнительные сведения об этом представлении см. в разделе [пользовательское представление](../format/creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8706b-134">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="8706b-135">Просмотр XML-элементов</span><span class="sxs-lookup"><span data-stu-id="8706b-135">View XML Elements</span></span>

<span data-ttu-id="8706b-136">В следующем примере показаны XML-теги, используемые для определения табличного представления, содержащего два столбца.</span><span class="sxs-lookup"><span data-stu-id="8706b-136">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="8706b-137">Элемент [виевдефинитионс](../format/viewdefinitions-element-format.md) является элементом-контейнером для всех представлений, определенных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="8706b-137">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="8706b-138">Элемент [View](../format/view-element-format.md) определяет определенную таблицу, список, широкий или настраиваемое представление.</span><span class="sxs-lookup"><span data-stu-id="8706b-138">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="8706b-139">В каждом представлении элемент [Name](../format/name-element-for-view-format.md) задает имя представления, элемент [виевселектедби](../format/viewselectedby-element-format.md) определяет объекты, использующие представление, а различные элементы управления (такие как `TableControl` элемент) определяют формат представления.</span><span class="sxs-lookup"><span data-stu-id="8706b-139">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

```xml
ViewDefinitions
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="8706b-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="8706b-140">See Also</span></span>

[<span data-ttu-id="8706b-141">Табличное представление</span><span class="sxs-lookup"><span data-stu-id="8706b-141">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="8706b-142">Представление списка</span><span class="sxs-lookup"><span data-stu-id="8706b-142">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="8706b-143">Расширенное представление</span><span class="sxs-lookup"><span data-stu-id="8706b-143">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="8706b-144">Пользовательское представление</span><span class="sxs-lookup"><span data-stu-id="8706b-144">Custom View</span></span>](../format/creating-custom-controls.md)

[<span data-ttu-id="8706b-145">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8706b-145">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
