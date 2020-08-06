---
title: Элемент Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a13e83ec941bed80eaab02e40131054432fcce00
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785886"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="ad677-102">Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ad677-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="ad677-103">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad677-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="ad677-104">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для Кустоментри представления (формат) Кустоментриес для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ad677-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad677-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad677-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad677-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad677-106">Attributes and Elements</span></span>

<span data-ttu-id="ad677-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="ad677-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="ad677-108">Необходимо указать элементы, отображаемые в определении.</span><span class="sxs-lookup"><span data-stu-id="ad677-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad677-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad677-109">Attributes</span></span>

<span data-ttu-id="ad677-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad677-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad677-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad677-111">Child Elements</span></span>

|<span data-ttu-id="ad677-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad677-112">Element</span></span>|<span data-ttu-id="ad677-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ad677-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad677-114">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad677-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="ad677-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ad677-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ad677-116">Определяет типы .NET, которые используют определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="ad677-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ad677-117">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad677-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="ad677-118">Определяет элемент управления для определения пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad677-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ad677-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad677-119">Parent Elements</span></span>

|<span data-ttu-id="ad677-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad677-120">Element</span></span>|<span data-ttu-id="ad677-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ad677-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad677-122">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ad677-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="ad677-123">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad677-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="ad677-124">В представлении пользовательского элемента управления должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="ad677-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ad677-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad677-125">Remarks</span></span>

<span data-ttu-id="ad677-126">В большинстве случаев для каждого представления пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="ad677-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="ad677-127">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="ad677-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad677-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ad677-128">See Also</span></span>

[<span data-ttu-id="ad677-129">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ad677-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="ad677-130">Элемент Кустомитем для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad677-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ad677-131">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad677-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ad677-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad677-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
