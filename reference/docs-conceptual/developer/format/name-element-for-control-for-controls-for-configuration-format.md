---
title: Элемент Name для элемента управления для элементов управления Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362713"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="302dd-102">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="302dd-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="302dd-103">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="302dd-103">Specifies the name of the control.</span></span> <span data-ttu-id="302dd-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="302dd-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="302dd-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления (Format) Name для элемента Control (формат), для которого наследуется конфигурация (Format).</span><span class="sxs-lookup"><span data-stu-id="302dd-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="302dd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="302dd-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="302dd-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="302dd-107">Attributes and Elements</span></span>

<span data-ttu-id="302dd-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.</span><span class="sxs-lookup"><span data-stu-id="302dd-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="302dd-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="302dd-109">Attributes</span></span>

<span data-ttu-id="302dd-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="302dd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="302dd-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="302dd-111">Child Elements</span></span>

<span data-ttu-id="302dd-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="302dd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="302dd-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="302dd-113">Parent Elements</span></span>

|<span data-ttu-id="302dd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="302dd-114">Element</span></span>|<span data-ttu-id="302dd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="302dd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="302dd-116">Элемент Control для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="302dd-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="302dd-117">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="302dd-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="302dd-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="302dd-118">Text Value</span></span>

<span data-ttu-id="302dd-119">Укажите имя, используемое для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="302dd-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="302dd-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="302dd-120">Remarks</span></span>

<span data-ttu-id="302dd-121">Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="302dd-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="302dd-122">При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="302dd-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="302dd-123">При создании другого общего элемента управления этот элемент управления может быть задан следующим элементом: [ExpressionBinding элемент для кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) .</span><span class="sxs-lookup"><span data-stu-id="302dd-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="302dd-124">При создании элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="302dd-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="302dd-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="302dd-125">See Also</span></span>

[<span data-ttu-id="302dd-126">Элемент Control для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="302dd-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="302dd-127">Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="302dd-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="302dd-128">Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="302dd-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="302dd-129">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="302dd-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="302dd-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="302dd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
