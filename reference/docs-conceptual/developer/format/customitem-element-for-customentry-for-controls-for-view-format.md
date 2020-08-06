---
title: Элемент Кустомитем для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 747ea14e7118be62ebee00e7d80af2dccb5c8353
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785852"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="88062-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="88062-103">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="88062-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="88062-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="88062-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="88062-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес элемент для элементов управления для представления (Format) Кустоментри для Кустоментриес для элементов управления представления (формат) кустомитем для кустоментри для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88062-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88062-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88062-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88062-107">Attributes and Elements</span></span>

<span data-ttu-id="88062-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="88062-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="88062-109">Дополнительные сведения см. в подразделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="88062-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="88062-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88062-110">Attributes</span></span>

<span data-ttu-id="88062-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="88062-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88062-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88062-112">Child Elements</span></span>

|<span data-ttu-id="88062-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="88062-113">Element</span></span>|<span data-ttu-id="88062-114">Описание</span><span class="sxs-lookup"><span data-stu-id="88062-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88062-115">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="88062-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88062-116">Optional element.</span></span><br /><br /> <span data-ttu-id="88062-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="88062-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="88062-118">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="88062-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88062-119">Optional element.</span></span><br /><br /> <span data-ttu-id="88062-120">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="88062-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="88062-121">Элемент NewLine для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="88062-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88062-122">Optional element.</span></span><br /><br /> <span data-ttu-id="88062-123">Добавляет пустую строку к отображению элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88062-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="88062-124">Элемент Text для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="88062-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88062-125">Optional element.</span></span><br /><br /> <span data-ttu-id="88062-126">Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="88062-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="88062-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88062-127">Parent Elements</span></span>

|<span data-ttu-id="88062-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="88062-128">Element</span></span>|<span data-ttu-id="88062-129">Описание</span><span class="sxs-lookup"><span data-stu-id="88062-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88062-130">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="88062-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88062-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="88062-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="88062-132">Remarks</span></span>

<span data-ttu-id="88062-133">При указании дочерних элементов `CustomItem` элемента учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="88062-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="88062-134">Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding` , `NewLine` , `Text` и `Frame` .</span><span class="sxs-lookup"><span data-stu-id="88062-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="88062-135">Максимальное число последовательностей, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="88062-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="88062-136">В каждой последовательности не существует максимального ограничения на количество `ExpressionBinding` элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="88062-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="88062-137">См. также</span><span class="sxs-lookup"><span data-stu-id="88062-137">See Also</span></span>

[<span data-ttu-id="88062-138">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="88062-139">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="88062-140">Элемент NewLine для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="88062-141">Элемент Text для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="88062-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="88062-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="88062-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
