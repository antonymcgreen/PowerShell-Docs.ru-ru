---
title: Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064413"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="c0388-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c0388-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="c0388-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="c0388-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c0388-104">При вычислении этого сценария для `true`условие выполняется, и используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="c0388-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="c0388-105">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="c0388-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="c0388-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems для списка (формат) ItemSelectionCondition элемент Control для ListItem для элемента ListControl (формат) ScriptBlock для ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c0388-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0388-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0388-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0388-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0388-108">Attributes and Elements</span></span>

<span data-ttu-id="c0388-109">В следующих разделах атрибуты, дочерние и родительские элементы из `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="c0388-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0388-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0388-110">Attributes</span></span>

<span data-ttu-id="c0388-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="c0388-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0388-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0388-112">Child Elements</span></span>

<span data-ttu-id="c0388-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="c0388-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c0388-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0388-114">Parent Elements</span></span>

|<span data-ttu-id="c0388-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0388-115">Element</span></span>|<span data-ttu-id="c0388-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c0388-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0388-117">Элемент ItemSelectionCondition для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c0388-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="c0388-118">Определяет условие, которое должен существовать для данного элемента списка для использования.</span><span class="sxs-lookup"><span data-stu-id="c0388-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c0388-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c0388-119">Text Value</span></span>

<span data-ttu-id="c0388-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="c0388-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0388-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="c0388-121">Remarks</span></span>

<span data-ttu-id="c0388-122">Если этот элемент используется, нельзя указать `PropertyName` элемент при определении условию выбора.</span><span class="sxs-lookup"><span data-stu-id="c0388-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0388-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c0388-123">See Also</span></span>

[<span data-ttu-id="c0388-124">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0388-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
