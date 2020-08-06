---
title: Элемент Frame для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785767"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="d90ac-102">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="d90ac-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="d90ac-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="d90ac-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="d90ac-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d90ac-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри для кустомитем для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d90ac-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d90ac-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d90ac-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d90ac-107">Attributes and Elements</span></span>

<span data-ttu-id="d90ac-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="d90ac-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d90ac-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d90ac-109">Attributes</span></span>

<span data-ttu-id="d90ac-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d90ac-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d90ac-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d90ac-111">Child Elements</span></span>

|<span data-ttu-id="d90ac-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d90ac-112">Element</span></span>|<span data-ttu-id="d90ac-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d90ac-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="d90ac-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="d90ac-114">Required Element</span></span>|
|[<span data-ttu-id="d90ac-115">Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d90ac-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d90ac-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d90ac-117">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="d90ac-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="d90ac-118">Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d90ac-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d90ac-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d90ac-120">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="d90ac-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="d90ac-121">Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="d90ac-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d90ac-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d90ac-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="d90ac-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="d90ac-124">[Элемент ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="d90ac-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="d90ac-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d90ac-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d90ac-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="d90ac-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d90ac-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d90ac-127">Parent Elements</span></span>

|<span data-ttu-id="d90ac-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d90ac-128">Element</span></span>|<span data-ttu-id="d90ac-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d90ac-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d90ac-130">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="d90ac-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="d90ac-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d90ac-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d90ac-132">Remarks</span></span>

<span data-ttu-id="d90ac-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-groupby-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-groupby-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="d90ac-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d90ac-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d90ac-134">See Also</span></span>

[<span data-ttu-id="d90ac-135">Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d90ac-136">Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d90ac-137">Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d90ac-138">Элемент RightIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d90ac-139">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="d90ac-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="d90ac-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90ac-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
