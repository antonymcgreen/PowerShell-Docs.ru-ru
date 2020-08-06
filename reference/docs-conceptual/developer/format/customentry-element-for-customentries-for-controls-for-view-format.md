---
title: Элемент Кустоментри для Кустоментриес элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785903"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="b5b09-102">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b5b09-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="b5b09-103">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b5b09-103">Provides a definition of the control.</span></span> <span data-ttu-id="b5b09-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="b5b09-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b5b09-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol, для элемента Control элементов ActiveX (формат).</span><span class="sxs-lookup"><span data-stu-id="b5b09-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b5b09-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5b09-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b5b09-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b5b09-107">Attributes and Elements</span></span>

<span data-ttu-id="b5b09-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="b5b09-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b5b09-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b5b09-109">Attributes</span></span>

<span data-ttu-id="b5b09-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b5b09-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b5b09-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b5b09-111">Child Elements</span></span>

|<span data-ttu-id="b5b09-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5b09-112">Element</span></span>|<span data-ttu-id="b5b09-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b09-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b5b09-114">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b5b09-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="b5b09-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b5b09-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b5b09-116">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="b5b09-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="b5b09-117">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b5b09-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="b5b09-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b5b09-118">Required element.</span></span><br /><br /> <span data-ttu-id="b5b09-119">Определяет, как элемент управления отображает данные.</span><span class="sxs-lookup"><span data-stu-id="b5b09-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b5b09-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b5b09-120">Parent Elements</span></span>

|<span data-ttu-id="b5b09-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5b09-121">Element</span></span>|<span data-ttu-id="b5b09-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b09-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b5b09-123">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b5b09-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="b5b09-124">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b5b09-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b5b09-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5b09-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b5b09-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b5b09-126">See Also</span></span>

[<span data-ttu-id="b5b09-127">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b5b09-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b5b09-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5b09-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
