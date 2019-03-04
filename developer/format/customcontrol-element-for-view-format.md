---
title: Элемент пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861260"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="9e9f2-102">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="9e9f2-103">Определяет формат для представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="9e9f2-104">Элемент элемента (формат) пользовательский элемент управления для элемента (формат) элемент ViewDefinitions (формат) конфигурации представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e9f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e9f2-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e9f2-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e9f2-106">Attributes and Elements</span></span>

<span data-ttu-id="9e9f2-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControl` элемент.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="9e9f2-108">Необходимо указать один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e9f2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e9f2-109">Attributes</span></span>

<span data-ttu-id="9e9f2-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e9f2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e9f2-111">Child Elements</span></span>

|<span data-ttu-id="9e9f2-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e9f2-112">Element</span></span>|<span data-ttu-id="9e9f2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9e9f2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e9f2-114">Элемент CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="9e9f2-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-115">Required element.</span></span><br /><br /> <span data-ttu-id="9e9f2-116">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9e9f2-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e9f2-117">Parent Elements</span></span>

|<span data-ttu-id="9e9f2-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e9f2-118">Element</span></span>|<span data-ttu-id="9e9f2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9e9f2-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e9f2-120">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9e9f2-121">Определяет представление, которое используется для отображения один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e9f2-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="9e9f2-122">Remarks</span></span>

<span data-ttu-id="9e9f2-123">В большинстве случаев только одно определение является обязательным для каждого элемента управления представления, но можно указать несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="9e9f2-124">В таком случае можно задать отдельный определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="9e9f2-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e9f2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9e9f2-125">See Also</span></span>

[<span data-ttu-id="9e9f2-126">Элемент CustomEntries для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9e9f2-127">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9e9f2-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="9e9f2-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e9f2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
