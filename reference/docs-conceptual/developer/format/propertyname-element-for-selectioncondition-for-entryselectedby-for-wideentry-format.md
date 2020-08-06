---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ca2106dbbd8da345e71e83a3ead3cf7a1cb44cb4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773119"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="f50a2-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f50a2-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="f50a2-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f50a2-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f50a2-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="f50a2-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="f50a2-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f50a2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f50a2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f50a2-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f50a2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f50a2-107">Attributes and Elements</span></span>

<span data-ttu-id="f50a2-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="f50a2-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f50a2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f50a2-109">Attributes</span></span>

<span data-ttu-id="f50a2-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f50a2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f50a2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f50a2-111">Child Elements</span></span>

<span data-ttu-id="f50a2-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f50a2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f50a2-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f50a2-113">Parent Elements</span></span>

|<span data-ttu-id="f50a2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f50a2-114">Element</span></span>|<span data-ttu-id="f50a2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f50a2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f50a2-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="f50a2-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f50a2-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="f50a2-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f50a2-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f50a2-118">Text Value</span></span>

<span data-ttu-id="f50a2-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="f50a2-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f50a2-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="f50a2-120">Remarks</span></span>

<span data-ttu-id="f50a2-121">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="f50a2-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f50a2-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f50a2-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f50a2-123">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="f50a2-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f50a2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f50a2-124">See Also</span></span>

[<span data-ttu-id="f50a2-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="f50a2-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f50a2-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="f50a2-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f50a2-127">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="f50a2-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f50a2-128">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="f50a2-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f50a2-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f50a2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
