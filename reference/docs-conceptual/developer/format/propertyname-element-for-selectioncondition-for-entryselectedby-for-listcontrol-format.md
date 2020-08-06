---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785563"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="7c8b8-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7c8b8-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="7c8b8-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="7c8b8-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="7c8b8-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7c8b8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c8b8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c8b8-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c8b8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c8b8-107">Attributes and Elements</span></span>

<span data-ttu-id="7c8b8-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c8b8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c8b8-109">Attributes</span></span>

<span data-ttu-id="7c8b8-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c8b8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c8b8-111">Child Elements</span></span>

<span data-ttu-id="7c8b8-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c8b8-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c8b8-113">Parent Elements</span></span>

|<span data-ttu-id="7c8b8-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="7c8b8-114">Element</span></span>|<span data-ttu-id="7c8b8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7c8b8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c8b8-116">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7c8b8-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7c8b8-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c8b8-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7c8b8-118">Text Value</span></span>

<span data-ttu-id="7c8b8-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c8b8-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c8b8-120">Remarks</span></span>

<span data-ttu-id="7c8b8-121">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="7c8b8-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="7c8b8-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b8-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7c8b8-123">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b8-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c8b8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7c8b8-124">See Also</span></span>

[<span data-ttu-id="7c8b8-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="7c8b8-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7c8b8-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="7c8b8-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7c8b8-127">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7c8b8-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="7c8b8-128">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7c8b8-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7c8b8-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c8b8-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
