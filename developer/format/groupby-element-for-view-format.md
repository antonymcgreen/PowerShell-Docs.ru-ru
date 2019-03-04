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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859530"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="ee844-102">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="ee844-103">Определяет порядок отображения группу объектов.</span><span class="sxs-lookup"><span data-stu-id="ee844-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="ee844-104">Этот элемент используется при определении таблицы, список, представление ширину или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ee844-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="ee844-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee844-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee844-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee844-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ee844-107">Attributes and Elements</span></span>

<span data-ttu-id="ee844-108">Атрибуты, дочерние и родительские элементы в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ee844-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee844-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ee844-109">Attributes</span></span>

<span data-ttu-id="ee844-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="ee844-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee844-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ee844-111">Child Elements</span></span>

|<span data-ttu-id="ee844-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee844-112">Element</span></span>|<span data-ttu-id="ee844-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ee844-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee844-114">Пользовательский элемент управления-элемент для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="ee844-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee844-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ee844-116">Определяет пользовательский элемент управления, отображающие новые группы.</span><span class="sxs-lookup"><span data-stu-id="ee844-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="ee844-117">Элемент CustomControlName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="ee844-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee844-118">Optional element.</span></span><br /><br /> <span data-ttu-id="ee844-119">Задает имя элемента управления, который используется для отображения новой группы.</span><span class="sxs-lookup"><span data-stu-id="ee844-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="ee844-120">Элемент Label для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="ee844-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee844-121">Optional element.</span></span><br /><br /> <span data-ttu-id="ee844-122">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="ee844-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="ee844-123">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="ee844-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee844-124">Optional element.</span></span><br /><br /> <span data-ttu-id="ee844-125">Указывает свойство .NET, то начинается группу при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="ee844-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="ee844-126">Элемент ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="ee844-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee844-127">Optional element.</span></span><br /><br /> <span data-ttu-id="ee844-128">Указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="ee844-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ee844-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ee844-129">Parent Elements</span></span>

|<span data-ttu-id="ee844-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee844-130">Element</span></span>|<span data-ttu-id="ee844-131">Описание</span><span class="sxs-lookup"><span data-stu-id="ee844-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee844-132">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="ee844-133">Определяет представление, которое отображает один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="ee844-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ee844-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="ee844-134">Remarks</span></span>

<span data-ttu-id="ee844-135">При определении, как отображается группу объектов, необходимо указать свойство или скрипт, который запустит группы. Тем не менее нельзя одновременно задать.</span><span class="sxs-lookup"><span data-stu-id="ee844-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee844-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ee844-136">See Also</span></span>

[<span data-ttu-id="ee844-137">Элемент CustomControlName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="ee844-138">Элемент Label для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="ee844-139">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="ee844-140">Элемент ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="ee844-141">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee844-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="ee844-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee844-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
