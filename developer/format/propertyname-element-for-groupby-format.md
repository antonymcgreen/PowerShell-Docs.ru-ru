---
title: Элемент PropertyName для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075874"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="fba9d-102">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fba9d-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="fba9d-103">Задает свойство .NET, которая запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="fba9d-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="fba9d-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fba9d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fba9d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fba9d-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fba9d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fba9d-106">Attributes and Elements</span></span>

<span data-ttu-id="fba9d-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.</span><span class="sxs-lookup"><span data-stu-id="fba9d-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fba9d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fba9d-108">Attributes</span></span>

<span data-ttu-id="fba9d-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="fba9d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fba9d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fba9d-110">Child Elements</span></span>

<span data-ttu-id="fba9d-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="fba9d-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fba9d-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fba9d-112">Parent Elements</span></span>

|<span data-ttu-id="fba9d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="fba9d-113">Element</span></span>|<span data-ttu-id="fba9d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fba9d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fba9d-115">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fba9d-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="fba9d-116">Определяет порядок отображения группы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="fba9d-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fba9d-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="fba9d-117">Text Value</span></span>

<span data-ttu-id="fba9d-118">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="fba9d-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="fba9d-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="fba9d-119">Remarks</span></span>

<span data-ttu-id="fba9d-120">Windows PowerShell запускает новую группу, при каждом изменении значения этого свойства.</span><span class="sxs-lookup"><span data-stu-id="fba9d-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="fba9d-121">Если этот элемент указан, нельзя указать [ScriptBlock](./scriptblock-element-for-groupby-format.md) элемент, чтобы начать новую группу.</span><span class="sxs-lookup"><span data-stu-id="fba9d-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="fba9d-122">Пример</span><span class="sxs-lookup"><span data-stu-id="fba9d-122">Example</span></span>

<span data-ttu-id="fba9d-123">Приведенный ниже показано, как начать новую группу, при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="fba9d-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="fba9d-124">Например, полный файл форматирования, который содержит этот элемент, см. в разделе [широкое представление (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="fba9d-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fba9d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fba9d-125">See Also</span></span>

[<span data-ttu-id="fba9d-126">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fba9d-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="fba9d-127">Элемент ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fba9d-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="fba9d-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fba9d-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
