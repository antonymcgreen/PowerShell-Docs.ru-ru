---
title: Рамку элемента для CustomItem пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054787"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="a6f87-102">Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a6f87-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="a6f87-103">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="a6f87-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="a6f87-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6f87-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="a6f87-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry CustomControlView (формат) элемента фрейма для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a6f87-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a6f87-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6f87-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a6f87-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6f87-107">Attributes and Elements</span></span>

<span data-ttu-id="a6f87-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6f87-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6f87-109">Attributes</span></span>

<span data-ttu-id="a6f87-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="a6f87-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6f87-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6f87-111">Child Elements</span></span>

|<span data-ttu-id="a6f87-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6f87-112">Element</span></span>|<span data-ttu-id="a6f87-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a6f87-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="a6f87-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="a6f87-114">Required Element</span></span>|
|[<span data-ttu-id="a6f87-115">Элемент FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="a6f87-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="a6f87-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f87-117">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="a6f87-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="a6f87-118">Элемент FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="a6f87-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f87-120">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="a6f87-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="a6f87-121">Элемент LeftIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="a6f87-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-122">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f87-123">Указывает количество символов, данные сдвигается от левого поля.</span><span class="sxs-lookup"><span data-stu-id="a6f87-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="a6f87-124">Элемент RightIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="a6f87-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-125">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f87-126">Указывает количество символов, данные сдвигается от правого поля.</span><span class="sxs-lookup"><span data-stu-id="a6f87-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a6f87-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6f87-127">Parent Elements</span></span>

|<span data-ttu-id="a6f87-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6f87-128">Element</span></span>|<span data-ttu-id="a6f87-129">Описание</span><span class="sxs-lookup"><span data-stu-id="a6f87-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6f87-130">Элемент CustomItem для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a6f87-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="a6f87-131">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="a6f87-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a6f87-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="a6f87-132">Remarks</span></span>

<span data-ttu-id="a6f87-133">Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) элементы в одном `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="a6f87-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f87-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a6f87-134">See Also</span></span>

[<span data-ttu-id="a6f87-135">Элемент FirstLineHanging</span><span class="sxs-lookup"><span data-stu-id="a6f87-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a6f87-136">Элемент FirstLineIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a6f87-137">Элемент LeftIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a6f87-138">Элемент RightIndent</span><span class="sxs-lookup"><span data-stu-id="a6f87-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a6f87-139">Элемент CustomItem для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a6f87-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a6f87-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6f87-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
