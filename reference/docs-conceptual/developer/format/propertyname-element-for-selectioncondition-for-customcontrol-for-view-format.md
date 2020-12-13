---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 1dd325a58b29a0f13b1341559c2a7dfe251c6b36
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665861"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="a870e-103">Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a870e-103">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="a870e-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="a870e-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="a870e-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="a870e-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="a870e-106">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a870e-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="a870e-107">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента представления (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) Кустомитем элемент для Кустоментри для ошибка customcontrol для элемента Ентриселектедби представления (Format) для CustomEntry для ошибка customcontrol для элемента SelectionCondition для представления (Format) EntrySelectedBy (формат).</span><span class="sxs-lookup"><span data-stu-id="a870e-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a870e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a870e-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a870e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a870e-109">Attributes and Elements</span></span>

<span data-ttu-id="a870e-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="a870e-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a870e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a870e-111">Attributes</span></span>

<span data-ttu-id="a870e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a870e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a870e-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a870e-113">Child Elements</span></span>

<span data-ttu-id="a870e-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a870e-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a870e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a870e-115">Parent Elements</span></span>

|<span data-ttu-id="a870e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="a870e-116">Element</span></span>|<span data-ttu-id="a870e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a870e-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a870e-118">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="a870e-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="a870e-119">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a870e-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a870e-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a870e-120">Text Value</span></span>

<span data-ttu-id="a870e-121">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="a870e-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a870e-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a870e-122">Remarks</span></span>

<span data-ttu-id="a870e-123">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="a870e-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="a870e-124">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a870e-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a870e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a870e-125">See Also</span></span>

[<span data-ttu-id="a870e-126">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="a870e-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="a870e-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a870e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
