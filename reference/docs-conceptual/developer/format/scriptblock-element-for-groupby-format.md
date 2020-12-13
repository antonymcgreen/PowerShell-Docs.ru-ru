---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента GroupBy (формат)
description: Элемент ScriptBlock для элемента GroupBy (формат)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665247"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="db0e2-103">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="db0e2-103">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="db0e2-104">Задает скрипт, запускающий новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="db0e2-104">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="db0e2-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента ScriptBlock представления (Format) для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="db0e2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db0e2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db0e2-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db0e2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db0e2-107">Attributes and Elements</span></span>

<span data-ttu-id="db0e2-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="db0e2-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db0e2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db0e2-109">Attributes</span></span>

<span data-ttu-id="db0e2-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db0e2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db0e2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db0e2-111">Child Elements</span></span>

<span data-ttu-id="db0e2-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db0e2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db0e2-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db0e2-113">Parent Elements</span></span>

|<span data-ttu-id="db0e2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="db0e2-114">Element</span></span>|<span data-ttu-id="db0e2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="db0e2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db0e2-116">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="db0e2-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="db0e2-117">Определяет, как отображается группа объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="db0e2-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db0e2-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="db0e2-118">Text Value</span></span>

<span data-ttu-id="db0e2-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="db0e2-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="db0e2-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="db0e2-120">Remarks</span></span>

<span data-ttu-id="db0e2-121">PowerShell запускает новую группу при каждом изменении значения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="db0e2-121">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="db0e2-122">Если этот элемент указан, нельзя указать элемент [PropertyName](propertyname-element-for-groupby-format.md) для запуска новой группы.</span><span class="sxs-lookup"><span data-stu-id="db0e2-122">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="db0e2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="db0e2-123">See Also</span></span>

[<span data-ttu-id="db0e2-124">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="db0e2-124">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="db0e2-125">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="db0e2-125">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="db0e2-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="db0e2-126">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
