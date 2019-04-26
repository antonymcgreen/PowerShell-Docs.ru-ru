---
title: Имя элемента для элемента управления для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065110"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="1b896-102">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="1b896-103">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1b896-103">Specifies the name of the control.</span></span>

<span data-ttu-id="1b896-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемент конфигурации (формат) указывает элемент управления элемента (формат) для элементов управления для элемента имя представления (формат) для элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1b896-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b896-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1b896-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1b896-106">Attributes and Elements</span></span>

<span data-ttu-id="1b896-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент.</span><span class="sxs-lookup"><span data-stu-id="1b896-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1b896-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1b896-108">Attributes</span></span>

<span data-ttu-id="1b896-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="1b896-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1b896-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1b896-110">Child Elements</span></span>

<span data-ttu-id="1b896-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="1b896-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1b896-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1b896-112">Parent Elements</span></span>

|<span data-ttu-id="1b896-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b896-113">Element</span></span>|<span data-ttu-id="1b896-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1b896-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1b896-115">Элемент управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="1b896-116">Определяет элемент управления, который может использоваться представление и имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1b896-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1b896-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1b896-117">Text Value</span></span>

<span data-ttu-id="1b896-118">Укажите имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1b896-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b896-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="1b896-119">Remarks</span></span>

<span data-ttu-id="1b896-120">Имя, указанное здесь можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1b896-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="1b896-121">При создании таблицы, список, расширенный пользовательский элемент управления или представления, элемент управления можно задать с помощью следующих элемента: [GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="1b896-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="1b896-122">При создание другого элемента управления, можно использовать представление, этот элемент управления можно указать в следующем элементе: [Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="1b896-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="1b896-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1b896-123">See Also</span></span>

[<span data-ttu-id="1b896-124">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="1b896-125">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="1b896-126">Элемент управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1b896-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="1b896-127">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b896-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
