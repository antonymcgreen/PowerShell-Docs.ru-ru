---
title: Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362923"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="92574-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="92574-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="92574-103">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="92574-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="92574-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="92574-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="92574-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format) Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92574-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92574-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92574-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92574-107">Attributes and Elements</span></span>

<span data-ttu-id="92574-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ItemSelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="92574-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92574-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92574-109">Attributes</span></span>

<span data-ttu-id="92574-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="92574-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92574-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92574-111">Child Elements</span></span>

|<span data-ttu-id="92574-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="92574-112">Element</span></span>|<span data-ttu-id="92574-113">Описание</span><span class="sxs-lookup"><span data-stu-id="92574-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92574-114">Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="92574-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="92574-115">Optional element.</span></span><br /><br /> <span data-ttu-id="92574-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="92574-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="92574-117">Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="92574-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="92574-118">Optional element.</span></span><br /><br /> <span data-ttu-id="92574-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="92574-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="92574-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92574-120">Parent Elements</span></span>

|<span data-ttu-id="92574-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="92574-121">Element</span></span>|<span data-ttu-id="92574-122">Описание</span><span class="sxs-lookup"><span data-stu-id="92574-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92574-123">Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="92574-124">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="92574-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="92574-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="92574-125">Remarks</span></span>

<span data-ttu-id="92574-126">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="92574-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="92574-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="92574-127">See Also</span></span>

[<span data-ttu-id="92574-128">Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="92574-129">Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="92574-130">Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="92574-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="92574-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="92574-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
