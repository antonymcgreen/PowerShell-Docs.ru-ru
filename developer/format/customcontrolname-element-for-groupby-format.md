---
title: Элемент CustomControlName для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860310"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="bf781-102">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="bf781-103">Задает имя пользовательского элемента управления, используемый для отображения новой группы.</span><span class="sxs-lookup"><span data-stu-id="bf781-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="bf781-104">Этот элемент используется при определении таблицы, список, расширенный пользовательский элемент управления или представлении.</span><span class="sxs-lookup"><span data-stu-id="bf781-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="bf781-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) CustomControlName GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf781-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf781-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf781-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf781-107">Attributes and Elements</span></span>

<span data-ttu-id="bf781-108">В следующих разделах атрибуты, дочерние элементы и родительские элементы из `CustomControlName` элемент.</span><span class="sxs-lookup"><span data-stu-id="bf781-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf781-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf781-109">Attributes</span></span>

<span data-ttu-id="bf781-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="bf781-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf781-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf781-111">Child Elements</span></span>

<span data-ttu-id="bf781-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="bf781-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bf781-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf781-113">Parent Elements</span></span>

|<span data-ttu-id="bf781-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf781-114">Element</span></span>|<span data-ttu-id="bf781-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bf781-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf781-116">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="bf781-117">Определяет, как Windows PowerShell отображает группу объектов.</span><span class="sxs-lookup"><span data-stu-id="bf781-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bf781-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="bf781-118">Text Value</span></span>

<span data-ttu-id="bf781-119">Укажите имя пользовательского элемента управления, который используется для отображения новой группы.</span><span class="sxs-lookup"><span data-stu-id="bf781-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf781-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="bf781-120">Remarks</span></span>

<span data-ttu-id="bf781-121">Можно создавать стандартные элементы управления, которые могут использоваться все представления файл форматирования, и можно создать элементы управления представления, которые могут использоваться по определенному представлению.</span><span class="sxs-lookup"><span data-stu-id="bf781-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="bf781-122">Следующие элементы укажите имена этих пользовательских элементов управления:</span><span class="sxs-lookup"><span data-stu-id="bf781-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="bf781-123">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="bf781-124">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="bf781-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bf781-125">See Also</span></span>

[<span data-ttu-id="bf781-126">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="bf781-127">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf781-128">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="bf781-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="bf781-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf781-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
