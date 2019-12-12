---
title: Элемент AutoSize для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369053"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="5c116-102">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5c116-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="5c116-103">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="5c116-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="5c116-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) AutoSize для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="5c116-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c116-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c116-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c116-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c116-106">Attributes and Elements</span></span>

<span data-ttu-id="5c116-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `AutoSize`.</span><span class="sxs-lookup"><span data-stu-id="5c116-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c116-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c116-108">Attributes</span></span>

<span data-ttu-id="5c116-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="5c116-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c116-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c116-110">Child Elements</span></span>

<span data-ttu-id="5c116-111">Нет</span><span class="sxs-lookup"><span data-stu-id="5c116-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5c116-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c116-112">Parent Elements</span></span>

|<span data-ttu-id="5c116-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c116-113">Element</span></span>|<span data-ttu-id="5c116-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5c116-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c116-115">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="5c116-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="5c116-116">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="5c116-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5c116-117">Замечания</span><span class="sxs-lookup"><span data-stu-id="5c116-117">Remarks</span></span>

<span data-ttu-id="5c116-118">При определении расширенного представления можно добавить элемент `AutoSize` или элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) , но нельзя добавить и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="5c116-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="5c116-119">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="5c116-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="5c116-120">Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="5c116-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c116-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c116-121">See Also</span></span>

[<span data-ttu-id="5c116-122">Элемент ColumnNumber для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="5c116-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="5c116-123">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="5c116-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5c116-124">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="5c116-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="5c116-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c116-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
