---
title: Элемент GroupBy для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363633"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="8ce48-102">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="8ce48-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="8ce48-103">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="8ce48-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="8ce48-104">Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8ce48-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="8ce48-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="8ce48-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ce48-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ce48-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8ce48-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ce48-107">Attributes and Elements</span></span>

<span data-ttu-id="8ce48-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ce48-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ce48-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ce48-109">Attributes</span></span>

<span data-ttu-id="8ce48-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="8ce48-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8ce48-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ce48-111">Child Elements</span></span>

|<span data-ttu-id="8ce48-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ce48-112">Element</span></span>|<span data-ttu-id="8ce48-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8ce48-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ce48-114">Элемент ошибка customcontrol для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="8ce48-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8ce48-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8ce48-116">Определяет пользовательский элемент управления, отображающий новые группы.</span><span class="sxs-lookup"><span data-stu-id="8ce48-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="8ce48-117">Элемент Кустомконтролнаме для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="8ce48-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8ce48-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8ce48-119">Задает имя элемента управления, используемого для вывода новой группы.</span><span class="sxs-lookup"><span data-stu-id="8ce48-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="8ce48-120">Элемент Label для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="8ce48-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8ce48-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8ce48-122">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="8ce48-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="8ce48-123">Элемент PropertyName для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="8ce48-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8ce48-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8ce48-125">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="8ce48-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="8ce48-126">Элемент ScriptBlock для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="8ce48-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8ce48-127">Optional element.</span></span><br /><br /> <span data-ttu-id="8ce48-128">Задает скрипт, запускающий новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="8ce48-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8ce48-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ce48-129">Parent Elements</span></span>

|<span data-ttu-id="8ce48-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ce48-130">Element</span></span>|<span data-ttu-id="8ce48-131">Описание</span><span class="sxs-lookup"><span data-stu-id="8ce48-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ce48-132">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="8ce48-133">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="8ce48-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8ce48-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="8ce48-134">Remarks</span></span>

<span data-ttu-id="8ce48-135">При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="8ce48-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ce48-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ce48-136">See Also</span></span>

[<span data-ttu-id="8ce48-137">Элемент Кустомконтролнаме для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="8ce48-138">Элемент Label для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="8ce48-139">Элемент PropertyName для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="8ce48-140">Элемент ScriptBlock для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="8ce48-141">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="8ce48-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="8ce48-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ce48-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
