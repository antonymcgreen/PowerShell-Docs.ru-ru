---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)
description: Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665997"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="8a6f9-103">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a6f9-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="8a6f9-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8a6f9-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется представление.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-105">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="8a6f9-106">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="8a6f9-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент для ListControl (Format) элементов ListItem для листентри для ListControl (Format) элемент ListItem для элемента ListItem для ListControl (формат) Итемселектионкондитион для элемента ListItem для листконтролс в ItemSelectionCondition (Format)</span><span class="sxs-lookup"><span data-stu-id="8a6f9-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a6f9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a6f9-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a6f9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a6f9-109">Attributes and Elements</span></span>

<span data-ttu-id="8a6f9-110">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-110">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a6f9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a6f9-111">Attributes</span></span>

<span data-ttu-id="8a6f9-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a6f9-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a6f9-113">Child Elements</span></span>

<span data-ttu-id="8a6f9-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a6f9-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a6f9-115">Parent Elements</span></span>

|<span data-ttu-id="8a6f9-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a6f9-116">Element</span></span>|<span data-ttu-id="8a6f9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8a6f9-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a6f9-118">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a6f9-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="8a6f9-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8a6f9-119">Text Value</span></span>

<span data-ttu-id="8a6f9-120">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-120">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a6f9-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8a6f9-121">Remarks</span></span>

<span data-ttu-id="8a6f9-122">Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="8a6f9-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a6f9-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a6f9-123">See Also</span></span>

[<span data-ttu-id="8a6f9-124">Элемент ScriptBlock для Итемселектионкондитион для Листиконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="8a6f9-124">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="8a6f9-125">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a6f9-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="8a6f9-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a6f9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
