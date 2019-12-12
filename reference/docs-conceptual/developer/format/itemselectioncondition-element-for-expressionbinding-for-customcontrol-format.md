---
title: Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362913"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="96666-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="96666-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="96666-103">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="96666-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="96666-104">Количество условий выбора, которое можно указать для элемента управления, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="96666-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="96666-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="96666-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="96666-106">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для элемента View (формат) Кустоментри для Кустоментриес для представления (Format) Кустомитем для Кустоментри для элемента ExpressionBinding представления (Format) для Кустомитем для ошибка customcontrol для элемента представления (Format) Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="96666-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96666-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96666-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96666-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="96666-108">Attributes and Elements</span></span>

<span data-ttu-id="96666-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ItemSelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="96666-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96666-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="96666-110">Attributes</span></span>

<span data-ttu-id="96666-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="96666-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96666-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="96666-112">Child Elements</span></span>

|<span data-ttu-id="96666-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="96666-113">Element</span></span>|<span data-ttu-id="96666-114">Описание</span><span class="sxs-lookup"><span data-stu-id="96666-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96666-115">Элемент PropertyName для Итемселектионкондитион для ошибка customcontrol в представлении (Format</span><span class="sxs-lookup"><span data-stu-id="96666-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="96666-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="96666-116">Optional element.</span></span><br /><br /> <span data-ttu-id="96666-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="96666-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="96666-118">Элемент ScriptBlock для Итемселектионкондитион для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="96666-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="96666-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="96666-119">Optional element.</span></span><br /><br /> <span data-ttu-id="96666-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="96666-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="96666-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="96666-121">Parent Elements</span></span>

|<span data-ttu-id="96666-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="96666-122">Element</span></span>|<span data-ttu-id="96666-123">Описание</span><span class="sxs-lookup"><span data-stu-id="96666-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96666-124">Элемент ExpressionBinding для Кустомитем для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="96666-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="96666-125">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="96666-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="96666-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="96666-126">Remarks</span></span>

<span data-ttu-id="96666-127">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="96666-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="96666-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="96666-128">See Also</span></span>

[<span data-ttu-id="96666-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="96666-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="96666-130">Элемент ExpressionBinding для Кустомитем для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="96666-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
