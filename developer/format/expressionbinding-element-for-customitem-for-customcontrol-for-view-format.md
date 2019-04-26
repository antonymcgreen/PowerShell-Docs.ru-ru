---
title: Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065926"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="7025a-102">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="7025a-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="7025a-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="7025a-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7025a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7025a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7025a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7025a-107">Attributes and Elements</span></span>

<span data-ttu-id="7025a-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7025a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7025a-109">Attributes</span></span>

<span data-ttu-id="7025a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7025a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7025a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7025a-111">Child Elements</span></span>

|<span data-ttu-id="7025a-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7025a-112">Element</span></span>|<span data-ttu-id="7025a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7025a-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="7025a-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-115">Определяет элемент управления, который используется в этом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="7025a-116">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="7025a-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-118">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="7025a-119">Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="7025a-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-121">Указано, что отображаются элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="7025a-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="7025a-122">Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="7025a-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-124">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="7025a-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="7025a-125">Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="7025a-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-127">Задает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="7025a-128">Элемент ScriptBlock для ExpressionBinding для CustomCustomControl для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="7025a-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7025a-129">Optional element.</span></span><br /><br /> <span data-ttu-id="7025a-130">Указывает сценарий, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7025a-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7025a-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7025a-131">Parent Elements</span></span>

|<span data-ttu-id="7025a-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="7025a-132">Element</span></span>|<span data-ttu-id="7025a-133">Описание</span><span class="sxs-lookup"><span data-stu-id="7025a-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7025a-134">Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="7025a-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="7025a-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7025a-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="7025a-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7025a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="7025a-137">See Also</span></span>

[<span data-ttu-id="7025a-138">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7025a-139">Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7025a-140">Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="7025a-141">Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7025a-142">Элемент ScriptBlock для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7025a-143">Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="7025a-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7025a-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7025a-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
