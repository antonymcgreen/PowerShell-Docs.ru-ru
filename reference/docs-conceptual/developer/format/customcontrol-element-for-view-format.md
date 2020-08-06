---
title: Элемент ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786056"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="0dc23-102">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="0dc23-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="0dc23-103">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="0dc23-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="0dc23-104">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="0dc23-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0dc23-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dc23-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0dc23-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0dc23-106">Attributes and Elements</span></span>

<span data-ttu-id="0dc23-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="0dc23-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="0dc23-108">Необходимо указать один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="0dc23-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0dc23-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0dc23-109">Attributes</span></span>

<span data-ttu-id="0dc23-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0dc23-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0dc23-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0dc23-111">Child Elements</span></span>

|<span data-ttu-id="0dc23-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0dc23-112">Element</span></span>|<span data-ttu-id="0dc23-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc23-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0dc23-114">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="0dc23-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="0dc23-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0dc23-115">Required element.</span></span><br /><br /> <span data-ttu-id="0dc23-116">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0dc23-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0dc23-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0dc23-117">Parent Elements</span></span>

|<span data-ttu-id="0dc23-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0dc23-118">Element</span></span>|<span data-ttu-id="0dc23-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc23-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0dc23-120">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="0dc23-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="0dc23-121">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="0dc23-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0dc23-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0dc23-122">Remarks</span></span>

<span data-ttu-id="0dc23-123">В большинстве случаев для каждого представления элемента управления требуется только одно определение, но можно предоставить несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="0dc23-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="0dc23-124">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="0dc23-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc23-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0dc23-125">See Also</span></span>

[<span data-ttu-id="0dc23-126">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="0dc23-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0dc23-127">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="0dc23-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="0dc23-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc23-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
