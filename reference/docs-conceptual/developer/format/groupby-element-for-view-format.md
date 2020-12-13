---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент GroupBy для элемента View (формат)
description: Элемент GroupBy для элемента View (формат)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652103"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="df091-103">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-103">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="df091-104">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="df091-104">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="df091-105">Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="df091-105">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="df091-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="df091-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df091-107">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="df091-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df091-108">Attributes and Elements</span></span>

<span data-ttu-id="df091-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="df091-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="df091-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df091-110">Attributes</span></span>

<span data-ttu-id="df091-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="df091-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="df091-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df091-112">Child Elements</span></span>

|<span data-ttu-id="df091-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="df091-113">Element</span></span>|<span data-ttu-id="df091-114">Описание</span><span class="sxs-lookup"><span data-stu-id="df091-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df091-115">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-115">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="df091-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df091-116">Optional element.</span></span><br /><br /> <span data-ttu-id="df091-117">Определяет пользовательский элемент управления, отображающий новые группы.</span><span class="sxs-lookup"><span data-stu-id="df091-117">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="df091-118">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-118">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="df091-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df091-119">Optional element.</span></span><br /><br /> <span data-ttu-id="df091-120">Задает имя элемента управления, используемого для вывода новой группы.</span><span class="sxs-lookup"><span data-stu-id="df091-120">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="df091-121">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-121">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="df091-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df091-122">Optional element.</span></span><br /><br /> <span data-ttu-id="df091-123">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="df091-123">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="df091-124">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-124">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="df091-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df091-125">Optional element.</span></span><br /><br /> <span data-ttu-id="df091-126">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="df091-126">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="df091-127">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="df091-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df091-128">Optional element.</span></span><br /><br /> <span data-ttu-id="df091-129">Задает скрипт, запускающий новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="df091-129">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="df091-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df091-130">Parent Elements</span></span>

|<span data-ttu-id="df091-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="df091-131">Element</span></span>|<span data-ttu-id="df091-132">Описание</span><span class="sxs-lookup"><span data-stu-id="df091-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df091-133">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-133">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="df091-134">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="df091-134">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="df091-135">Комментарии</span><span class="sxs-lookup"><span data-stu-id="df091-135">Remarks</span></span>

<span data-ttu-id="df091-136">При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="df091-136">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="df091-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="df091-137">See Also</span></span>

[<span data-ttu-id="df091-138">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-138">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="df091-139">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-139">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="df091-140">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-140">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="df091-141">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-141">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="df091-142">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="df091-142">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="df091-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="df091-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
