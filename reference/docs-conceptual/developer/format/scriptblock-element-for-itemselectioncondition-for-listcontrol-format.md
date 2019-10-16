---
title: Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362103"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="14bed-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="14bed-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="14bed-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="14bed-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="14bed-104">При вычислении этого скрипта в `true` условие выполняется, и используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="14bed-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="14bed-105">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="14bed-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="14bed-106">Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри для элемента ListControl (Format) ListItem для элементов управления List (Format) Итемселектионкондитион для элемента ListItem в элементе ScriptBlock для ListControl (Format) для Итемселектионкондитион для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="14bed-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="14bed-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14bed-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="14bed-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14bed-108">Attributes and Elements</span></span>

<span data-ttu-id="14bed-109">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="14bed-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="14bed-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14bed-110">Attributes</span></span>

<span data-ttu-id="14bed-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="14bed-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="14bed-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14bed-112">Child Elements</span></span>

<span data-ttu-id="14bed-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="14bed-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="14bed-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14bed-114">Parent Elements</span></span>

|<span data-ttu-id="14bed-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="14bed-115">Element</span></span>|<span data-ttu-id="14bed-116">Описание</span><span class="sxs-lookup"><span data-stu-id="14bed-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="14bed-117">Элемент Итемселектионкондитион для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="14bed-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="14bed-118">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="14bed-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="14bed-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="14bed-119">Text Value</span></span>

<span data-ttu-id="14bed-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="14bed-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="14bed-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="14bed-121">Remarks</span></span>

<span data-ttu-id="14bed-122">Если этот элемент используется, нельзя указать элемент `PropertyName` при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="14bed-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="14bed-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="14bed-123">See Also</span></span>

[<span data-ttu-id="14bed-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="14bed-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
