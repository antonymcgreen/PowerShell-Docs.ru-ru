---
title: Элемент Frame для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362953"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="72597-102">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="72597-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="72597-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="72597-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="72597-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="72597-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="72597-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Кустомитем GroupBy для Кустоментри для GroupBy (Format) элемент Frame для Кустомитем для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="72597-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72597-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72597-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72597-107">Attributes and Elements</span></span>

<span data-ttu-id="72597-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Frame`.</span><span class="sxs-lookup"><span data-stu-id="72597-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="72597-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72597-109">Attributes</span></span>

<span data-ttu-id="72597-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="72597-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="72597-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72597-111">Child Elements</span></span>

|<span data-ttu-id="72597-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="72597-112">Element</span></span>|<span data-ttu-id="72597-113">Описание</span><span class="sxs-lookup"><span data-stu-id="72597-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="72597-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="72597-114">Required Element</span></span>|
|[<span data-ttu-id="72597-115">Элемент Фирстлинехангинг для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="72597-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="72597-116">Optional element.</span></span><br /><br /> <span data-ttu-id="72597-117">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="72597-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="72597-118">Элемент Фирстлинеиндент для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="72597-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="72597-119">Optional element.</span></span><br /><br /> <span data-ttu-id="72597-120">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="72597-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="72597-121">Элемент Лефтиндент для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="72597-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="72597-122">Optional element.</span></span><br /><br /> <span data-ttu-id="72597-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="72597-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="72597-124">[Элемент ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="72597-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="72597-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="72597-125">Optional element.</span></span><br /><br /> <span data-ttu-id="72597-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="72597-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="72597-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72597-127">Parent Elements</span></span>

|<span data-ttu-id="72597-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="72597-128">Element</span></span>|<span data-ttu-id="72597-129">Описание</span><span class="sxs-lookup"><span data-stu-id="72597-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72597-130">Элемент Кустомитем для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="72597-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="72597-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72597-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="72597-132">Remarks</span></span>

<span data-ttu-id="72597-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-groupby-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-groupby-format.md) в одном элементе `Frame`.</span><span class="sxs-lookup"><span data-stu-id="72597-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="72597-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="72597-134">See Also</span></span>

[<span data-ttu-id="72597-135">Элемент Фирстлинехангинг для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="72597-136">Элемент Фирстлинеиндент для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="72597-137">Элемент Лефтиндент для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="72597-138">Элемент Ригхтиндент для Frame для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="72597-139">Элемент Кустомитем для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="72597-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="72597-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="72597-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
