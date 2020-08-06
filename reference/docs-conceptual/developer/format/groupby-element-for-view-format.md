---
title: Элемент GroupBy для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781432"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="f761b-102">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="f761b-103">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="f761b-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="f761b-104">Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f761b-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="f761b-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f761b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f761b-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f761b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f761b-107">Attributes and Elements</span></span>

<span data-ttu-id="f761b-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f761b-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f761b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f761b-109">Attributes</span></span>

<span data-ttu-id="f761b-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f761b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f761b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f761b-111">Child Elements</span></span>

|<span data-ttu-id="f761b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f761b-112">Element</span></span>|<span data-ttu-id="f761b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f761b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f761b-114">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="f761b-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f761b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f761b-116">Определяет пользовательский элемент управления, отображающий новые группы.</span><span class="sxs-lookup"><span data-stu-id="f761b-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="f761b-117">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="f761b-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f761b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f761b-119">Задает имя элемента управления, используемого для вывода новой группы.</span><span class="sxs-lookup"><span data-stu-id="f761b-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="f761b-120">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="f761b-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f761b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f761b-122">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="f761b-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="f761b-123">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="f761b-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f761b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="f761b-125">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="f761b-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="f761b-126">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="f761b-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f761b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="f761b-128">Задает скрипт, запускающий новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="f761b-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f761b-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f761b-129">Parent Elements</span></span>

|<span data-ttu-id="f761b-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="f761b-130">Element</span></span>|<span data-ttu-id="f761b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="f761b-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f761b-132">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="f761b-133">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="f761b-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f761b-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="f761b-134">Remarks</span></span>

<span data-ttu-id="f761b-135">При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f761b-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f761b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f761b-136">See Also</span></span>

[<span data-ttu-id="f761b-137">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="f761b-138">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="f761b-139">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="f761b-140">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="f761b-141">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="f761b-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="f761b-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f761b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
