---
title: TypeName-элемент для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 3f0c0ba1fe85d70557e67a30b3a9a59a33043475
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856110"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="0c52c-102">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0c52c-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="0c52c-103">Указывает тип .NET, который использует эту операцию в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="0c52c-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="0c52c-104">Нет ограничений на число типов, которые могут быть указаны для записи в списке.</span><span class="sxs-lookup"><span data-stu-id="0c52c-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="0c52c-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента TypeName ListEntry (формат) для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0c52c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c52c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c52c-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c52c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0c52c-107">Attributes and Elements</span></span>

<span data-ttu-id="0c52c-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="0c52c-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c52c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0c52c-109">Attributes</span></span>

<span data-ttu-id="0c52c-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="0c52c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c52c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0c52c-111">Child Elements</span></span>

<span data-ttu-id="0c52c-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="0c52c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0c52c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0c52c-113">Parent Elements</span></span>

|<span data-ttu-id="0c52c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0c52c-114">Element</span></span>|<span data-ttu-id="0c52c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0c52c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c52c-116">Элемент EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0c52c-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="0c52c-117">Определяет типы .NET, использующих этот элемент списка или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="0c52c-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0c52c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0c52c-118">Text Value</span></span>

<span data-ttu-id="0c52c-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="0c52c-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c52c-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="0c52c-120">Remarks</span></span>

<span data-ttu-id="0c52c-121">Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="0c52c-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="0c52c-122">Дополнительные сведения о том, как этот элемент используется в виде списка, см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="0c52c-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="0c52c-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0c52c-123">Example</span></span>

<span data-ttu-id="0c52c-124">В следующем примере показано задание выбора для записи представления списка.</span><span class="sxs-lookup"><span data-stu-id="0c52c-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="0c52c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0c52c-125">See Also</span></span>

[<span data-ttu-id="0c52c-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="0c52c-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="0c52c-127">Элемент EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0c52c-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="0c52c-128">Элемент SelectionSetName для EnrtySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0c52c-128">SelectionSetName Element for EnrtySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="0c52c-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c52c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
