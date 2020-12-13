---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)
description: Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652180"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="8308a-103">Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="8308a-103">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="8308a-104">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="8308a-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="8308a-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8308a-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="8308a-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) кустомитем для кустоментри для кустомконтролвиев (Format) элемент Frame для CustomItem for ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="8308a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8308a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8308a-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8308a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8308a-108">Attributes and Elements</span></span>

<span data-ttu-id="8308a-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="8308a-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8308a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8308a-110">Attributes</span></span>

<span data-ttu-id="8308a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8308a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8308a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8308a-112">Child Elements</span></span>

|<span data-ttu-id="8308a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-113">Element</span></span>|<span data-ttu-id="8308a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8308a-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="8308a-115">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-115">Required Element</span></span>|
|[<span data-ttu-id="8308a-116">Фирстлинехангинг, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-116">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="8308a-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8308a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="8308a-118">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="8308a-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="8308a-119">Фирстлинеиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-119">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="8308a-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8308a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="8308a-121">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="8308a-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="8308a-122">Лефтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-122">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="8308a-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8308a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="8308a-124">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="8308a-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="8308a-125">Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-125">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="8308a-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8308a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="8308a-127">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="8308a-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8308a-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8308a-128">Parent Elements</span></span>

|<span data-ttu-id="8308a-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-129">Element</span></span>|<span data-ttu-id="8308a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="8308a-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8308a-131">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="8308a-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="8308a-132">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="8308a-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8308a-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8308a-133">Remarks</span></span>

<span data-ttu-id="8308a-134">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="8308a-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8308a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="8308a-135">See Also</span></span>

[<span data-ttu-id="8308a-136">Фирстлинехангинг, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-136">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8308a-137">Фирстлинеиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-137">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8308a-138">Лефтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-138">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8308a-139">Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="8308a-139">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8308a-140">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="8308a-140">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8308a-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8308a-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
