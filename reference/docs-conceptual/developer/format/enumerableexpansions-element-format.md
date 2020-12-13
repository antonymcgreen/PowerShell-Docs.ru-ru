---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EnumerableExpansions (формат)
description: Элемент EnumerableExpansions (формат)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660179"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="e30e0-103">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="e30e0-103">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="e30e0-104">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="e30e0-104">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="e30e0-105">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)</span><span class="sxs-lookup"><span data-stu-id="e30e0-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e30e0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e30e0-106">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e30e0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e30e0-107">Attributes and Elements</span></span>

<span data-ttu-id="e30e0-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемента.</span><span class="sxs-lookup"><span data-stu-id="e30e0-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="e30e0-109">Количество дочерних элементов, которые можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="e30e0-109">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="e30e0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e30e0-110">Attributes</span></span>

<span data-ttu-id="e30e0-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e30e0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e30e0-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e30e0-112">Child Elements</span></span>

|<span data-ttu-id="e30e0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="e30e0-113">Element</span></span>|<span data-ttu-id="e30e0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e30e0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e30e0-115">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="e30e0-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="e30e0-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e30e0-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e30e0-117">Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="e30e0-117">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e30e0-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e30e0-118">Parent Elements</span></span>

|<span data-ttu-id="e30e0-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e30e0-119">Element</span></span>|<span data-ttu-id="e30e0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e30e0-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e30e0-121">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="e30e0-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="e30e0-122">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="e30e0-122">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e30e0-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e30e0-123">Remarks</span></span>

<span data-ttu-id="e30e0-124">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e30e0-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="e30e0-125">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="e30e0-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="e30e0-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e30e0-126">See Also</span></span>

[<span data-ttu-id="e30e0-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e30e0-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
