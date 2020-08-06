---
title: Элемент Frame для элемента управления Кустомитем для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5ade36c183a026cb9001a2abbe91d31638a87108
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773459"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="4d123-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="4d123-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="4d123-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="4d123-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="4d123-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="4d123-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес View (формат). для элемента Ошибка customcontrol для представления (Format) Кустоментри для Кустоментриес для элементов управления для представления (Format) Кустомитем элемента для Кустоментри для элементов управления элемента Frame (формат) для Кустомитем для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4d123-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d123-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4d123-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d123-107">Attributes and Elements</span></span>

<span data-ttu-id="4d123-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="4d123-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4d123-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d123-109">Attributes</span></span>

<span data-ttu-id="4d123-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4d123-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4d123-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d123-111">Child Elements</span></span>

|<span data-ttu-id="4d123-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d123-112">Element</span></span>|<span data-ttu-id="4d123-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4d123-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="4d123-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="4d123-114">Required Element</span></span>|
|[<span data-ttu-id="4d123-115">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="4d123-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4d123-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4d123-117">Указывает, сколько знаков первая строка смещается влево.</span><span class="sxs-lookup"><span data-stu-id="4d123-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="4d123-118">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="4d123-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4d123-119">Optional element.</span></span><br /><br /> <span data-ttu-id="4d123-120">Указывает, сколько знаков первая строка смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="4d123-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="4d123-121">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="4d123-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4d123-122">Optional element.</span></span><br /><br /> <span data-ttu-id="4d123-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="4d123-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="4d123-124">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="4d123-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4d123-125">Optional element.</span></span><br /><br /> <span data-ttu-id="4d123-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="4d123-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4d123-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d123-127">Parent Elements</span></span>

|<span data-ttu-id="4d123-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d123-128">Element</span></span>|<span data-ttu-id="4d123-129">Описание</span><span class="sxs-lookup"><span data-stu-id="4d123-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4d123-130">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="4d123-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="4d123-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d123-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d123-132">Remarks</span></span>

<span data-ttu-id="4d123-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-view-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="4d123-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d123-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4d123-134">See Also</span></span>

[<span data-ttu-id="4d123-135">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="4d123-136">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="4d123-137">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="4d123-138">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="4d123-139">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4d123-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="4d123-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d123-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
