---
title: Элемент TypeName для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 0f7216d4dcc0380bceb47ea7c15b3d4a7e5ceeb2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361663"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="84df7-102">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="84df7-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="84df7-103">Указывает тип .NET, который использует эту запись представления списка.</span><span class="sxs-lookup"><span data-stu-id="84df7-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="84df7-104">Количество типов, которое можно указать для записи списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="84df7-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="84df7-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для элемента TypeName Листентри (Format) для Ентриселектедби для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="84df7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84df7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84df7-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="84df7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="84df7-107">Attributes and Elements</span></span>

<span data-ttu-id="84df7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="84df7-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="84df7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84df7-109">Attributes</span></span>

<span data-ttu-id="84df7-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="84df7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84df7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84df7-111">Child Elements</span></span>

<span data-ttu-id="84df7-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="84df7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="84df7-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="84df7-113">Parent Elements</span></span>

|<span data-ttu-id="84df7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="84df7-114">Element</span></span>|<span data-ttu-id="84df7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="84df7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84df7-116">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="84df7-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="84df7-117">Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="84df7-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="84df7-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="84df7-118">Text Value</span></span>

<span data-ttu-id="84df7-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="84df7-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="84df7-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="84df7-120">Remarks</span></span>

<span data-ttu-id="84df7-121">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="84df7-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="84df7-122">Дополнительные сведения об использовании этого элемента в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="84df7-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="84df7-123">Пример</span><span class="sxs-lookup"><span data-stu-id="84df7-123">Example</span></span>

<span data-ttu-id="84df7-124">В следующем примере показано, как задать набор выбора для записи в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="84df7-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="84df7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="84df7-125">See Also</span></span>

[<span data-ttu-id="84df7-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="84df7-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="84df7-127">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="84df7-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="84df7-128">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="84df7-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="84df7-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="84df7-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
