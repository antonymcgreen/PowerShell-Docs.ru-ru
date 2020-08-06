---
title: Элемент ScriptBlock для Селектионкондитион для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d3506188d32ce85ad6345dc0d0866dd789a1f293
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785410"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="c6ec8-102">Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c6ec8-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="c6ec8-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c6ec8-104">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="c6ec8-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="c6ec8-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) ошибка customcontrol элемента для для с представления (Format) кустомитем для кустоментри для ошибка customcontrol для представления (Format) селектионкондитион для EntrySelectedBy для ошибка customcontrol для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="c6ec8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c6ec8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6ec8-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c6ec8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6ec8-108">Attributes and Elements</span></span>

<span data-ttu-id="c6ec8-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c6ec8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6ec8-110">Attributes</span></span>

<span data-ttu-id="c6ec8-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c6ec8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6ec8-112">Child Elements</span></span>

<span data-ttu-id="c6ec8-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c6ec8-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6ec8-114">Parent Elements</span></span>

|<span data-ttu-id="c6ec8-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6ec8-115">Element</span></span>|<span data-ttu-id="c6ec8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c6ec8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c6ec8-117">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c6ec8-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="c6ec8-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c6ec8-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c6ec8-119">Text Value</span></span>

<span data-ttu-id="c6ec8-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6ec8-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6ec8-121">Remarks</span></span>

<span data-ttu-id="c6ec8-122">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="c6ec8-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="c6ec8-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6ec8-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6ec8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ec8-124">See Also</span></span>

[<span data-ttu-id="c6ec8-125">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c6ec8-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="c6ec8-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6ec8-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
