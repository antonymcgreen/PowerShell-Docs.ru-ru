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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076231"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="017a2-102">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="017a2-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="017a2-103">Задает набор объектов .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="017a2-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="017a2-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент ViewSelectedBy (формат) SelectionSetName элемент конфигурации для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="017a2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="017a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="017a2-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="017a2-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="017a2-106">Attributes and Elements</span></span>

<span data-ttu-id="017a2-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="017a2-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="017a2-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="017a2-108">Attributes</span></span>

<span data-ttu-id="017a2-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="017a2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="017a2-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="017a2-110">Child Elements</span></span>

<span data-ttu-id="017a2-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="017a2-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="017a2-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="017a2-112">Parent Elements</span></span>

|<span data-ttu-id="017a2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="017a2-113">Element</span></span>|<span data-ttu-id="017a2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="017a2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="017a2-115">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="017a2-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="017a2-116">Определяет объекты .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="017a2-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="017a2-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="017a2-117">Text Value</span></span>

<span data-ttu-id="017a2-118">Укажите имя набора, который определяется `Name` элемент набора выбора.</span><span class="sxs-lookup"><span data-stu-id="017a2-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="017a2-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="017a2-119">Remarks</span></span>

<span data-ttu-id="017a2-120">Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование.</span><span class="sxs-lookup"><span data-stu-id="017a2-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="017a2-121">Дополнительные сведения об определении и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="017a2-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="017a2-122">Пример</span><span class="sxs-lookup"><span data-stu-id="017a2-122">Example</span></span>

<span data-ttu-id="017a2-123">В следующем примере показано задание выбора представления списка.</span><span class="sxs-lookup"><span data-stu-id="017a2-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="017a2-124">Ту же схему используется для таблицы, расширенных и настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="017a2-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="017a2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="017a2-125">See Also</span></span>

[<span data-ttu-id="017a2-126">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="017a2-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="017a2-127">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="017a2-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="017a2-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="017a2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
