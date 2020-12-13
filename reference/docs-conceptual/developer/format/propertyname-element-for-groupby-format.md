---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента GroupBy (формат)
description: Элемент PropertyName для элемента GroupBy (формат)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666150"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="b9a7d-103">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b9a7d-103">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="b9a7d-104">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-104">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="b9a7d-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (Format) PropertyName для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b9a7d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b9a7d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9a7d-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b9a7d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9a7d-107">Attributes and Elements</span></span>

<span data-ttu-id="b9a7d-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b9a7d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9a7d-109">Attributes</span></span>

<span data-ttu-id="b9a7d-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b9a7d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9a7d-111">Child Elements</span></span>

<span data-ttu-id="b9a7d-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b9a7d-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9a7d-113">Parent Elements</span></span>

|<span data-ttu-id="b9a7d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9a7d-114">Element</span></span>|<span data-ttu-id="b9a7d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b9a7d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b9a7d-116">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b9a7d-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="b9a7d-117">Определяет, как отображается группа объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b9a7d-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b9a7d-118">Text Value</span></span>

<span data-ttu-id="b9a7d-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9a7d-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b9a7d-120">Remarks</span></span>

<span data-ttu-id="b9a7d-121">Windows PowerShell запускает новую группу при каждом изменении значения этого свойства.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-121">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="b9a7d-122">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) для запуска новой группы.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-122">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="b9a7d-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b9a7d-123">Example</span></span>

<span data-ttu-id="b9a7d-124">В следующем примере показано, как запустить новую группу при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="b9a7d-124">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="b9a7d-125">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="b9a7d-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9a7d-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9a7d-126">See Also</span></span>

[<span data-ttu-id="b9a7d-127">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b9a7d-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="b9a7d-128">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b9a7d-128">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="b9a7d-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9a7d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
