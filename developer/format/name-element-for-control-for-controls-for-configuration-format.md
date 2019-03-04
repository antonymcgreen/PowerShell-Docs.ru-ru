---
title: Имя элемента для элемента управления для элементов управления для Configuration (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860090"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="e3df3-102">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e3df3-103">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3df3-103">Specifies the name of the control.</span></span> <span data-ttu-id="e3df3-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="e3df3-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e3df3-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) имя для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3df3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3df3-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3df3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3df3-107">Attributes and Elements</span></span>

<span data-ttu-id="e3df3-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент.</span><span class="sxs-lookup"><span data-stu-id="e3df3-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3df3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3df3-109">Attributes</span></span>

<span data-ttu-id="e3df3-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e3df3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3df3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3df3-111">Child Elements</span></span>

<span data-ttu-id="e3df3-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e3df3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3df3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3df3-113">Parent Elements</span></span>

|<span data-ttu-id="e3df3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3df3-114">Element</span></span>|<span data-ttu-id="e3df3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e3df3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3df3-116">Элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="e3df3-117">Определяет общий элемент управления, который может использоваться все представления файла форматирования и имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e3df3-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3df3-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e3df3-118">Text Value</span></span>

<span data-ttu-id="e3df3-119">Укажите имя, которое используется для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e3df3-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3df3-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e3df3-120">Remarks</span></span>

<span data-ttu-id="e3df3-121">Имя, указанное здесь можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e3df3-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="e3df3-122">При создании таблицы, список, расширенный пользовательский элемент управления или представления, элемент управления можно задать с помощью следующих элемента: [GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="e3df3-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="e3df3-123">При создании другого общего элемента управления, этот элемент управления можно задать с помощью следующих элемента: [Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="e3df3-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="e3df3-124">При Создание элемента управления, который можно использовать представления, этот элемент управления можно указать в следующем элементе: [Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="e3df3-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="e3df3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e3df3-125">See Also</span></span>

[<span data-ttu-id="e3df3-126">Элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="e3df3-127">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e3df3-128">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="e3df3-129">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e3df3-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e3df3-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3df3-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
