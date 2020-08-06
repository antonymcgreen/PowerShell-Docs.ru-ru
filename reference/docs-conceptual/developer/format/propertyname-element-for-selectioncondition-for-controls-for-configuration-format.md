---
title: Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7730951a840fcfcd8bf819fff5182049bd6b6c23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773136"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="a8780-102">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="a8780-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a8780-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="a8780-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="a8780-104">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись.</span><span class="sxs-lookup"><span data-stu-id="a8780-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="a8780-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="a8780-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a8780-106">Элемент конфигурации (Format) контролирует элемент элемента управления конфигурации (Format) для элементов управления для элемента конфигурации (Format) ошибка customcontrol для элемента управления в элементе конфигурации (Format) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления для элемента конфигурации (Format) Селектионкондитион для Ентриселектедби для CustomEntry для элемента конфигурации (Format) PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a8780-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a8780-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8780-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8780-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8780-108">Attributes and Elements</span></span>

<span data-ttu-id="a8780-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="a8780-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8780-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8780-110">Attributes</span></span>

<span data-ttu-id="a8780-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8780-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a8780-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8780-112">Child Elements</span></span>

<span data-ttu-id="a8780-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8780-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a8780-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8780-114">Parent Elements</span></span>

|<span data-ttu-id="a8780-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8780-115">Element</span></span>|<span data-ttu-id="a8780-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a8780-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8780-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="a8780-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="a8780-118">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a8780-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a8780-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a8780-119">Text Value</span></span>

<span data-ttu-id="a8780-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="a8780-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8780-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8780-121">Remarks</span></span>

<span data-ttu-id="a8780-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="a8780-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="a8780-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a8780-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8780-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a8780-124">See Also</span></span>

[<span data-ttu-id="a8780-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="a8780-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="a8780-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8780-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
