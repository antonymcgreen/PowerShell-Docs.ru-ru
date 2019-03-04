---
title: Элемент SelectionSetName для ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858340"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="5f0fd-102">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5f0fd-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="5f0fd-103">Задает набор объектов .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="5f0fd-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент ViewSelectedBy (формат) SelectionSetName элемент конфигурации для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5f0fd-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f0fd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f0fd-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5f0fd-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5f0fd-106">Attributes and Elements</span></span>

<span data-ttu-id="5f0fd-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f0fd-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f0fd-108">Attributes</span></span>

<span data-ttu-id="5f0fd-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f0fd-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f0fd-110">Child Elements</span></span>

<span data-ttu-id="5f0fd-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5f0fd-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f0fd-112">Parent Elements</span></span>

|<span data-ttu-id="5f0fd-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f0fd-113">Element</span></span>|<span data-ttu-id="5f0fd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5f0fd-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f0fd-115">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5f0fd-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="5f0fd-116">Определяет объекты .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5f0fd-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="5f0fd-117">Text Value</span></span>

<span data-ttu-id="5f0fd-118">Укажите имя набора, который определяется `Name` элемент набора выбора.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f0fd-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="5f0fd-119">Remarks</span></span>

<span data-ttu-id="5f0fd-120">Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="5f0fd-121">Дополнительные сведения об определении и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5f0fd-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="5f0fd-122">Пример</span><span class="sxs-lookup"><span data-stu-id="5f0fd-122">Example</span></span>

<span data-ttu-id="5f0fd-123">В следующем примере показано задание выбора представления списка.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="5f0fd-124">Ту же схему используется для таблицы, расширенных и настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="5f0fd-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="5f0fd-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5f0fd-125">See Also</span></span>

[<span data-ttu-id="5f0fd-126">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="5f0fd-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="5f0fd-127">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5f0fd-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="5f0fd-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f0fd-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
