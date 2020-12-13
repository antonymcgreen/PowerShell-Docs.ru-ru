---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideItem для WideControl (формат)
description: Элемент WideItem для WideControl (формат)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647797"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="8a22d-103">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a22d-103">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="8a22d-104">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="8a22d-104">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="8a22d-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем (формат)</span><span class="sxs-lookup"><span data-stu-id="8a22d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a22d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a22d-106">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a22d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a22d-107">Attributes and Elements</span></span>

<span data-ttu-id="8a22d-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="8a22d-108">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="8a22d-109">Элемент `FormatString` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8a22d-109">The `FormatString` element is optional.</span></span> <span data-ttu-id="8a22d-110">Однако необходимо указать `PropertyName` `ScriptBlock` элемент или, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="8a22d-110">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a22d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a22d-111">Attributes</span></span>

<span data-ttu-id="8a22d-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a22d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a22d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a22d-113">Child Elements</span></span>

|<span data-ttu-id="8a22d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a22d-114">Element</span></span>|<span data-ttu-id="8a22d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8a22d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a22d-116">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a22d-116">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="8a22d-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a22d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="8a22d-118">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="8a22d-118">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="8a22d-119">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-119">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="8a22d-120">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="8a22d-120">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="8a22d-121">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-121">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="8a22d-122">Задает скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="8a22d-122">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8a22d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a22d-123">Parent Elements</span></span>

|<span data-ttu-id="8a22d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a22d-124">Element</span></span>|<span data-ttu-id="8a22d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8a22d-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a22d-126">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="8a22d-127">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="8a22d-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8a22d-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8a22d-128">Remarks</span></span>

<span data-ttu-id="8a22d-129">Дополнительные сведения о компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="8a22d-129">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8a22d-130">Пример</span><span class="sxs-lookup"><span data-stu-id="8a22d-130">Example</span></span>

<span data-ttu-id="8a22d-131">В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="8a22d-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="8a22d-132">`WideItem`Элемент определяет свойство или скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="8a22d-132">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="8a22d-133">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="8a22d-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a22d-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a22d-134">See Also</span></span>

[<span data-ttu-id="8a22d-135">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8a22d-135">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="8a22d-136">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-136">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="8a22d-137">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-137">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="8a22d-138">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="8a22d-138">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="8a22d-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a22d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
