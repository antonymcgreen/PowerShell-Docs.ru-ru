---
title: Элемент Frame для Кустомитем элементов управления в конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781483"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="89d97-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="89d97-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="89d97-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="89d97-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="89d97-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="89d97-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления конфигурации (формат).</span><span class="sxs-lookup"><span data-stu-id="89d97-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89d97-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89d97-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89d97-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89d97-107">Attributes and Elements</span></span>

<span data-ttu-id="89d97-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="89d97-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89d97-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89d97-109">Attributes</span></span>

<span data-ttu-id="89d97-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89d97-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89d97-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89d97-111">Child Elements</span></span>

|<span data-ttu-id="89d97-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="89d97-112">Element</span></span>|<span data-ttu-id="89d97-113">Описание</span><span class="sxs-lookup"><span data-stu-id="89d97-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="89d97-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="89d97-114">Required Element</span></span>|
|[<span data-ttu-id="89d97-115">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="89d97-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d97-116">Optional element.</span></span><br /><br /> <span data-ttu-id="89d97-117">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="89d97-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="89d97-118">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="89d97-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d97-119">Optional element.</span></span><br /><br /> <span data-ttu-id="89d97-120">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="89d97-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="89d97-121">Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="89d97-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d97-122">Optional element.</span></span><br /><br /> <span data-ttu-id="89d97-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="89d97-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="89d97-124">Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="89d97-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d97-125">Optional element.</span></span><br /><br /> <span data-ttu-id="89d97-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="89d97-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="89d97-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89d97-127">Parent Elements</span></span>

|<span data-ttu-id="89d97-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="89d97-128">Element</span></span>|<span data-ttu-id="89d97-129">Описание</span><span class="sxs-lookup"><span data-stu-id="89d97-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89d97-130">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="89d97-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="89d97-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="89d97-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89d97-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="89d97-132">Remarks</span></span>

<span data-ttu-id="89d97-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="89d97-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="89d97-134">См. также</span><span class="sxs-lookup"><span data-stu-id="89d97-134">See Also</span></span>

[<span data-ttu-id="89d97-135">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="89d97-136">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="89d97-137">Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="89d97-138">Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="89d97-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="89d97-139">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="89d97-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="89d97-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="89d97-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
