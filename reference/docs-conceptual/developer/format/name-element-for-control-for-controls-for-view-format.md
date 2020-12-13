---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента Control для элемента Controls для элемента View (формат)
description: Элемент Name для элемента Control для элемента Controls для элемента View (формат)
ms.openlocfilehash: 52b7170777a35596767c34f2d58106dfa6479567
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666490"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="a6323-103">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a6323-103">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="a6323-104">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6323-104">Specifies the name of the control.</span></span>

<span data-ttu-id="a6323-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления для представления (формат) элемента управления для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="a6323-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a6323-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6323-106">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a6323-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6323-107">Attributes and Elements</span></span>

<span data-ttu-id="a6323-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="a6323-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6323-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6323-109">Attributes</span></span>

<span data-ttu-id="a6323-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a6323-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6323-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6323-111">Child Elements</span></span>

<span data-ttu-id="a6323-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a6323-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a6323-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6323-113">Parent Elements</span></span>

|<span data-ttu-id="a6323-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6323-114">Element</span></span>|<span data-ttu-id="a6323-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a6323-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6323-116">Элемент Control для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a6323-116">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="a6323-117">Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a6323-117">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a6323-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a6323-118">Text Value</span></span>

<span data-ttu-id="a6323-119">Укажите имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a6323-119">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6323-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a6323-120">Remarks</span></span>

<span data-ttu-id="a6323-121">Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a6323-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="a6323-122">При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a6323-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="a6323-123">При создании другого элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a6323-123">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="a6323-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6323-124">See Also</span></span>

[<span data-ttu-id="a6323-125">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a6323-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="a6323-126">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a6323-126">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="a6323-127">Элемент Control для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a6323-127">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="a6323-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6323-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
