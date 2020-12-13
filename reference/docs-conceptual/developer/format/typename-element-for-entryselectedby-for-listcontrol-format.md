---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)
description: Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)
ms.openlocfilehash: 6fc5a2385fde3140abbc984e3da6a4dda483b2a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645657"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="31395-103">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="31395-103">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="31395-104">Указывает тип .NET, который использует эту запись представления списка.</span><span class="sxs-lookup"><span data-stu-id="31395-104">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="31395-105">Количество типов, которое можно указать для записи списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="31395-105">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="31395-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) элемент TypeName для ентриселектедби в ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="31395-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="31395-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31395-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="31395-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="31395-108">Attributes and Elements</span></span>

<span data-ttu-id="31395-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="31395-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="31395-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="31395-110">Attributes</span></span>

<span data-ttu-id="31395-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="31395-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="31395-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="31395-112">Child Elements</span></span>

<span data-ttu-id="31395-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="31395-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="31395-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="31395-114">Parent Elements</span></span>

|<span data-ttu-id="31395-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="31395-115">Element</span></span>|<span data-ttu-id="31395-116">Описание</span><span class="sxs-lookup"><span data-stu-id="31395-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31395-117">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="31395-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="31395-118">Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="31395-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="31395-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="31395-119">Text Value</span></span>

<span data-ttu-id="31395-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="31395-120">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="31395-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="31395-121">Remarks</span></span>

<span data-ttu-id="31395-122">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="31395-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="31395-123">Дополнительные сведения об использовании этого элемента в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="31395-123">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="31395-124">Пример</span><span class="sxs-lookup"><span data-stu-id="31395-124">Example</span></span>

<span data-ttu-id="31395-125">В следующем примере показано, как задать набор выбора для записи в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="31395-125">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="31395-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="31395-126">See Also</span></span>

[<span data-ttu-id="31395-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="31395-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="31395-128">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="31395-128">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="31395-129">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="31395-129">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="31395-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="31395-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
