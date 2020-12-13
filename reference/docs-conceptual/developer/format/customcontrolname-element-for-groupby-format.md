---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomControlName для элемента GroupBy (формат)
description: Элемент CustomControlName для элемента GroupBy (формат)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655426"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="6f1ed-103">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-103">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="6f1ed-104">Задает имя пользовательского элемента управления, используемого для вывода новой группы.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-104">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="6f1ed-105">Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-105">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="6f1ed-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента представления (Format) Кустомконтролнаме в GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f1ed-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f1ed-107">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f1ed-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6f1ed-108">Attributes and Elements</span></span>

<span data-ttu-id="6f1ed-109">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomControlName` элемента.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-109">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f1ed-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f1ed-110">Attributes</span></span>

<span data-ttu-id="6f1ed-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f1ed-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f1ed-112">Child Elements</span></span>

<span data-ttu-id="6f1ed-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f1ed-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f1ed-114">Parent Elements</span></span>

|<span data-ttu-id="6f1ed-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f1ed-115">Element</span></span>|<span data-ttu-id="6f1ed-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6f1ed-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6f1ed-117">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-117">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="6f1ed-118">Определяет, как Windows PowerShell отображает новую группу объектов.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-118">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6f1ed-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="6f1ed-119">Text Value</span></span>

<span data-ttu-id="6f1ed-120">Укажите имя пользовательского элемента управления, используемого для вывода новой группы.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-120">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f1ed-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6f1ed-121">Remarks</span></span>

<span data-ttu-id="6f1ed-122">Можно создавать стандартные элементы управления, которые могут использоваться всеми представлениями файла форматирования, а также создавать элементы управления представления, которые могут использоваться в определенном представлении.</span><span class="sxs-lookup"><span data-stu-id="6f1ed-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="6f1ed-123">Следующие элементы определяют имена этих настраиваемых элементов управления:</span><span class="sxs-lookup"><span data-stu-id="6f1ed-123">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="6f1ed-124">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="6f1ed-125">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="6f1ed-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f1ed-126">See Also</span></span>

[<span data-ttu-id="6f1ed-127">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="6f1ed-128">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-128">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="6f1ed-129">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6f1ed-129">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="6f1ed-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f1ed-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
