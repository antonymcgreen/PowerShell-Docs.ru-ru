---
title: Элемент PropertyName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 8ada9a8ca7fbfdba5b2fea1881b2670c56a71d4f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773085"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="39085-102">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="39085-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="39085-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="39085-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="39085-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="39085-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="39085-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="39085-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="39085-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy для селектионкондитион для EntrySelectedBy for GroupBy (формат), для SelectionCondition в качестве элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="39085-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="39085-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39085-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39085-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="39085-108">Attributes and Elements</span></span>

<span data-ttu-id="39085-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="39085-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="39085-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="39085-110">Attributes</span></span>

<span data-ttu-id="39085-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="39085-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="39085-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="39085-112">Child Elements</span></span>

<span data-ttu-id="39085-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="39085-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="39085-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="39085-114">Parent Elements</span></span>

|<span data-ttu-id="39085-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="39085-115">Element</span></span>|<span data-ttu-id="39085-116">Описание</span><span class="sxs-lookup"><span data-stu-id="39085-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39085-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="39085-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="39085-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="39085-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="39085-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="39085-119">Text Value</span></span>

<span data-ttu-id="39085-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="39085-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="39085-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="39085-121">Remarks</span></span>

<span data-ttu-id="39085-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="39085-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="39085-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="39085-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39085-124">См. также</span><span class="sxs-lookup"><span data-stu-id="39085-124">See Also</span></span>

[<span data-ttu-id="39085-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="39085-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="39085-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="39085-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
