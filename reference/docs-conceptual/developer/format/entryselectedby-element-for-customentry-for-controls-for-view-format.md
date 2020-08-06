---
title: Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5c82e02d23b1694d05f7a32578ccc5d33686f13f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774258"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="78984-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="78984-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="78984-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="78984-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="78984-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="78984-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol для элемента Control для элементов управления для элемента "View" (формат) Кустоментриес для ошибка customcontrol для элементов управления для представления (Format) кустоментри для кустоментриес для элементов управления представления (формат).</span><span class="sxs-lookup"><span data-stu-id="78984-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78984-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78984-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78984-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78984-107">Attributes and Elements</span></span>

<span data-ttu-id="78984-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="78984-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="78984-109">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="78984-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="78984-110">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="78984-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="78984-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78984-111">Attributes</span></span>

<span data-ttu-id="78984-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78984-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78984-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78984-113">Child Elements</span></span>

|<span data-ttu-id="78984-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="78984-114">Element</span></span>|<span data-ttu-id="78984-115">Описание</span><span class="sxs-lookup"><span data-stu-id="78984-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78984-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="78984-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="78984-117">Optional element.</span></span><br /><br /> <span data-ttu-id="78984-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="78984-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="78984-119">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="78984-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="78984-120">Optional element.</span></span><br /><br /> <span data-ttu-id="78984-121">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="78984-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="78984-122">Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="78984-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="78984-123">Optional element.</span></span><br /><br /> <span data-ttu-id="78984-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="78984-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78984-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78984-125">Parent Elements</span></span>

|<span data-ttu-id="78984-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="78984-126">Element</span></span>|<span data-ttu-id="78984-127">Описание</span><span class="sxs-lookup"><span data-stu-id="78984-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78984-128">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="78984-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="78984-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78984-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="78984-130">Remarks</span></span>

<span data-ttu-id="78984-131">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` .</span><span class="sxs-lookup"><span data-stu-id="78984-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="78984-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="78984-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78984-133">См. также</span><span class="sxs-lookup"><span data-stu-id="78984-133">See Also</span></span>

[<span data-ttu-id="78984-134">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="78984-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="78984-135">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="78984-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
