---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e70e1555a8f2fe0d15d3e864d80d35527af81b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785393"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="1fe7a-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1fe7a-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="1fe7a-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="1fe7a-104">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="1fe7a-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1fe7a-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (Format) ентриселектедби для кустоментри for GroupBy (формат). элемент селектионкондитион для для EntrySelectedBy для SelectionCondition for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1fe7a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1fe7a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fe7a-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1fe7a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1fe7a-108">Attributes and Elements</span></span>

<span data-ttu-id="1fe7a-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1fe7a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1fe7a-110">Attributes</span></span>

<span data-ttu-id="1fe7a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1fe7a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1fe7a-112">Child Elements</span></span>

<span data-ttu-id="1fe7a-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1fe7a-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1fe7a-114">Parent Elements</span></span>

|<span data-ttu-id="1fe7a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="1fe7a-115">Element</span></span>|<span data-ttu-id="1fe7a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1fe7a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1fe7a-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1fe7a-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="1fe7a-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1fe7a-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1fe7a-119">Text Value</span></span>

<span data-ttu-id="1fe7a-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fe7a-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="1fe7a-121">Remarks</span></span>

<span data-ttu-id="1fe7a-122">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="1fe7a-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1fe7a-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1fe7a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1fe7a-124">See Also</span></span>

[<span data-ttu-id="1fe7a-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1fe7a-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="1fe7a-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fe7a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
