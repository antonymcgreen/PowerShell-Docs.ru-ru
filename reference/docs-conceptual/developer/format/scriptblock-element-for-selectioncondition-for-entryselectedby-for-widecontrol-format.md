---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787620"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="daeb3-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="daeb3-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="daeb3-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="daeb3-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="daeb3-104">При вычислении этого скрипта `true` выполняется условие, и используется расширенное определение записи.</span><span class="sxs-lookup"><span data-stu-id="daeb3-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="daeb3-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="daeb3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="daeb3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="daeb3-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="daeb3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="daeb3-107">Attributes and Elements</span></span>

<span data-ttu-id="daeb3-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="daeb3-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="daeb3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="daeb3-109">Attributes</span></span>

<span data-ttu-id="daeb3-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="daeb3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="daeb3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="daeb3-111">Child Elements</span></span>

<span data-ttu-id="daeb3-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="daeb3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="daeb3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="daeb3-113">Parent Elements</span></span>

|<span data-ttu-id="daeb3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="daeb3-114">Element</span></span>|<span data-ttu-id="daeb3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="daeb3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="daeb3-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="daeb3-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="daeb3-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="daeb3-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="daeb3-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="daeb3-118">Text Value</span></span>

<span data-ttu-id="daeb3-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="daeb3-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="daeb3-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="daeb3-120">Remarks</span></span>

<span data-ttu-id="daeb3-121">Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="daeb3-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="daeb3-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="daeb3-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="daeb3-123">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="daeb3-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="daeb3-124">См. также</span><span class="sxs-lookup"><span data-stu-id="daeb3-124">See Also</span></span>

[<span data-ttu-id="daeb3-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="daeb3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="daeb3-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="daeb3-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="daeb3-127">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="daeb3-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="daeb3-128">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="daeb3-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="daeb3-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="daeb3-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
