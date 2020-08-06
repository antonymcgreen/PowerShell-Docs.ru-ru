---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5021f665b994581f9ff982e13af922d7940ebf2b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783319"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="1b4c2-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="1b4c2-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="1b4c2-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="1b4c2-104">При наличии этого типа используется определение.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="1b4c2-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="1b4c2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1b4c2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b4c2-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1b4c2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1b4c2-107">Attributes and Elements</span></span>

<span data-ttu-id="1b4c2-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1b4c2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1b4c2-109">Attributes</span></span>

<span data-ttu-id="1b4c2-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1b4c2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1b4c2-111">Child Elements</span></span>

<span data-ttu-id="1b4c2-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1b4c2-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1b4c2-113">Parent Elements</span></span>

|<span data-ttu-id="1b4c2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b4c2-114">Element</span></span>|<span data-ttu-id="1b4c2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1b4c2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1b4c2-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="1b4c2-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="1b4c2-117">Определяет условие, которое должно существовать для использования этой широкой записи.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1b4c2-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1b4c2-118">Text Value</span></span>

<span data-ttu-id="1b4c2-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="1b4c2-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b4c2-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b4c2-120">Remarks</span></span>

<span data-ttu-id="1b4c2-121">Условие выбора может указывать тип .NET или набор выбора, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="1b4c2-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="1b4c2-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1b4c2-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1b4c2-123">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="1b4c2-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b4c2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1b4c2-124">See Also</span></span>

[<span data-ttu-id="1b4c2-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="1b4c2-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1b4c2-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="1b4c2-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1b4c2-127">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="1b4c2-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="1b4c2-128">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="1b4c2-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="1b4c2-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b4c2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
