---
title: Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860370"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="38322-102">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="38322-103">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="38322-103">Provides a definition of the control.</span></span> <span data-ttu-id="38322-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="38322-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="38322-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="38322-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38322-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="38322-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38322-107">Attributes and Elements</span></span>

<span data-ttu-id="38322-108">В следующих разделах атрибуты, дочерние и родительские элементы из `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="38322-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="38322-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38322-109">Attributes</span></span>

<span data-ttu-id="38322-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="38322-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="38322-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38322-111">Child Elements</span></span>

|<span data-ttu-id="38322-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="38322-112">Element</span></span>|<span data-ttu-id="38322-113">Описание</span><span class="sxs-lookup"><span data-stu-id="38322-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38322-114">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="38322-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="38322-115">Optional element.</span></span><br /><br /> <span data-ttu-id="38322-116">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="38322-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="38322-117">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="38322-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="38322-118">Required element.</span></span><br /><br /> <span data-ttu-id="38322-119">Определяет порядок отображения данных.</span><span class="sxs-lookup"><span data-stu-id="38322-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="38322-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38322-120">Parent Elements</span></span>

|<span data-ttu-id="38322-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="38322-121">Element</span></span>|<span data-ttu-id="38322-122">Описание</span><span class="sxs-lookup"><span data-stu-id="38322-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38322-123">Элемент CustomEntries для пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="38322-124">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="38322-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="38322-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="38322-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="38322-126">См. также</span><span class="sxs-lookup"><span data-stu-id="38322-126">See Also</span></span>

[<span data-ttu-id="38322-127">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="38322-128">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="38322-129">Элемент CustomEntries для пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="38322-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="38322-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="38322-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
