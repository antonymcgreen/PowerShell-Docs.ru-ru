---
title: Элемент PropertyName для Селектионкондитион для ошибка customcontrol в представлении (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: aa3955b84b8de9901f394e8108f31440fcb6c942
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780803"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="db249-102">Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="db249-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="db249-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="db249-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="db249-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="db249-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="db249-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="db249-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="db249-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента представления (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) Кустомитем элемент для Кустоментри для ошибка customcontrol для элемента Ентриселектедби представления (Format) для CustomEntry для ошибка customcontrol для элемента SelectionCondition для представления (Format) EntrySelectedBy (формат).</span><span class="sxs-lookup"><span data-stu-id="db249-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db249-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db249-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db249-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db249-108">Attributes and Elements</span></span>

<span data-ttu-id="db249-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="db249-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db249-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db249-110">Attributes</span></span>

<span data-ttu-id="db249-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db249-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db249-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db249-112">Child Elements</span></span>

<span data-ttu-id="db249-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db249-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db249-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db249-114">Parent Elements</span></span>

|<span data-ttu-id="db249-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="db249-115">Element</span></span>|<span data-ttu-id="db249-116">Описание</span><span class="sxs-lookup"><span data-stu-id="db249-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db249-117">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="db249-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="db249-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="db249-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db249-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="db249-119">Text Value</span></span>

<span data-ttu-id="db249-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="db249-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="db249-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="db249-121">Remarks</span></span>

<span data-ttu-id="db249-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="db249-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="db249-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="db249-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db249-124">См. также</span><span class="sxs-lookup"><span data-stu-id="db249-124">See Also</span></span>

[<span data-ttu-id="db249-125">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="db249-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="db249-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="db249-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
