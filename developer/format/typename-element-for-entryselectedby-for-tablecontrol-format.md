---
title: TypeName-элемент для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855730"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="4616b-102">Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4616b-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="4616b-103">Указывает тип .NET, который использует эту операцию представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="4616b-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="4616b-104">Нет ограничений на число типов, которые могут быть указаны для записи таблицы.</span><span class="sxs-lookup"><span data-stu-id="4616b-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="4616b-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент EntrySelectedBy (формат) TypeName элемент конфигурации для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4616b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4616b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4616b-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4616b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4616b-107">Attributes and Elements</span></span>

<span data-ttu-id="4616b-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="4616b-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4616b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4616b-109">Attributes</span></span>

<span data-ttu-id="4616b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4616b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4616b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4616b-111">Child Elements</span></span>

<span data-ttu-id="4616b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="4616b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4616b-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4616b-113">Parent Elements</span></span>

|<span data-ttu-id="4616b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4616b-114">Element</span></span>|<span data-ttu-id="4616b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4616b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4616b-116">Элемент EntrySelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4616b-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="4616b-117">Определяет типы .NET, использующих эту запись или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="4616b-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4616b-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4616b-118">Text Value</span></span>

<span data-ttu-id="4616b-119">Укажите имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="4616b-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="4616b-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="4616b-120">Remarks</span></span>

<span data-ttu-id="4616b-121">Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="4616b-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="4616b-122">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="4616b-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4616b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4616b-123">See Also</span></span>

[<span data-ttu-id="4616b-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="4616b-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4616b-125">Элемент EntrySelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4616b-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="4616b-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4616b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
