---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)
description: Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666507"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="7d040-103">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-103">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7d040-104">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d040-104">Specifies the name of the control.</span></span> <span data-ttu-id="7d040-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="7d040-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7d040-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления (Format) Name для элемента Control (формат), для которого наследуется конфигурация (Format).</span><span class="sxs-lookup"><span data-stu-id="7d040-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d040-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d040-107">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d040-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7d040-108">Attributes and Elements</span></span>

<span data-ttu-id="7d040-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="7d040-109">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d040-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d040-110">Attributes</span></span>

<span data-ttu-id="7d040-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d040-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d040-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d040-112">Child Elements</span></span>

<span data-ttu-id="7d040-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d040-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d040-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d040-114">Parent Elements</span></span>

|<span data-ttu-id="7d040-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d040-115">Element</span></span>|<span data-ttu-id="7d040-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7d040-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d040-117">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-117">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="7d040-118">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7d040-118">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d040-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7d040-119">Text Value</span></span>

<span data-ttu-id="7d040-120">Укажите имя, используемое для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7d040-120">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d040-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7d040-121">Remarks</span></span>

<span data-ttu-id="7d040-122">Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7d040-122">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="7d040-123">При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="7d040-123">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="7d040-124">При создании другого общего элемента управления этот элемент управления может быть задан следующим элементом: [ExpressionBinding элемент для кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) .</span><span class="sxs-lookup"><span data-stu-id="7d040-124">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="7d040-125">При создании элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="7d040-125">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="7d040-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d040-126">See Also</span></span>

[<span data-ttu-id="7d040-127">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="7d040-128">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="7d040-129">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="7d040-130">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="7d040-130">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="7d040-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d040-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
