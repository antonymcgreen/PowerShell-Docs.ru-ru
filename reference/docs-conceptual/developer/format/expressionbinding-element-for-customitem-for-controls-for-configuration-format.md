---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 1abcf2173e18d45839161b4c7e59f1ad238f81a1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655339"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="ff216-103">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ff216-104">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="ff216-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="ff216-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ff216-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления в элементе Configuration ExpressionBinding для кустомитем для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="ff216-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff216-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff216-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ff216-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff216-108">Attributes and Elements</span></span>

<span data-ttu-id="ff216-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="ff216-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff216-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff216-110">Attributes</span></span>

<span data-ttu-id="ff216-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff216-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff216-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff216-112">Child Elements</span></span>

|<span data-ttu-id="ff216-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff216-113">Element</span></span>|<span data-ttu-id="ff216-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ff216-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="ff216-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-116">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="ff216-117">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-118">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-119">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="ff216-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="ff216-120">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-121">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-122">Указывает, что элементы коллекций отображаются элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-122">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="ff216-123">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-124">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-125">Определяет условие, которое должно существовать для использования этого общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-125">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="ff216-126">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-127">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-128">Указывает свойство .NET, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-128">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="ff216-129">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ff216-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff216-130">Optional element.</span></span><br /><br /> <span data-ttu-id="ff216-131">Указывает скрипт, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff216-131">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ff216-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff216-132">Parent Elements</span></span>

|<span data-ttu-id="ff216-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff216-133">Element</span></span>|<span data-ttu-id="ff216-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ff216-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff216-135">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff216-135">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="ff216-136">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="ff216-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ff216-137">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ff216-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ff216-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff216-138">See Also</span></span>

[<span data-ttu-id="ff216-139">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff216-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="ff216-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff216-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
