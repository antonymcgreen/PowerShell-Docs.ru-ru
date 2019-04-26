---
title: Элемент CustomEntry для CustomEntries для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066453"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="825f0-102">Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="825f0-103">Предоставляет определение пользовательского элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="825f0-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="825f0-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="825f0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="825f0-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="825f0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="825f0-106">Attributes and Elements</span></span>

<span data-ttu-id="825f0-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="825f0-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="825f0-108">Необходимо указать элементы, отображаемые с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="825f0-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="825f0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="825f0-109">Attributes</span></span>

<span data-ttu-id="825f0-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="825f0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="825f0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="825f0-111">Child Elements</span></span>

|<span data-ttu-id="825f0-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="825f0-112">Element</span></span>|<span data-ttu-id="825f0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="825f0-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="825f0-114">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="825f0-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="825f0-115">Optional element.</span></span><br /><br /> <span data-ttu-id="825f0-116">Определяет типы .NET, использующих определение представления пользовательского элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="825f0-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="825f0-117">Элемент CustomItem для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="825f0-118">Определяет элемент управления для определения пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="825f0-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="825f0-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="825f0-119">Parent Elements</span></span>

|<span data-ttu-id="825f0-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="825f0-120">Element</span></span>|<span data-ttu-id="825f0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="825f0-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="825f0-122">Элемент CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="825f0-123">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="825f0-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="825f0-124">Представление пользовательского элемента управления необходимо указать одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="825f0-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="825f0-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="825f0-125">Remarks</span></span>

<span data-ttu-id="825f0-126">В большинстве случаев для каждого представления пользовательского элемента управления требуется только одно определение, но можно иметь несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="825f0-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="825f0-127">В таком случае можно задать отдельный определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="825f0-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="825f0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="825f0-128">See Also</span></span>

[<span data-ttu-id="825f0-129">Элемент пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="825f0-130">Элемент CustomItem для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="825f0-131">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="825f0-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="825f0-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="825f0-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
