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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856190"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="693db-102">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="693db-103">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="693db-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="693db-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="693db-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="693db-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="693db-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="693db-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="693db-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="693db-107">Attributes and Elements</span></span>

<span data-ttu-id="693db-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="693db-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="693db-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="693db-109">Attributes</span></span>

<span data-ttu-id="693db-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="693db-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="693db-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="693db-111">Child Elements</span></span>

|<span data-ttu-id="693db-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="693db-112">Element</span></span>|<span data-ttu-id="693db-113">Описание</span><span class="sxs-lookup"><span data-stu-id="693db-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="693db-114">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="693db-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="693db-115">Optional element.</span></span><br /><br /> <span data-ttu-id="693db-116">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="693db-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="693db-117">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="693db-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="693db-118">Optional element.</span></span><br /><br /> <span data-ttu-id="693db-119">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="693db-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="693db-120">Элемент новой строки для CustomItem для пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="693db-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="693db-121">Optional element.</span></span><br /><br /> <span data-ttu-id="693db-122">Добавляет пустой строки для отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="693db-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="693db-123">Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="693db-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="693db-124">Optional element.</span></span><br /><br /> <span data-ttu-id="693db-125">Задает дополнительный текст для данных, отображаемых элементом управления.</span><span class="sxs-lookup"><span data-stu-id="693db-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="693db-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="693db-126">Parent Elements</span></span>

|<span data-ttu-id="693db-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="693db-127">Element</span></span>|<span data-ttu-id="693db-128">Описание</span><span class="sxs-lookup"><span data-stu-id="693db-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="693db-129">Элемент CustomEntry для CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="693db-130">Предоставляет определение пользовательского элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="693db-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="693db-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="693db-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="693db-132">См. также</span><span class="sxs-lookup"><span data-stu-id="693db-132">See Also</span></span>

[<span data-ttu-id="693db-133">Элемент CustomEntry для CustomEntries для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="693db-134">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="693db-135">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="693db-136">Элемент новой строки для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="693db-137">Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="693db-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="693db-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="693db-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
