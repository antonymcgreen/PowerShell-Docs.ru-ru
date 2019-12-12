---
title: Элемент PropertyName для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362523"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="536ec-102">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="536ec-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="536ec-103">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="536ec-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="536ec-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (Format) PropertyName для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="536ec-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="536ec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="536ec-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="536ec-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="536ec-106">Attributes and Elements</span></span>

<span data-ttu-id="536ec-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="536ec-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="536ec-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="536ec-108">Attributes</span></span>

<span data-ttu-id="536ec-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="536ec-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="536ec-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="536ec-110">Child Elements</span></span>

<span data-ttu-id="536ec-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="536ec-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="536ec-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="536ec-112">Parent Elements</span></span>

|<span data-ttu-id="536ec-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="536ec-113">Element</span></span>|<span data-ttu-id="536ec-114">Описание</span><span class="sxs-lookup"><span data-stu-id="536ec-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="536ec-115">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="536ec-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="536ec-116">Определяет, как отображается группа объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="536ec-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="536ec-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="536ec-117">Text Value</span></span>

<span data-ttu-id="536ec-118">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="536ec-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="536ec-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="536ec-119">Remarks</span></span>

<span data-ttu-id="536ec-120">Windows PowerShell запускает новую группу при каждом изменении значения этого свойства.</span><span class="sxs-lookup"><span data-stu-id="536ec-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="536ec-121">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) для запуска новой группы.</span><span class="sxs-lookup"><span data-stu-id="536ec-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="536ec-122">Пример</span><span class="sxs-lookup"><span data-stu-id="536ec-122">Example</span></span>

<span data-ttu-id="536ec-123">В следующем примере показано, как запустить новую группу при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="536ec-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="536ec-124">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="536ec-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="536ec-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="536ec-125">See Also</span></span>

[<span data-ttu-id="536ec-126">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="536ec-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="536ec-127">Элемент ScriptBlock для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="536ec-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="536ec-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="536ec-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
