---
title: Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858300"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="368e6-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="368e6-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="368e6-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="368e6-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="368e6-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="368e6-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="368e6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="368e6-106">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="368e6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="368e6-107">Attributes and Elements</span></span>

<span data-ttu-id="368e6-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="368e6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="368e6-109">Attributes</span></span>

<span data-ttu-id="368e6-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="368e6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="368e6-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="368e6-111">Child Elements</span></span>

|<span data-ttu-id="368e6-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="368e6-112">Element</span></span>|<span data-ttu-id="368e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="368e6-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="368e6-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-114">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-115">Определяет элемент управления, который используется в этом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="368e6-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="368e6-116">Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="368e6-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-117">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-118">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="368e6-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="368e6-119">Элемент EnumerateCollection для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="368e6-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-120">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-121">Указывает, что отображаются элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="368e6-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="368e6-122">Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="368e6-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-123">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-124">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="368e6-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="368e6-125">Элемент PropertyName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="368e6-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-126">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-127">Задает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="368e6-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="368e6-128">Элемент ScriptBlock для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="368e6-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="368e6-129">Optional element.</span></span><br /><br /> <span data-ttu-id="368e6-130">Указывает сценарий, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="368e6-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="368e6-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="368e6-131">Parent Elements</span></span>

|<span data-ttu-id="368e6-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="368e6-132">Element</span></span>|<span data-ttu-id="368e6-133">Описание</span><span class="sxs-lookup"><span data-stu-id="368e6-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="368e6-134">Элемент CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="368e6-135">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="368e6-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="368e6-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="368e6-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="368e6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="368e6-137">See Also</span></span>

[<span data-ttu-id="368e6-138">Элемент CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-139">Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-140">Элемент EnumerateCollection для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-141">Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-142">Элемент PropertyName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-143">Элемент ScriptBlock для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="368e6-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="368e6-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="368e6-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
