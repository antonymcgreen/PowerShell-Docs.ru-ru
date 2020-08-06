---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783472"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="52c7a-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="52c7a-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="52c7a-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="52c7a-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="52c7a-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="52c7a-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="52c7a-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) элемент PropertyName для SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="52c7a-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52c7a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52c7a-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52c7a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52c7a-107">Attributes and Elements</span></span>

<span data-ttu-id="52c7a-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="52c7a-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="52c7a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52c7a-109">Attributes</span></span>

<span data-ttu-id="52c7a-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="52c7a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52c7a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52c7a-111">Child Elements</span></span>

<span data-ttu-id="52c7a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="52c7a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="52c7a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52c7a-113">Parent Elements</span></span>

|<span data-ttu-id="52c7a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="52c7a-114">Element</span></span>|<span data-ttu-id="52c7a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="52c7a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52c7a-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="52c7a-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="52c7a-117">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="52c7a-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="52c7a-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="52c7a-118">Text Value</span></span>

<span data-ttu-id="52c7a-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="52c7a-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="52c7a-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="52c7a-120">Remarks</span></span>

<span data-ttu-id="52c7a-121">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="52c7a-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="52c7a-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="52c7a-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52c7a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="52c7a-123">See Also</span></span>

[<span data-ttu-id="52c7a-124">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="52c7a-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="52c7a-125">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="52c7a-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="52c7a-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="52c7a-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="52c7a-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c7a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
