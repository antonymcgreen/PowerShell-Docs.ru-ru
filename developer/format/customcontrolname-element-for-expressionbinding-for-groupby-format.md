---
title: Элемент CustomControlName для ExpressionBinding для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e11da8f-1e75-4d3d-b4c8-b500dec3028e
caps.latest.revision: 6
ms.openlocfilehash: 32f8a71e9818c8c1a052f3b96f442f169c1bda4a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854300"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="741ed-102">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="741ed-103">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="741ed-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="741ed-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="741ed-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="741ed-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem элемента CustomControlName GroupBy (формат) для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="741ed-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="741ed-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="741ed-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="741ed-107">Attributes and Elements</span></span>

<span data-ttu-id="741ed-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControlName` элемент.</span><span class="sxs-lookup"><span data-stu-id="741ed-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="741ed-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="741ed-109">Attributes</span></span>

<span data-ttu-id="741ed-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="741ed-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="741ed-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="741ed-111">Child Elements</span></span>

<span data-ttu-id="741ed-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="741ed-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="741ed-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="741ed-113">Parent Elements</span></span>

|<span data-ttu-id="741ed-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="741ed-114">Element</span></span>|<span data-ttu-id="741ed-115">Описание</span><span class="sxs-lookup"><span data-stu-id="741ed-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="741ed-116">Элемент ExpressionBinding для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="741ed-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="741ed-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="741ed-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="741ed-118">Text Value</span></span>

<span data-ttu-id="741ed-119">Укажите имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="741ed-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="741ed-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="741ed-120">Remarks</span></span>

<span data-ttu-id="741ed-121">Можно создавать стандартные элементы управления, которые могут использоваться все представления файл форматирования, и можно создать элементы управления представления, которые могут использоваться по определенному представлению.</span><span class="sxs-lookup"><span data-stu-id="741ed-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="741ed-122">Следующие элементы укажите имена этих элементов управления:</span><span class="sxs-lookup"><span data-stu-id="741ed-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="741ed-123">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="741ed-124">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="741ed-125">См. также</span><span class="sxs-lookup"><span data-stu-id="741ed-125">See Also</span></span>

[<span data-ttu-id="741ed-126">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="741ed-127">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="741ed-128">Элемент ExpressionBinding для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="741ed-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="741ed-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="741ed-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
