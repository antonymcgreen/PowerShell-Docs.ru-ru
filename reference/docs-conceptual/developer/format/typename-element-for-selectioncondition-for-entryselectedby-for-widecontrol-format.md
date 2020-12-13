---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: af6e4782c345b43e16bce59c333bdaaceba0d845
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645508"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="a46dd-103">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a46dd-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="a46dd-104">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="a46dd-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="a46dd-105">При наличии этого типа используется определение.</span><span class="sxs-lookup"><span data-stu-id="a46dd-105">When this type is present, the definition is used.</span></span>

<span data-ttu-id="a46dd-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="a46dd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a46dd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a46dd-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a46dd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a46dd-108">Attributes and Elements</span></span>

<span data-ttu-id="a46dd-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="a46dd-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a46dd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a46dd-110">Attributes</span></span>

<span data-ttu-id="a46dd-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a46dd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a46dd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a46dd-112">Child Elements</span></span>

<span data-ttu-id="a46dd-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a46dd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a46dd-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a46dd-114">Parent Elements</span></span>

|<span data-ttu-id="a46dd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a46dd-115">Element</span></span>|<span data-ttu-id="a46dd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a46dd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a46dd-117">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a46dd-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a46dd-118">Определяет условие, которое должно существовать для использования этой широкой записи.</span><span class="sxs-lookup"><span data-stu-id="a46dd-118">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a46dd-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a46dd-119">Text Value</span></span>

<span data-ttu-id="a46dd-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="a46dd-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a46dd-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a46dd-121">Remarks</span></span>

<span data-ttu-id="a46dd-122">Условие выбора может указывать тип .NET или набор выбора, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="a46dd-122">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="a46dd-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a46dd-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a46dd-124">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a46dd-124">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a46dd-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a46dd-125">See Also</span></span>

[<span data-ttu-id="a46dd-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="a46dd-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a46dd-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="a46dd-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a46dd-128">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a46dd-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a46dd-129">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="a46dd-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="a46dd-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a46dd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
