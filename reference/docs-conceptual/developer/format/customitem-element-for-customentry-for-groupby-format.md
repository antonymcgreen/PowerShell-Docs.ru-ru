---
title: Элемент Кустомитем для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783727"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="e60bb-102">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="e60bb-103">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="e60bb-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="e60bb-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="e60bb-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e60bb-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) Кустомитем для ошибка customcontrol для Кустоментри для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e60bb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e60bb-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e60bb-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e60bb-107">Attributes and Elements</span></span>

<span data-ttu-id="e60bb-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="e60bb-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e60bb-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e60bb-109">Attributes</span></span>

<span data-ttu-id="e60bb-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e60bb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e60bb-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e60bb-111">Child Elements</span></span>

|<span data-ttu-id="e60bb-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e60bb-112">Element</span></span>|<span data-ttu-id="e60bb-113">Description</span><span class="sxs-lookup"><span data-stu-id="e60bb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e60bb-114">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="e60bb-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e60bb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e60bb-116">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e60bb-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="e60bb-117">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="e60bb-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e60bb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e60bb-119">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="e60bb-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="e60bb-120">Элемент NewLine для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="e60bb-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e60bb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e60bb-122">Добавляет пустую строку к отображению элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e60bb-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="e60bb-123">Элемент Text для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="e60bb-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e60bb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e60bb-125">Задает дополнительный текст для данных, отображаемых элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e60bb-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e60bb-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e60bb-126">Parent Elements</span></span>

|<span data-ttu-id="e60bb-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="e60bb-127">Element</span></span>|<span data-ttu-id="e60bb-128">Description</span><span class="sxs-lookup"><span data-stu-id="e60bb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e60bb-129">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="e60bb-130">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e60bb-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e60bb-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="e60bb-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e60bb-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="e60bb-132">See Also</span></span>

[<span data-ttu-id="e60bb-133">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="e60bb-134">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="e60bb-135">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="e60bb-136">Элемент NewLine для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="e60bb-137">Элемент Text для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e60bb-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="e60bb-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e60bb-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
