---
title: Элемент Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779902"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="4b678-102">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b678-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="4b678-103">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="4b678-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="4b678-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем (формат)</span><span class="sxs-lookup"><span data-stu-id="4b678-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b678-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b678-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b678-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b678-106">Attributes and Elements</span></span>

<span data-ttu-id="4b678-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="4b678-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="4b678-108">Элемент `FormatString` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4b678-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="4b678-109">Однако необходимо указать `PropertyName` `ScriptBlock` элемент или, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="4b678-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b678-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b678-110">Attributes</span></span>

<span data-ttu-id="4b678-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4b678-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b678-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b678-112">Child Elements</span></span>

|<span data-ttu-id="4b678-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b678-113">Element</span></span>|<span data-ttu-id="4b678-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4b678-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b678-115">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b678-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="4b678-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b678-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4b678-117">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="4b678-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="4b678-118">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="4b678-119">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="4b678-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="4b678-120">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="4b678-121">Задает скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="4b678-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4b678-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b678-122">Parent Elements</span></span>

|<span data-ttu-id="4b678-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b678-123">Element</span></span>|<span data-ttu-id="4b678-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4b678-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b678-125">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="4b678-126">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="4b678-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b678-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b678-127">Remarks</span></span>

<span data-ttu-id="4b678-128">Дополнительные сведения о компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="4b678-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4b678-129">Пример</span><span class="sxs-lookup"><span data-stu-id="4b678-129">Example</span></span>

<span data-ttu-id="4b678-130">В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="4b678-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="4b678-131">`WideItem`Элемент определяет свойство или скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="4b678-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="4b678-132">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="4b678-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b678-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4b678-133">See Also</span></span>

[<span data-ttu-id="4b678-134">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b678-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="4b678-135">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="4b678-136">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="4b678-137">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4b678-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="4b678-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b678-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
