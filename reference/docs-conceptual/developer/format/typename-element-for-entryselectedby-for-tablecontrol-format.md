---
title: Элемент TypeName для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c514d3e6155278ddd3a0565c87e9377dc8419356
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780208"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="dc13f-102">Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dc13f-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="dc13f-103">Указывает тип .NET, который использует эту запись табличного представления.</span><span class="sxs-lookup"><span data-stu-id="dc13f-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="dc13f-104">Количество типов, которое можно указать для записи в таблице, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="dc13f-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="dc13f-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби элемент (Format) элемент TypeName для Ентриселектедби в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="dc13f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dc13f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc13f-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dc13f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc13f-107">Attributes and Elements</span></span>

<span data-ttu-id="dc13f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="dc13f-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dc13f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc13f-109">Attributes</span></span>

<span data-ttu-id="dc13f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc13f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dc13f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc13f-111">Child Elements</span></span>

<span data-ttu-id="dc13f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc13f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dc13f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc13f-113">Parent Elements</span></span>

|<span data-ttu-id="dc13f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc13f-114">Element</span></span>|<span data-ttu-id="dc13f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dc13f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc13f-116">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="dc13f-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="dc13f-117">Определяет типы .NET, которые используют эту запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="dc13f-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dc13f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="dc13f-118">Text Value</span></span>

<span data-ttu-id="dc13f-119">Укажите имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="dc13f-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc13f-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc13f-120">Remarks</span></span>

<span data-ttu-id="dc13f-121">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="dc13f-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="dc13f-122">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="dc13f-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc13f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="dc13f-123">See Also</span></span>

[<span data-ttu-id="dc13f-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="dc13f-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dc13f-125">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="dc13f-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="dc13f-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc13f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
