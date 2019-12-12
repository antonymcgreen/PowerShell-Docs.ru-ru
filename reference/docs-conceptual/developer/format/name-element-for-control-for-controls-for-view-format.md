---
title: Элемент Name для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365103"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="df510-102">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="df510-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="df510-103">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="df510-103">Specifies the name of the control.</span></span>

<span data-ttu-id="df510-104">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления для представления (формат) элемента управления для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="df510-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="df510-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df510-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="df510-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df510-106">Attributes and Elements</span></span>

<span data-ttu-id="df510-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.</span><span class="sxs-lookup"><span data-stu-id="df510-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="df510-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df510-108">Attributes</span></span>

<span data-ttu-id="df510-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="df510-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="df510-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df510-110">Child Elements</span></span>

<span data-ttu-id="df510-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="df510-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="df510-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df510-112">Parent Elements</span></span>

|<span data-ttu-id="df510-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="df510-113">Element</span></span>|<span data-ttu-id="df510-114">Описание</span><span class="sxs-lookup"><span data-stu-id="df510-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df510-115">Элемент Control для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="df510-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="df510-116">Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="df510-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="df510-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="df510-117">Text Value</span></span>

<span data-ttu-id="df510-118">Укажите имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="df510-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="df510-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="df510-119">Remarks</span></span>

<span data-ttu-id="df510-120">Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="df510-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="df510-121">При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="df510-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="df510-122">При создании другого элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="df510-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="df510-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="df510-123">See Also</span></span>

[<span data-ttu-id="df510-124">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="df510-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="df510-125">Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="df510-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="df510-126">Элемент Control для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="df510-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="df510-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="df510-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
