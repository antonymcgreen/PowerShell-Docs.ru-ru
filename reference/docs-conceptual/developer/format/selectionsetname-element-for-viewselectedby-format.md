---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента ViewSelectedBy (формат)
description: Элемент SelectionSetName для элемента ViewSelectedBy (формат)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654903"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="4e714-103">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4e714-103">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="4e714-104">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="4e714-104">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="4e714-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби элемент (Format) Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="4e714-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e714-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e714-106">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e714-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e714-107">Attributes and Elements</span></span>

<span data-ttu-id="4e714-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="4e714-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e714-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e714-109">Attributes</span></span>

<span data-ttu-id="4e714-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e714-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e714-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e714-111">Child Elements</span></span>

<span data-ttu-id="4e714-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e714-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4e714-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e714-113">Parent Elements</span></span>

|<span data-ttu-id="4e714-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e714-114">Element</span></span>|<span data-ttu-id="4e714-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4e714-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e714-116">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4e714-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="4e714-117">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="4e714-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4e714-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4e714-118">Text Value</span></span>

<span data-ttu-id="4e714-119">Укажите имя набора выбора, который определяется `Name` элементом для набора выбора.</span><span class="sxs-lookup"><span data-stu-id="4e714-119">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e714-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e714-120">Remarks</span></span>

<span data-ttu-id="4e714-121">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="4e714-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="4e714-122">Дополнительные сведения об определении и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="4e714-122">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="4e714-123">Пример</span><span class="sxs-lookup"><span data-stu-id="4e714-123">Example</span></span>

<span data-ttu-id="4e714-124">В следующем примере показано, как задать набор выбора для представления списка.</span><span class="sxs-lookup"><span data-stu-id="4e714-124">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="4e714-125">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="4e714-125">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="4e714-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e714-126">See Also</span></span>

[<span data-ttu-id="4e714-127">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="4e714-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="4e714-128">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4e714-128">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="4e714-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e714-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
