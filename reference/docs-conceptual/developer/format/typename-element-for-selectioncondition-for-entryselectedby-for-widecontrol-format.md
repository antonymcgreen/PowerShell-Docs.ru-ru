---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d6d43fa-c900-4e2f-952d-deccd584236f
caps.latest.revision: 11
ms.openlocfilehash: 6142350e3843a5feddcb5cee8901bbfa607d8d4c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368063"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="4fca1-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4fca1-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="4fca1-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="4fca1-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="4fca1-104">При наличии этого типа используется определение.</span><span class="sxs-lookup"><span data-stu-id="4fca1-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="4fca1-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион элемент для Ентриселектедби для Видинтри (Format) элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4fca1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fca1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fca1-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fca1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4fca1-107">Attributes and Elements</span></span>

<span data-ttu-id="4fca1-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="4fca1-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fca1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4fca1-109">Attributes</span></span>

<span data-ttu-id="4fca1-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4fca1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fca1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4fca1-111">Child Elements</span></span>

<span data-ttu-id="4fca1-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="4fca1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4fca1-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4fca1-113">Parent Elements</span></span>

|<span data-ttu-id="4fca1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4fca1-114">Element</span></span>|<span data-ttu-id="4fca1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4fca1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fca1-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4fca1-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="4fca1-117">Определяет условие, которое должно существовать для использования этой широкой записи.</span><span class="sxs-lookup"><span data-stu-id="4fca1-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4fca1-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4fca1-118">Text Value</span></span>

<span data-ttu-id="4fca1-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="4fca1-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fca1-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="4fca1-120">Remarks</span></span>

<span data-ttu-id="4fca1-121">Условие выбора может указывать тип .NET или набор выбора, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="4fca1-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="4fca1-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4fca1-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4fca1-123">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="4fca1-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fca1-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fca1-124">See Also</span></span>

[<span data-ttu-id="4fca1-125">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="4fca1-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4fca1-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="4fca1-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4fca1-127">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4fca1-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="4fca1-128">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4fca1-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="4fca1-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fca1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
