---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)
description: Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645751"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="c7464-103">Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c7464-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="c7464-104">Указывает тип .NET, который использует это определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7464-104">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="c7464-105">Количество типов, которое можно указать для определения, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="c7464-105">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="c7464-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления кустоментри для кустоментриес для представления (Format) ентриселектедби для кустоментри для EntrySelectedBy для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="c7464-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c7464-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7464-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c7464-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c7464-108">Attributes and Elements</span></span>

<span data-ttu-id="c7464-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="c7464-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c7464-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c7464-110">Attributes</span></span>

<span data-ttu-id="c7464-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c7464-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c7464-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c7464-112">Child Elements</span></span>

<span data-ttu-id="c7464-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c7464-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c7464-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c7464-114">Parent Elements</span></span>

|<span data-ttu-id="c7464-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c7464-115">Element</span></span>|<span data-ttu-id="c7464-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c7464-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c7464-117">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c7464-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="c7464-118">Определяет типы .NET, которые используют это определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="c7464-118">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c7464-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c7464-119">Text Value</span></span>

<span data-ttu-id="c7464-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="c7464-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7464-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c7464-121">Remarks</span></span>

<span data-ttu-id="c7464-122">Для каждого определения представления пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="c7464-122">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="c7464-123">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c7464-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7464-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7464-124">See Also</span></span>

[<span data-ttu-id="c7464-125">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="c7464-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="c7464-126">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c7464-126">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c7464-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7464-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
