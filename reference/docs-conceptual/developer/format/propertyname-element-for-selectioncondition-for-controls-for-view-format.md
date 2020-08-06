---
title: Элемент PropertyName для Селектионкондитион элементов управления в представлении (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 251fc129896cfa4a6255330e23854b014675ac5f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780820"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="a2248-102">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a2248-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="a2248-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="a2248-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="a2248-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись.</span><span class="sxs-lookup"><span data-stu-id="a2248-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="a2248-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="a2248-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a2248-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) элемент Кустоментри для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления для представления (Format) элемент PropertyName для SelectionCondition для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a2248-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a2248-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2248-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a2248-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a2248-108">Attributes and Elements</span></span>

<span data-ttu-id="a2248-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="a2248-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a2248-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2248-110">Attributes</span></span>

<span data-ttu-id="a2248-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a2248-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a2248-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a2248-112">Child Elements</span></span>

<span data-ttu-id="a2248-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a2248-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a2248-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a2248-114">Parent Elements</span></span>

|<span data-ttu-id="a2248-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a2248-115">Element</span></span>|<span data-ttu-id="a2248-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a2248-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a2248-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a2248-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a2248-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a2248-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a2248-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a2248-119">Text Value</span></span>

<span data-ttu-id="a2248-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="a2248-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2248-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2248-121">Remarks</span></span>

<span data-ttu-id="a2248-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="a2248-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="a2248-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a2248-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2248-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a2248-124">See Also</span></span>

[<span data-ttu-id="a2248-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a2248-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="a2248-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2248-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
