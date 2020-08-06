---
title: Элемент Frame для Кустомитем для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781449"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="42848-102">Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="42848-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="42848-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="42848-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="42848-104">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="42848-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="42848-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) кустомитем для кустоментри для кустомконтролвиев (Format) элемент Frame для CustomItem for ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="42848-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="42848-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42848-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="42848-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42848-107">Attributes and Elements</span></span>

<span data-ttu-id="42848-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="42848-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="42848-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42848-109">Attributes</span></span>

<span data-ttu-id="42848-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="42848-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="42848-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42848-111">Child Elements</span></span>

|<span data-ttu-id="42848-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="42848-112">Element</span></span>|<span data-ttu-id="42848-113">Description</span><span class="sxs-lookup"><span data-stu-id="42848-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="42848-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="42848-114">Required Element</span></span>|
|[<span data-ttu-id="42848-115">Фирстлинехангинг, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="42848-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42848-116">Optional element.</span></span><br /><br /> <span data-ttu-id="42848-117">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="42848-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="42848-118">Фирстлинеиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="42848-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42848-119">Optional element.</span></span><br /><br /> <span data-ttu-id="42848-120">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="42848-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="42848-121">Лефтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="42848-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42848-122">Optional element.</span></span><br /><br /> <span data-ttu-id="42848-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="42848-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="42848-124">Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="42848-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42848-125">Optional element.</span></span><br /><br /> <span data-ttu-id="42848-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="42848-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="42848-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42848-127">Parent Elements</span></span>

|<span data-ttu-id="42848-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="42848-128">Element</span></span>|<span data-ttu-id="42848-129">Description</span><span class="sxs-lookup"><span data-stu-id="42848-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42848-130">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="42848-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="42848-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="42848-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="42848-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="42848-132">Remarks</span></span>

<span data-ttu-id="42848-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="42848-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="42848-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="42848-134">See Also</span></span>

[<span data-ttu-id="42848-135">Фирстлинехангинг, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42848-136">Фирстлинеиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42848-137">Лефтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42848-138">Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="42848-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42848-139">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="42848-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42848-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="42848-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
