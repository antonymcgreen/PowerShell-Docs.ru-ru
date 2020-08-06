---
title: Элемент Name для элемента управления для элементов управления Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783540"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="fb5b0-102">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="fb5b0-103">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-103">Specifies the name of the control.</span></span> <span data-ttu-id="fb5b0-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="fb5b0-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления (Format) Name для элемента Control (формат), для которого наследуется конфигурация (Format).</span><span class="sxs-lookup"><span data-stu-id="fb5b0-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fb5b0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb5b0-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb5b0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fb5b0-107">Attributes and Elements</span></span>

<span data-ttu-id="fb5b0-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fb5b0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fb5b0-109">Attributes</span></span>

<span data-ttu-id="fb5b0-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fb5b0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fb5b0-111">Child Elements</span></span>

<span data-ttu-id="fb5b0-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fb5b0-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fb5b0-113">Parent Elements</span></span>

|<span data-ttu-id="fb5b0-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="fb5b0-114">Element</span></span>|<span data-ttu-id="fb5b0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fb5b0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb5b0-116">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="fb5b0-117">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fb5b0-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="fb5b0-118">Text Value</span></span>

<span data-ttu-id="fb5b0-119">Укажите имя, используемое для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb5b0-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb5b0-120">Remarks</span></span>

<span data-ttu-id="fb5b0-121">Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fb5b0-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="fb5b0-122">При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fb5b0-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="fb5b0-123">При создании другого общего элемента управления этот элемент управления может быть задан следующим элементом: [ExpressionBinding элемент для кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fb5b0-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="fb5b0-124">При создании элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .</span><span class="sxs-lookup"><span data-stu-id="fb5b0-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="fb5b0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fb5b0-125">See Also</span></span>

[<span data-ttu-id="fb5b0-126">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="fb5b0-127">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="fb5b0-128">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="fb5b0-129">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="fb5b0-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="fb5b0-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb5b0-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
