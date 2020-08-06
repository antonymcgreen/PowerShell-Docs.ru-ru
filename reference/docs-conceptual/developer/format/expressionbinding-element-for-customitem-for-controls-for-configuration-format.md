---
title: Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773918"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="3c160-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="3c160-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="3c160-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="3c160-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="3c160-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления в элементе Configuration ExpressionBinding для кустомитем для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="3c160-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c160-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c160-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3c160-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3c160-107">Attributes and Elements</span></span>

<span data-ttu-id="3c160-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="3c160-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3c160-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3c160-109">Attributes</span></span>

<span data-ttu-id="3c160-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3c160-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3c160-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3c160-111">Child Elements</span></span>

|<span data-ttu-id="3c160-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c160-112">Element</span></span>|<span data-ttu-id="3c160-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3c160-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="3c160-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-114">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="3c160-116">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-117">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="3c160-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="3c160-119">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-120">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-121">Указывает, что элементы коллекций отображаются элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="3c160-122">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-123">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-124">Определяет условие, которое должно существовать для использования этого общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="3c160-125">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-126">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-127">Указывает свойство .NET, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="3c160-128">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="3c160-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c160-129">Optional element.</span></span><br /><br /> <span data-ttu-id="3c160-130">Указывает скрипт, значение которого отображается общим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3c160-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3c160-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3c160-131">Parent Elements</span></span>

|<span data-ttu-id="3c160-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c160-132">Element</span></span>|<span data-ttu-id="3c160-133">Описание</span><span class="sxs-lookup"><span data-stu-id="3c160-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c160-134">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="3c160-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="3c160-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="3c160-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3c160-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c160-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3c160-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3c160-137">See Also</span></span>

[<span data-ttu-id="3c160-138">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="3c160-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="3c160-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c160-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
