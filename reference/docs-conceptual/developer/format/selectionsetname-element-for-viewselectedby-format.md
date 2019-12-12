---
title: Элемент Селектионсетнаме для Виевселектедби (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368263"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="b7187-102">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b7187-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="b7187-103">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="b7187-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="b7187-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби элемент (Format) Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b7187-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7187-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7187-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7187-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7187-106">Attributes and Elements</span></span>

<span data-ttu-id="b7187-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="b7187-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7187-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7187-108">Attributes</span></span>

<span data-ttu-id="b7187-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="b7187-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7187-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7187-110">Child Elements</span></span>

<span data-ttu-id="b7187-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b7187-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7187-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7187-112">Parent Elements</span></span>

|<span data-ttu-id="b7187-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7187-113">Element</span></span>|<span data-ttu-id="b7187-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b7187-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b7187-115">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b7187-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="b7187-116">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="b7187-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b7187-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b7187-117">Text Value</span></span>

<span data-ttu-id="b7187-118">Укажите имя набора выбора, который определяется элементом `Name` для набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b7187-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7187-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="b7187-119">Remarks</span></span>

<span data-ttu-id="b7187-120">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="b7187-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="b7187-121">Дополнительные сведения об определении и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b7187-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b7187-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b7187-122">Example</span></span>

<span data-ttu-id="b7187-123">В следующем примере показано, как задать набор выбора для представления списка.</span><span class="sxs-lookup"><span data-stu-id="b7187-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="b7187-124">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="b7187-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="b7187-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7187-125">See Also</span></span>

[<span data-ttu-id="b7187-126">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="b7187-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b7187-127">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b7187-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="b7187-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7187-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
