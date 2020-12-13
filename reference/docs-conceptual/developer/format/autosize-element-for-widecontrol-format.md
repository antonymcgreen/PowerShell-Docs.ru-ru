---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент AutoSize для WideControl (формат)
description: Элемент AutoSize для WideControl (формат)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650007"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="55420-103">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="55420-103">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="55420-104">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="55420-104">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="55420-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) AutoSize для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="55420-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="55420-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55420-106">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="55420-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="55420-107">Attributes and Elements</span></span>

<span data-ttu-id="55420-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `AutoSize` элемента.</span><span class="sxs-lookup"><span data-stu-id="55420-108">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="55420-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="55420-109">Attributes</span></span>

<span data-ttu-id="55420-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="55420-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="55420-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="55420-111">Child Elements</span></span>

<span data-ttu-id="55420-112">Нет</span><span class="sxs-lookup"><span data-stu-id="55420-112">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="55420-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="55420-113">Parent Elements</span></span>

|<span data-ttu-id="55420-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="55420-114">Element</span></span>|<span data-ttu-id="55420-115">Описание</span><span class="sxs-lookup"><span data-stu-id="55420-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55420-116">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="55420-116">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="55420-117">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="55420-117">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="55420-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="55420-118">Remarks</span></span>

<span data-ttu-id="55420-119">При определении расширенного представления можно добавить `AutoSize` элемент или элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) , но нельзя добавить оба элемента.</span><span class="sxs-lookup"><span data-stu-id="55420-119">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="55420-120">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="55420-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="55420-121">Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="55420-121">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55420-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="55420-122">See Also</span></span>

[<span data-ttu-id="55420-123">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="55420-123">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="55420-124">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="55420-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="55420-125">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="55420-125">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="55420-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="55420-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
