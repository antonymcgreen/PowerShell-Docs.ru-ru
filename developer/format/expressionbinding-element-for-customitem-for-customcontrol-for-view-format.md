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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860690"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="9dbed-102">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="9dbed-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="9dbed-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="9dbed-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9dbed-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dbed-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9dbed-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9dbed-107">Attributes and Elements</span></span>

<span data-ttu-id="9dbed-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9dbed-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9dbed-109">Attributes</span></span>

<span data-ttu-id="9dbed-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="9dbed-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9dbed-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9dbed-111">Child Elements</span></span>

|<span data-ttu-id="9dbed-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="9dbed-112">Element</span></span>|<span data-ttu-id="9dbed-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9dbed-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="9dbed-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-114">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-115">Определяет элемент управления, который используется в этом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="9dbed-116">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9dbed-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-118">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="9dbed-119">Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9dbed-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-121">Указано, что отображаются элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="9dbed-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="9dbed-122">Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="9dbed-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-124">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="9dbed-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="9dbed-125">Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9dbed-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-126">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-127">Задает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="9dbed-128">Элемент ScriptBlock для ExpressionBinding для CustomCustomControl для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="9dbed-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9dbed-129">Optional element.</span></span><br /><br /> <span data-ttu-id="9dbed-130">Указывает сценарий, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="9dbed-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9dbed-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9dbed-131">Parent Elements</span></span>

|<span data-ttu-id="9dbed-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="9dbed-132">Element</span></span>|<span data-ttu-id="9dbed-133">Описание</span><span class="sxs-lookup"><span data-stu-id="9dbed-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dbed-134">Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="9dbed-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="9dbed-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9dbed-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="9dbed-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="9dbed-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9dbed-137">See Also</span></span>

[<span data-ttu-id="9dbed-138">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9dbed-139">Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9dbed-140">Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="9dbed-141">Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9dbed-142">Элемент ScriptBlock для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9dbed-143">Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9dbed-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9dbed-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dbed-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
