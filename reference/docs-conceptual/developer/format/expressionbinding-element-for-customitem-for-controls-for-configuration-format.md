---
title: Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363193"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="eccab-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="eccab-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="eccab-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="eccab-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="eccab-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="eccab-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eccab-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eccab-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="eccab-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eccab-107">Attributes and Elements</span></span>

<span data-ttu-id="eccab-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="eccab-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eccab-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eccab-109">Attributes</span></span>

<span data-ttu-id="eccab-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="eccab-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eccab-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eccab-111">Child Elements</span></span>

|<span data-ttu-id="eccab-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="eccab-112">Element</span></span>|<span data-ttu-id="eccab-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eccab-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="eccab-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-114">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="eccab-116">Элемент Кустомконтролнаме для ExpressionBinding для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-117">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="eccab-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="eccab-119">Элемент Енумератеколлектион для ExpressionBinding для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-120">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-121">Указывает, что элементы коллекций отображаются элементом управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="eccab-122">Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-123">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-124">Определяет условие, которое должно существовать для использования этого общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="eccab-125">Элемент PropertyName для ExpressionBinding элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-126">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-127">Указывает свойство .NET, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="eccab-128">Элемент ScriptBlock для ExpressionBinding элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="eccab-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccab-129">Optional element.</span></span><br /><br /> <span data-ttu-id="eccab-130">Указывает скрипт, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="eccab-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="eccab-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eccab-131">Parent Elements</span></span>

|<span data-ttu-id="eccab-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="eccab-132">Element</span></span>|<span data-ttu-id="eccab-133">Описание</span><span class="sxs-lookup"><span data-stu-id="eccab-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eccab-134">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="eccab-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="eccab-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="eccab-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="eccab-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="eccab-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="eccab-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="eccab-137">See Also</span></span>

[<span data-ttu-id="eccab-138">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="eccab-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="eccab-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="eccab-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
