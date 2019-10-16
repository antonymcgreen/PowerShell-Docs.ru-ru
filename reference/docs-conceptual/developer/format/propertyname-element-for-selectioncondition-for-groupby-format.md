---
title: Элемент PropertyName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1707317-6c26-4866-bcc1-8924103c9014
caps.latest.revision: 6
ms.openlocfilehash: 7241ea0ea364befa7ad4ab0af4c4209be72214a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364953"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="cf6cd-102">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="cf6cd-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="cf6cd-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="cf6cd-104">Если это свойство имеется или если оно имеет значение `true`, условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="cf6cd-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="cf6cd-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy для Кустоментри для GroupBy (Format) Селектионкондитион элемента для Ентриселектедби для GroupBy (Format) элемент PropertyName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cf6cd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cf6cd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf6cd-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf6cd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf6cd-108">Attributes and Elements</span></span>

<span data-ttu-id="cf6cd-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf6cd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf6cd-110">Attributes</span></span>

<span data-ttu-id="cf6cd-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cf6cd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf6cd-112">Child Elements</span></span>

<span data-ttu-id="cf6cd-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cf6cd-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf6cd-114">Parent Elements</span></span>

|<span data-ttu-id="cf6cd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf6cd-115">Element</span></span>|<span data-ttu-id="cf6cd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="cf6cd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf6cd-117">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cf6cd-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="cf6cd-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cf6cd-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="cf6cd-119">Text Value</span></span>

<span data-ttu-id="cf6cd-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf6cd-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="cf6cd-121">Remarks</span></span>

<span data-ttu-id="cf6cd-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="cf6cd-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="cf6cd-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf6cd-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf6cd-124">See Also</span></span>

[<span data-ttu-id="cf6cd-125">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cf6cd-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="cf6cd-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf6cd-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
