---
title: Элемент TypeName для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5e7b73db5aa597d96141454008c5c58b1827df24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780225"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="1c072-102">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="1c072-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="1c072-103">Указывает тип .NET, который использует эту запись представления списка.</span><span class="sxs-lookup"><span data-stu-id="1c072-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="1c072-104">Количество типов, которое можно указать для записи списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="1c072-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="1c072-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) элемент TypeName для ентриселектедби в ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1c072-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1c072-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c072-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1c072-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c072-107">Attributes and Elements</span></span>

<span data-ttu-id="1c072-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="1c072-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1c072-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c072-109">Attributes</span></span>

<span data-ttu-id="1c072-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c072-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1c072-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c072-111">Child Elements</span></span>

<span data-ttu-id="1c072-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c072-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1c072-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c072-113">Parent Elements</span></span>

|<span data-ttu-id="1c072-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c072-114">Element</span></span>|<span data-ttu-id="1c072-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1c072-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1c072-116">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="1c072-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="1c072-117">Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="1c072-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1c072-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1c072-118">Text Value</span></span>

<span data-ttu-id="1c072-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="1c072-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c072-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c072-120">Remarks</span></span>

<span data-ttu-id="1c072-121">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="1c072-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1c072-122">Дополнительные сведения об использовании этого элемента в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="1c072-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1c072-123">Пример</span><span class="sxs-lookup"><span data-stu-id="1c072-123">Example</span></span>

<span data-ttu-id="1c072-124">В следующем примере показано, как задать набор выбора для записи в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="1c072-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="1c072-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1c072-125">See Also</span></span>

[<span data-ttu-id="1c072-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="1c072-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1c072-127">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="1c072-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="1c072-128">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="1c072-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1c072-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c072-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
