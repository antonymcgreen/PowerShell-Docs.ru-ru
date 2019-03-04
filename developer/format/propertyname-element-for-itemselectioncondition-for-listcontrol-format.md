---
title: Элемент PropertyName для ItemSelectionCondition для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855540"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="0f41f-102">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f41f-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="0f41f-103">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="0f41f-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="0f41f-104">Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется представление.</span><span class="sxs-lookup"><span data-stu-id="0f41f-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="0f41f-105">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="0f41f-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="0f41f-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) элемент ListEntries (формат) ListEntry элемента конфигурации для элемента ListControl (формат) ListItems ListEntry для ListItem ListControl (формат) Элемент для ListItems для элемента ListControl (формат) ItemSelectionCondition ListItem для элемента PropertyName объектов ListControls ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f41f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f41f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f41f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f41f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f41f-108">Attributes and Elements</span></span>

<span data-ttu-id="0f41f-109">В следующих разделах атрибуты, дочерние и родительские элементы из `PropertyName` элемент.</span><span class="sxs-lookup"><span data-stu-id="0f41f-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f41f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f41f-110">Attributes</span></span>

<span data-ttu-id="0f41f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f41f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f41f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f41f-112">Child Elements</span></span>

<span data-ttu-id="0f41f-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f41f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f41f-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f41f-114">Parent Elements</span></span>

|<span data-ttu-id="0f41f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f41f-115">Element</span></span>|<span data-ttu-id="0f41f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0f41f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f41f-117">Элемент ItemSelectionCondition для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f41f-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="0f41f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0f41f-118">Text Value</span></span>

<span data-ttu-id="0f41f-119">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="0f41f-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f41f-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="0f41f-120">Remarks</span></span>

<span data-ttu-id="0f41f-121">Если этот элемент используется, нельзя указать [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) элемент при определении условию выбора.</span><span class="sxs-lookup"><span data-stu-id="0f41f-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f41f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0f41f-122">See Also</span></span>

[<span data-ttu-id="0f41f-123">Элемент ScriptBlock для ItemSelectionCondition для ListIControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f41f-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="0f41f-124">Элемент ItemSelectionCondition для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f41f-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="0f41f-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f41f-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
