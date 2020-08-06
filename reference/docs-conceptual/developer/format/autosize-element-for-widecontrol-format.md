---
title: Элемент AutoSize для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 64e62142738916978b37eb1cd3a73536b0447099
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783880"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="89f97-102">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89f97-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="89f97-103">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="89f97-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="89f97-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) AutoSize для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="89f97-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89f97-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89f97-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89f97-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89f97-106">Attributes and Elements</span></span>

<span data-ttu-id="89f97-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `AutoSize` элемента.</span><span class="sxs-lookup"><span data-stu-id="89f97-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89f97-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89f97-108">Attributes</span></span>

<span data-ttu-id="89f97-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89f97-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89f97-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89f97-110">Child Elements</span></span>

<span data-ttu-id="89f97-111">Нет</span><span class="sxs-lookup"><span data-stu-id="89f97-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="89f97-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89f97-112">Parent Elements</span></span>

|<span data-ttu-id="89f97-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="89f97-113">Element</span></span>|<span data-ttu-id="89f97-114">Description</span><span class="sxs-lookup"><span data-stu-id="89f97-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89f97-115">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89f97-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="89f97-116">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="89f97-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89f97-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="89f97-117">Remarks</span></span>

<span data-ttu-id="89f97-118">При определении расширенного представления можно добавить `AutoSize` элемент или элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) , но нельзя добавить оба элемента.</span><span class="sxs-lookup"><span data-stu-id="89f97-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="89f97-119">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="89f97-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="89f97-120">Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="89f97-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89f97-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="89f97-121">See Also</span></span>

[<span data-ttu-id="89f97-122">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89f97-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="89f97-123">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="89f97-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="89f97-124">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89f97-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="89f97-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="89f97-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
