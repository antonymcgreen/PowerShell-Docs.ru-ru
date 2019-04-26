---
title: Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066419"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="3d693-102">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="3d693-103">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="3d693-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="3d693-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3d693-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3d693-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3d693-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d693-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3d693-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d693-107">Attributes and Elements</span></span>

<span data-ttu-id="3d693-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="3d693-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d693-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d693-109">Attributes</span></span>

<span data-ttu-id="3d693-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3d693-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3d693-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d693-111">Child Elements</span></span>

|<span data-ttu-id="3d693-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d693-112">Element</span></span>|<span data-ttu-id="3d693-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3d693-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d693-114">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d693-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d693-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3d693-116">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d693-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="3d693-117">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d693-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d693-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3d693-119">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="3d693-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="3d693-120">Элемент новой строки для CustomItem для пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d693-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d693-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3d693-122">Добавляет пустой строки для отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3d693-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="3d693-123">Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="3d693-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d693-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3d693-125">Задает дополнительный текст для данных, отображаемых элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d693-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3d693-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d693-126">Parent Elements</span></span>

|<span data-ttu-id="3d693-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d693-127">Element</span></span>|<span data-ttu-id="3d693-128">Описание</span><span class="sxs-lookup"><span data-stu-id="3d693-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d693-129">Элемент CustomEntry для CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d693-130">Предоставляет определение пользовательского элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="3d693-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3d693-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="3d693-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3d693-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3d693-132">See Also</span></span>

[<span data-ttu-id="3d693-133">Элемент CustomEntry для CustomEntries для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d693-134">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d693-135">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d693-136">Элемент новой строки для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d693-137">Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3d693-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="3d693-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d693-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
