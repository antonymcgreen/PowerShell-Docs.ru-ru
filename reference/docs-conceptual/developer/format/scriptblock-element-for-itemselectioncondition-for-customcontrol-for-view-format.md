---
title: Элемент ScriptBlock для Итемселектионкондитион для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 31873e886af04f8eedaf859af1d6bc1d5bcfdbf7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772881"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="65898-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="65898-102">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="65898-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="65898-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="65898-104">При вычислении этого скрипта `true` выполняется условие, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="65898-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="65898-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65898-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="65898-106">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для элемента View (формат) Кустоментри для Кустоментриес для представления (Format) Кустомитем для Кустоментри для элемента ExpressionBinding представления (Format) для Кустомитем для ошибка customcontrol для элемента "View" ItemSelectionCondition в качестве привязывания выражения для ошибка customcontrol для представления (Format) элемент ScriptBlock для ItemSelectionCondition для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="65898-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65898-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65898-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65898-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65898-108">Attributes and Elements</span></span>

<span data-ttu-id="65898-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="65898-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="65898-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65898-110">Attributes</span></span>

<span data-ttu-id="65898-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="65898-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65898-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65898-112">Child Elements</span></span>

<span data-ttu-id="65898-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="65898-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="65898-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65898-114">Parent Elements</span></span>

|<span data-ttu-id="65898-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="65898-115">Element</span></span>|<span data-ttu-id="65898-116">Описание</span><span class="sxs-lookup"><span data-stu-id="65898-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65898-117">Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="65898-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="65898-118">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65898-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="65898-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="65898-119">Text Value</span></span>

<span data-ttu-id="65898-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="65898-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="65898-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="65898-121">Remarks</span></span>

<span data-ttu-id="65898-122">Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="65898-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="65898-123">См. также</span><span class="sxs-lookup"><span data-stu-id="65898-123">See Also</span></span>

[<span data-ttu-id="65898-124">Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="65898-124">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="65898-125">Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="65898-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="65898-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="65898-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
