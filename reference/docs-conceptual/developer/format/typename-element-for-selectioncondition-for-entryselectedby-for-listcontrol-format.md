---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787381"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="7bf9e-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7bf9e-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="7bf9e-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="7bf9e-104">При наличии этого типа используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="7bf9e-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для листентриес для ListControl (Format) ентриселектедби для листентри for ListControl (формат) селектионкондитион элемента for EntrySelectedBy for ListControl для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="7bf9e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7bf9e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bf9e-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7bf9e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7bf9e-107">Attributes and Elements</span></span>

<span data-ttu-id="7bf9e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7bf9e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7bf9e-109">Attributes</span></span>

<span data-ttu-id="7bf9e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7bf9e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7bf9e-111">Child Elements</span></span>

<span data-ttu-id="7bf9e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7bf9e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7bf9e-113">Parent Elements</span></span>

|<span data-ttu-id="7bf9e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bf9e-114">Element</span></span>|<span data-ttu-id="7bf9e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7bf9e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bf9e-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7bf9e-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7bf9e-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7bf9e-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7bf9e-118">Text Value</span></span>

<span data-ttu-id="7bf9e-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="7bf9e-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bf9e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bf9e-120">Remarks</span></span>

<span data-ttu-id="7bf9e-121">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="7bf9e-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="7bf9e-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7bf9e-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7bf9e-123">Дополнительные сведения о других компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="7bf9e-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7bf9e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7bf9e-124">See Also</span></span>

[<span data-ttu-id="7bf9e-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="7bf9e-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7bf9e-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="7bf9e-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7bf9e-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7bf9e-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7bf9e-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bf9e-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
