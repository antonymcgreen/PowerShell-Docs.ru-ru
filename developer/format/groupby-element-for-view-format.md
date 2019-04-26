---
title: GroupBy-элемент для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065549"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="d263d-102">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="d263d-103">Определяет порядок отображения группу объектов.</span><span class="sxs-lookup"><span data-stu-id="d263d-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="d263d-104">Этот элемент используется при определении таблицы, список, представление ширину или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d263d-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="d263d-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d263d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d263d-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d263d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d263d-107">Attributes and Elements</span></span>

<span data-ttu-id="d263d-108">Атрибуты, дочерние и родительские элементы в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d263d-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d263d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d263d-109">Attributes</span></span>

<span data-ttu-id="d263d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="d263d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d263d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d263d-111">Child Elements</span></span>

|<span data-ttu-id="d263d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d263d-112">Element</span></span>|<span data-ttu-id="d263d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d263d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d263d-114">Пользовательский элемент управления-элемент для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="d263d-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d263d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d263d-116">Определяет пользовательский элемент управления, отображающие новые группы.</span><span class="sxs-lookup"><span data-stu-id="d263d-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="d263d-117">Элемент CustomControlName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="d263d-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d263d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d263d-119">Задает имя элемента управления, который используется для отображения новой группы.</span><span class="sxs-lookup"><span data-stu-id="d263d-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="d263d-120">Элемент Label для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="d263d-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d263d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d263d-122">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="d263d-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="d263d-123">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="d263d-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d263d-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d263d-125">Указывает свойство .NET, то начинается группу при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="d263d-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="d263d-126">Элемент ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="d263d-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d263d-127">Optional element.</span></span><br /><br /> <span data-ttu-id="d263d-128">Указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="d263d-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d263d-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d263d-129">Parent Elements</span></span>

|<span data-ttu-id="d263d-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="d263d-130">Element</span></span>|<span data-ttu-id="d263d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="d263d-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d263d-132">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="d263d-133">Определяет представление, которое отображает один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="d263d-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d263d-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="d263d-134">Remarks</span></span>

<span data-ttu-id="d263d-135">При определении, как отображается группу объектов, необходимо указать свойство или скрипт, который запустит группы. Тем не менее нельзя одновременно задать.</span><span class="sxs-lookup"><span data-stu-id="d263d-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d263d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="d263d-136">See Also</span></span>

[<span data-ttu-id="d263d-137">Элемент CustomControlName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="d263d-138">Элемент Label для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="d263d-139">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="d263d-140">Элемент ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="d263d-141">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d263d-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="d263d-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d263d-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
