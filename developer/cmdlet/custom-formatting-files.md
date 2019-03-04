---
title: Настраиваемое форматирование файлов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85d27545-8097-4010-9947-6d8b3ce2eac0
caps.latest.revision: 15
ms.openlocfilehash: 71c1c181058c5646c817b90d9832976a78c6c7de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860610"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="2d6e6-102">Пользовательские файлы форматирования</span><span class="sxs-lookup"><span data-stu-id="2d6e6-102">Custom Formatting Files</span></span>

<span data-ttu-id="2d6e6-103">Формат отображения для объектов, возвращенных командлеты, функции и сценарии определяются с помощью форматирования (файлы format.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="2d6e6-103">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="2d6e6-104">Некоторые из этих файлов предоставляются Windows PowerShell, чтобы определить формат отображения по умолчанию для этих объектов, возвращаемых командлетами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-104">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2d6e6-105">Тем не менее можно также создать собственные пользовательские файлы форматирования для перезаписи форматы отображения по умолчанию или для определения отображения объектов, возвращенных собственные команды.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-105">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="2d6e6-106">Windows PowerShell использует данные в эти файлы форматирования для определения отображаемых и форматирование данных.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-106">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="2d6e6-107">Отображаемые данные могут включать, свойства объекта или значение блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-107">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="2d6e6-108">Блоки сценариев используются в том случае, если вы хотите отобразить некое значение, не доступны непосредственно из окна свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-108">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="2d6e6-109">Например можно добавить значения двух свойств объекта и отобразить сумму как отдельный фрагмент данных.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-109">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="2d6e6-110">При написании собственного форматирования файла, необходимо определить *представления* для объектов, которые вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-110">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="2d6e6-111">Можно определить одно представление для каждого объекта, можно определить одно представление для нескольких объектов или вы можете определить несколько представлений для одного объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-111">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="2d6e6-112">Нет ограничений на количество представлений, которые можно определить.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-112">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d6e6-113">Файлы форматирования, не определяют элементы объекта, которые возвращаются в конвейер.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-113">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="2d6e6-114">Когда объект возвращается в конвейер, доступны всем членам этого объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-114">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="2d6e6-115">Формат представления</span><span class="sxs-lookup"><span data-stu-id="2d6e6-115">Format Views</span></span>

<span data-ttu-id="2d6e6-116">Форматирования представлений можно отображать объекты в табличном формате, формате списка, расширенном формате и пользовательский формат.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-116">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="2d6e6-117">В большинстве случаев каждое определение форматирования описывается набор XML-теги, которые описывают представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-117">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="2d6e6-118">Каждое представление содержит имя представления, объекты, используемые представления и элементы представления, такие как данные столбцов и строк для таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-118">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="2d6e6-119">Доступны следующие представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-119">The following views are available.</span></span>

<span data-ttu-id="2d6e6-120">Представление таблицы представлены свойства объекта или значение блока скрипта в один или несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-120">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="2d6e6-121">Каждый столбец представляет свойства объекта или значение блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-121">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="2d6e6-122">Можно определить представление таблицы, которое отображает все свойства объекта, подмножество свойств объекта или комбинации свойств и значений блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-122">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="2d6e6-123">Каждая строка таблицы представляет возвращаемый объект.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-123">Each row of the table represents a returned object.</span></span> <span data-ttu-id="2d6e6-124">Дополнительные сведения об этом представлении см. в разделе [табличное представление](../format/creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e6-124">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="2d6e6-125">Представление списка перечислены свойства объекта или значение блока скрипта в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-125">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="2d6e6-126">Каждая строка списка отображает необязательную метку или имя свойства, за которым следует значение свойства или скрипт блока.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-126">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="2d6e6-127">Дополнительные сведения об этом представлении см. в разделе [представление списка](../format/creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e6-127">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="2d6e6-128">Широкое представление перечислены одиночному свойству объекта или значение блока скрипта в один или несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-128">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="2d6e6-129">Нет, метка или заголовок для этого представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-129">There is no label or header for this view.</span></span> <span data-ttu-id="2d6e6-130">Дополнительные сведения об этом представлении см. в разделе [широкое представление](../format/creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e6-130">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="2d6e6-131">Пользовательское представление Отображение настраиваемых свойств объектов или значений блок скрипта, не соответствует структуре жесткой представления таблицы, списки или широкие представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-131">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="2d6e6-132">Можно определить автономного представления, или можно определить пользовательское представление, которое используется другое представление, например представление таблицы или представления списка.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-132">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="2d6e6-133">Дополнительные сведения об этом представлении см. в разделе [пользовательское представление](../format/creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e6-133">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="2d6e6-134">Представление XML-элементов</span><span class="sxs-lookup"><span data-stu-id="2d6e6-134">View XML Elements</span></span>

<span data-ttu-id="2d6e6-135">В следующем примере показано XML-теги, используемые для определения представления таблицы, содержащий два столбца.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-135">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="2d6e6-136">[ViewDefinitions](../format/viewdefinitions-element-format.md) элементом является элемент-контейнер для всех представлений, определенных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-136">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="2d6e6-137">[Представление](../format/view-element-format.md) элемент определяет конкретную таблицу, список, ширину, или в пользовательские представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-137">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="2d6e6-138">В каждом представлении [имя](../format/name-element-for-view-format.md) элемент задает имя представления, [ViewSelectedBy](../format/viewselectedby-element-format.md) элемент определяет объекты, используемые представления и элементы другой элемент управления (такие как `TableControl` элемент) определяют формат представления.</span><span class="sxs-lookup"><span data-stu-id="2d6e6-138">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2d6e6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2d6e6-139">See Also</span></span>

[<span data-ttu-id="2d6e6-140">Табличное представление</span><span class="sxs-lookup"><span data-stu-id="2d6e6-140">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="2d6e6-141">Представление списка</span><span class="sxs-lookup"><span data-stu-id="2d6e6-141">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="2d6e6-142">Широкое представление</span><span class="sxs-lookup"><span data-stu-id="2d6e6-142">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="2d6e6-143">Пользовательское представление</span><span class="sxs-lookup"><span data-stu-id="2d6e6-143">Custom View</span></span>](../format/creating-custom-controls.md)

[<span data-ttu-id="2d6e6-144">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d6e6-144">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
