---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)
description: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665053"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="5f02e-103">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5f02e-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="5f02e-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="5f02e-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="5f02e-105">При вычислении этого скрипта выполняется `true` условие, и используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="5f02e-105">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="5f02e-106">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="5f02e-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="5f02e-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элемента списка элементов управления "список" (формат) ListControl для элемента SPListItem в итемселектионкондитион (Format) элемент ScriptBlock для ListControl в ItemSelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="5f02e-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f02e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f02e-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5f02e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5f02e-109">Attributes and Elements</span></span>

<span data-ttu-id="5f02e-110">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="5f02e-110">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f02e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f02e-111">Attributes</span></span>

<span data-ttu-id="5f02e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5f02e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f02e-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f02e-113">Child Elements</span></span>

<span data-ttu-id="5f02e-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5f02e-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5f02e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f02e-115">Parent Elements</span></span>

|<span data-ttu-id="5f02e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f02e-116">Element</span></span>|<span data-ttu-id="5f02e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5f02e-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f02e-118">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5f02e-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5f02e-119">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="5f02e-119">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5f02e-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="5f02e-120">Text Value</span></span>

<span data-ttu-id="5f02e-121">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="5f02e-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f02e-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5f02e-122">Remarks</span></span>

<span data-ttu-id="5f02e-123">Если используется этот элемент, нельзя указать `PropertyName` элемент при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="5f02e-123">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f02e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f02e-124">See Also</span></span>

[<span data-ttu-id="5f02e-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f02e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
