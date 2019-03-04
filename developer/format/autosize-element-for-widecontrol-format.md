---
title: AutoSize-элемент для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857090"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="319fe-102">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="319fe-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="319fe-103">Указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.</span><span class="sxs-lookup"><span data-stu-id="319fe-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="319fe-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) Autosize элемент конфигурации для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="319fe-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="319fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="319fe-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="319fe-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="319fe-106">Attributes and Elements</span></span>

<span data-ttu-id="319fe-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `AutoSize` элемент.</span><span class="sxs-lookup"><span data-stu-id="319fe-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="319fe-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="319fe-108">Attributes</span></span>

<span data-ttu-id="319fe-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="319fe-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="319fe-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="319fe-110">Child Elements</span></span>

<span data-ttu-id="319fe-111">Нет</span><span class="sxs-lookup"><span data-stu-id="319fe-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="319fe-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="319fe-112">Parent Elements</span></span>

|<span data-ttu-id="319fe-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="319fe-113">Element</span></span>|<span data-ttu-id="319fe-114">Описание</span><span class="sxs-lookup"><span data-stu-id="319fe-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="319fe-115">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="319fe-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="319fe-116">Большое (значение одно значение) определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="319fe-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="319fe-117">Замечания</span><span class="sxs-lookup"><span data-stu-id="319fe-117">Remarks</span></span>

<span data-ttu-id="319fe-118">При определении широкое представление, можно добавить `AutoSize` элемент или [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) элемент, но нельзя добавить одновременно.</span><span class="sxs-lookup"><span data-stu-id="319fe-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="319fe-119">Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="319fe-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="319fe-120">Пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="319fe-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="319fe-121">См. также</span><span class="sxs-lookup"><span data-stu-id="319fe-121">See Also</span></span>

[<span data-ttu-id="319fe-122">ColumnNumber-элемент для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="319fe-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="319fe-123">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="319fe-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="319fe-124">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="319fe-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="319fe-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="319fe-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
