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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368263"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="97913-102">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="97913-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="97913-103">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="97913-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="97913-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби элемент (Format) Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="97913-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97913-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97913-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97913-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97913-106">Attributes and Elements</span></span>

<span data-ttu-id="97913-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="97913-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="97913-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97913-108">Attributes</span></span>

<span data-ttu-id="97913-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="97913-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97913-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97913-110">Child Elements</span></span>

<span data-ttu-id="97913-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="97913-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="97913-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97913-112">Parent Elements</span></span>

|<span data-ttu-id="97913-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="97913-113">Element</span></span>|<span data-ttu-id="97913-114">Описание</span><span class="sxs-lookup"><span data-stu-id="97913-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97913-115">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="97913-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="97913-116">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="97913-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="97913-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="97913-117">Text Value</span></span>

<span data-ttu-id="97913-118">Укажите имя набора выбора, который определяется элементом `Name` для набора выбора.</span><span class="sxs-lookup"><span data-stu-id="97913-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="97913-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="97913-119">Remarks</span></span>

<span data-ttu-id="97913-120">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="97913-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="97913-121">Дополнительные сведения об определении и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="97913-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="97913-122">Пример</span><span class="sxs-lookup"><span data-stu-id="97913-122">Example</span></span>

<span data-ttu-id="97913-123">В следующем примере показано, как задать набор выбора для представления списка.</span><span class="sxs-lookup"><span data-stu-id="97913-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="97913-124">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="97913-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="97913-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="97913-125">See Also</span></span>

[<span data-ttu-id="97913-126">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="97913-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="97913-127">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="97913-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="97913-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="97913-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
