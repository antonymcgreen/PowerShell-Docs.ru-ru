---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361563"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="e1682-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e1682-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="e1682-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e1682-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="e1682-104">При наличии этого типа используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="e1682-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="e1682-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) Ентриселектедби элемент для Листентри для ListControl (Format) Селектионкондитион элемент для Ентриселектедби для ListControl (Format) TypeName элемента для Селектионкондитион для ентриселектедби в ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e1682-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e1682-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1682-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1682-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1682-107">Attributes and Elements</span></span>

<span data-ttu-id="e1682-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="e1682-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1682-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1682-109">Attributes</span></span>

<span data-ttu-id="e1682-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e1682-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e1682-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1682-111">Child Elements</span></span>

<span data-ttu-id="e1682-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e1682-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e1682-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1682-113">Parent Elements</span></span>

|<span data-ttu-id="e1682-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1682-114">Element</span></span>|<span data-ttu-id="e1682-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e1682-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1682-116">Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e1682-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="e1682-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="e1682-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e1682-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e1682-118">Text Value</span></span>

<span data-ttu-id="e1682-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="e1682-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1682-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e1682-120">Remarks</span></span>

<span data-ttu-id="e1682-121">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="e1682-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="e1682-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e1682-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e1682-123">Дополнительные сведения о других компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e1682-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1682-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1682-124">See Also</span></span>

[<span data-ttu-id="e1682-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="e1682-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e1682-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="e1682-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e1682-127">Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e1682-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e1682-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1682-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
