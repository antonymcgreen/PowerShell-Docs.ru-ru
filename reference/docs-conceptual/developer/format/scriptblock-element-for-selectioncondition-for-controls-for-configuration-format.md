---
title: Элемент ScriptBlock для Селектионкондитион для элементов управления Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785444"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="8948d-102">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="8948d-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="8948d-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8948d-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="8948d-104">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="8948d-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="8948d-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="8948d-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="8948d-106">Элемент конфигурации (Format) контролирует элемент элемента управления конфигурации (Format) для элементов управления для элемента конфигурации (Format) ошибка customcontrol для элемента управления в элементе конфигурации (Format) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления в элементе конфигурации (Format) Селектионкондитион для Ентриселектедби для элементов управления для элемента конфигурации (Format) элемент ScriptBlock для SelectionCondition для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8948d-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8948d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8948d-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8948d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8948d-108">Attributes and Elements</span></span>

<span data-ttu-id="8948d-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="8948d-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8948d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8948d-110">Attributes</span></span>

<span data-ttu-id="8948d-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8948d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8948d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8948d-112">Child Elements</span></span>

<span data-ttu-id="8948d-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8948d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8948d-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8948d-114">Parent Elements</span></span>

|<span data-ttu-id="8948d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="8948d-115">Element</span></span>|<span data-ttu-id="8948d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8948d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8948d-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="8948d-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="8948d-118">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8948d-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8948d-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8948d-119">Text Value</span></span>

<span data-ttu-id="8948d-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="8948d-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="8948d-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="8948d-121">Remarks</span></span>

<span data-ttu-id="8948d-122">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="8948d-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="8948d-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8948d-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8948d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8948d-124">See Also</span></span>

[<span data-ttu-id="8948d-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="8948d-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="8948d-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8948d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
