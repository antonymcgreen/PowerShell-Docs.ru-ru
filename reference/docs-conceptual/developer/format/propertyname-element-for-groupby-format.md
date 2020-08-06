---
title: Элемент PropertyName для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785614"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="bf573-102">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="bf573-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="bf573-103">Указывает свойство .NET, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="bf573-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="bf573-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (Format) PropertyName для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bf573-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf573-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf573-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf573-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf573-106">Attributes and Elements</span></span>

<span data-ttu-id="bf573-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="bf573-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf573-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf573-108">Attributes</span></span>

<span data-ttu-id="bf573-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf573-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf573-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf573-110">Child Elements</span></span>

<span data-ttu-id="bf573-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf573-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bf573-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf573-112">Parent Elements</span></span>

|<span data-ttu-id="bf573-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf573-113">Element</span></span>|<span data-ttu-id="bf573-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bf573-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf573-115">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="bf573-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="bf573-116">Определяет, как отображается группа объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="bf573-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bf573-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="bf573-117">Text Value</span></span>

<span data-ttu-id="bf573-118">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="bf573-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf573-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf573-119">Remarks</span></span>

<span data-ttu-id="bf573-120">Windows PowerShell запускает новую группу при каждом изменении значения этого свойства.</span><span class="sxs-lookup"><span data-stu-id="bf573-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="bf573-121">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) для запуска новой группы.</span><span class="sxs-lookup"><span data-stu-id="bf573-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="bf573-122">Пример</span><span class="sxs-lookup"><span data-stu-id="bf573-122">Example</span></span>

<span data-ttu-id="bf573-123">В следующем примере показано, как запустить новую группу при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="bf573-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="bf573-124">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="bf573-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf573-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bf573-125">See Also</span></span>

[<span data-ttu-id="bf573-126">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="bf573-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="bf573-127">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="bf573-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="bf573-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf573-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
