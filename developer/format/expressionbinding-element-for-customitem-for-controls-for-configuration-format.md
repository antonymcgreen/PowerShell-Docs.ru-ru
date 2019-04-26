---
title: Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065954"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="6c46d-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="6c46d-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6c46d-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="6c46d-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c46d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="6c46d-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для элемента конфигурации ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c46d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c46d-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="6c46d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c46d-107">Attributes and Elements</span></span>

<span data-ttu-id="6c46d-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c46d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c46d-109">Attributes</span></span>

<span data-ttu-id="6c46d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c46d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c46d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c46d-111">Child Elements</span></span>

|<span data-ttu-id="6c46d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c46d-112">Element</span></span>|<span data-ttu-id="6c46d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6c46d-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="6c46d-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-115">Определяет элемент управления, который используется в этом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6c46d-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="6c46d-116">Элемент CustomControlName для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-118">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6c46d-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="6c46d-119">Элемент EnumerateCollection для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-121">Указано, что элементом управления отображаются элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="6c46d-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="6c46d-122">Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-123">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-124">Определяет условие, которое должен существовать для этого общего элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="6c46d-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="6c46d-125">Элемент PropertyName для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-126">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-127">Задает свойство .NET, значение которого отображается с общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c46d-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="6c46d-128">Элемент ScriptBlock для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="6c46d-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c46d-129">Optional element.</span></span><br /><br /> <span data-ttu-id="6c46d-130">Указывает сценарий, значение которого отображается с общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c46d-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6c46d-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c46d-131">Parent Elements</span></span>

|<span data-ttu-id="6c46d-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c46d-132">Element</span></span>|<span data-ttu-id="6c46d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="6c46d-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c46d-134">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="6c46d-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="6c46d-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="6c46d-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6c46d-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="6c46d-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="6c46d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="6c46d-137">See Also</span></span>

[<span data-ttu-id="6c46d-138">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="6c46d-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="6c46d-139">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c46d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
