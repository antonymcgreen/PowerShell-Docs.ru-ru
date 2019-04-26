---
title: Элемент CustomEntry для CustomEntries для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066504"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="cd62e-102">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="cd62e-103">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cd62e-103">Provides a definition of the control.</span></span> <span data-ttu-id="cd62e-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="cd62e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cd62e-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cd62e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd62e-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cd62e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd62e-107">Attributes and Elements</span></span>

<span data-ttu-id="cd62e-108">В следующих разделах атрибуты, дочерние и родительские элементы из `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="cd62e-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cd62e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd62e-109">Attributes</span></span>

<span data-ttu-id="cd62e-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="cd62e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cd62e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd62e-111">Child Elements</span></span>

|<span data-ttu-id="cd62e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd62e-112">Element</span></span>|<span data-ttu-id="cd62e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cd62e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd62e-114">Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="cd62e-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cd62e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="cd62e-116">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="cd62e-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="cd62e-117">Элемент CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="cd62e-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cd62e-118">Required element.</span></span><br /><br /> <span data-ttu-id="cd62e-119">Определяет порядок отображения данных.</span><span class="sxs-lookup"><span data-stu-id="cd62e-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cd62e-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd62e-120">Parent Elements</span></span>

|<span data-ttu-id="cd62e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd62e-121">Element</span></span>|<span data-ttu-id="cd62e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cd62e-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd62e-123">Элемент CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="cd62e-124">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cd62e-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cd62e-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="cd62e-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="cd62e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cd62e-126">See Also</span></span>

[<span data-ttu-id="cd62e-127">Элемент CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="cd62e-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cd62e-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd62e-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
