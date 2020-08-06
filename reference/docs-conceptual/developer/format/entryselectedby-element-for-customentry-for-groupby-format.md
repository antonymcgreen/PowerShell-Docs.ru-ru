---
title: Элемент Ентриселектедби для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774139"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="9b25e-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="9b25e-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="9b25e-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="9b25e-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="9b25e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9b25e-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b25e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b25e-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b25e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b25e-107">Attributes and Elements</span></span>

<span data-ttu-id="9b25e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="9b25e-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="9b25e-109">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="9b25e-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="9b25e-110">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9b25e-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b25e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b25e-111">Attributes</span></span>

<span data-ttu-id="9b25e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b25e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b25e-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b25e-113">Child Elements</span></span>

|<span data-ttu-id="9b25e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b25e-114">Element</span></span>|<span data-ttu-id="9b25e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9b25e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b25e-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="9b25e-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9b25e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9b25e-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="9b25e-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="9b25e-119">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="9b25e-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9b25e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9b25e-121">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9b25e-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="9b25e-122">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="9b25e-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9b25e-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9b25e-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9b25e-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9b25e-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b25e-125">Parent Elements</span></span>

|<span data-ttu-id="9b25e-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b25e-126">Element</span></span>|<span data-ttu-id="9b25e-127">Описание</span><span class="sxs-lookup"><span data-stu-id="9b25e-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b25e-128">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="9b25e-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9b25e-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b25e-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b25e-130">Remarks</span></span>

<span data-ttu-id="9b25e-131">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` .</span><span class="sxs-lookup"><span data-stu-id="9b25e-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="9b25e-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9b25e-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b25e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="9b25e-133">See Also</span></span>

[<span data-ttu-id="9b25e-134">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="9b25e-135">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="9b25e-136">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="9b25e-137">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="9b25e-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="9b25e-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b25e-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
