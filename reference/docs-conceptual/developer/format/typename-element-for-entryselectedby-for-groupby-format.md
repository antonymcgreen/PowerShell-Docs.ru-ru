---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)
description: Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645704"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="5af8e-103">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5af8e-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="5af8e-104">Указывает тип .NET, использующий это определение пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5af8e-104">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="5af8e-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="5af8e-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5af8e-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри для GroupBy.</span><span class="sxs-lookup"><span data-stu-id="5af8e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5af8e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5af8e-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5af8e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5af8e-108">Attributes and Elements</span></span>

<span data-ttu-id="5af8e-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="5af8e-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5af8e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5af8e-110">Attributes</span></span>

<span data-ttu-id="5af8e-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5af8e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5af8e-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5af8e-112">Child Elements</span></span>

<span data-ttu-id="5af8e-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5af8e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5af8e-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5af8e-114">Parent Elements</span></span>

|<span data-ttu-id="5af8e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="5af8e-115">Element</span></span>|<span data-ttu-id="5af8e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5af8e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5af8e-117">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5af8e-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="5af8e-118">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="5af8e-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5af8e-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="5af8e-119">Text Value</span></span>

<span data-ttu-id="5af8e-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="5af8e-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5af8e-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5af8e-121">Remarks</span></span>

<span data-ttu-id="5af8e-122">Для каждого определения элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="5af8e-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="5af8e-123">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5af8e-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5af8e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5af8e-124">See Also</span></span>

[<span data-ttu-id="5af8e-125">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="5af8e-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="5af8e-126">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5af8e-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="5af8e-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5af8e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
