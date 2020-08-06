---
title: Элемент Кустоментриес для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785971"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="fbf74-102">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="fbf74-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="fbf74-103">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbf74-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="fbf74-104">В представлении пользовательского элемента управления должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="fbf74-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="fbf74-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fbf74-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fbf74-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbf74-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fbf74-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fbf74-107">Attributes and Elements</span></span>

<span data-ttu-id="fbf74-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControlEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="fbf74-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="fbf74-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="fbf74-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fbf74-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fbf74-110">Attributes</span></span>

<span data-ttu-id="fbf74-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fbf74-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fbf74-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fbf74-112">Child Elements</span></span>

|<span data-ttu-id="fbf74-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbf74-113">Element</span></span>|<span data-ttu-id="fbf74-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fbf74-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbf74-115">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="fbf74-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="fbf74-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fbf74-116">Required element.</span></span><br /><br /> <span data-ttu-id="fbf74-117">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbf74-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fbf74-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fbf74-118">Parent Elements</span></span>

|<span data-ttu-id="fbf74-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbf74-119">Element</span></span>|<span data-ttu-id="fbf74-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fbf74-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbf74-121">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="fbf74-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="fbf74-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="fbf74-122">Required element.</span></span><br /><br /> <span data-ttu-id="fbf74-123">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="fbf74-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fbf74-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbf74-124">Remarks</span></span>

<span data-ttu-id="fbf74-125">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="fbf74-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="fbf74-126">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="fbf74-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="fbf74-127">В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="fbf74-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf74-128">См. также</span><span class="sxs-lookup"><span data-stu-id="fbf74-128">See Also</span></span>

[<span data-ttu-id="fbf74-129">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="fbf74-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="fbf74-130">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="fbf74-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="fbf74-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbf74-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
