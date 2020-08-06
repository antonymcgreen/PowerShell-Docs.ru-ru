---
title: Элемент ScriptBlock для Селектионкондитион элементов управления для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785427"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="d3dfd-102">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d3dfd-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="d3dfd-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="d3dfd-104">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="d3dfd-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d3dfd-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) Кустоментри элемент для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления представления (Format) элемент ScriptBlock для SelectionCondition для элементов управления View (формат)</span><span class="sxs-lookup"><span data-stu-id="d3dfd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d3dfd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3dfd-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3dfd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3dfd-108">Attributes and Elements</span></span>

<span data-ttu-id="d3dfd-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3dfd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3dfd-110">Attributes</span></span>

<span data-ttu-id="d3dfd-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3dfd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3dfd-112">Child Elements</span></span>

<span data-ttu-id="d3dfd-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3dfd-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3dfd-114">Parent Elements</span></span>

|<span data-ttu-id="d3dfd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3dfd-115">Element</span></span>|<span data-ttu-id="d3dfd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d3dfd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3dfd-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d3dfd-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d3dfd-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d3dfd-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d3dfd-119">Text Value</span></span>

<span data-ttu-id="d3dfd-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3dfd-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3dfd-121">Remarks</span></span>

<span data-ttu-id="d3dfd-122">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="d3dfd-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="d3dfd-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d3dfd-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3dfd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d3dfd-124">See Also</span></span>

[<span data-ttu-id="d3dfd-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d3dfd-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="d3dfd-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dfd-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
