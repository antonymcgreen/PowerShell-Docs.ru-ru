---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)
description: Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: 096d2355e113a7e44cc6ae31ea23efc3f01080a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664640"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="f12b3-103">Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f12b3-103">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="f12b3-104">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f12b3-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="f12b3-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="f12b3-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f12b3-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format). селектионкондитион для EntrySelectedBy for GroupBy в SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f12b3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f12b3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f12b3-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f12b3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f12b3-108">Attributes and Elements</span></span>

<span data-ttu-id="f12b3-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="f12b3-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f12b3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f12b3-110">Attributes</span></span>

<span data-ttu-id="f12b3-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f12b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f12b3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f12b3-112">Child Elements</span></span>

<span data-ttu-id="f12b3-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f12b3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f12b3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f12b3-114">Parent Elements</span></span>

|<span data-ttu-id="f12b3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f12b3-115">Element</span></span>|<span data-ttu-id="f12b3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f12b3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f12b3-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f12b3-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f12b3-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f12b3-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f12b3-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f12b3-119">Text Value</span></span>

<span data-ttu-id="f12b3-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="f12b3-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f12b3-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f12b3-121">Remarks</span></span>

<span data-ttu-id="f12b3-122">Если этот элемент указан, нельзя указать `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="f12b3-122">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="f12b3-123">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f12b3-123">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f12b3-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f12b3-124">See Also</span></span>

[<span data-ttu-id="f12b3-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f12b3-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f12b3-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f12b3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
