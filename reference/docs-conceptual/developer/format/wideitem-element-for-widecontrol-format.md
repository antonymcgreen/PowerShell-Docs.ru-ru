---
title: Элемент Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361403"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="f4088-102">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f4088-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="f4088-103">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="f4088-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="f4088-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем (формат)</span><span class="sxs-lookup"><span data-stu-id="f4088-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4088-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4088-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4088-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4088-106">Attributes and Elements</span></span>

<span data-ttu-id="f4088-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="f4088-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="f4088-108">Элемент `FormatString` необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4088-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="f4088-109">Однако необходимо указать элемент `PropertyName` или `ScriptBlock`, но нельзя указать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="f4088-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4088-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4088-110">Attributes</span></span>

<span data-ttu-id="f4088-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4088-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4088-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4088-112">Child Elements</span></span>

|<span data-ttu-id="f4088-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4088-113">Element</span></span>|<span data-ttu-id="f4088-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f4088-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4088-115">Элемент FormatString для Видеитем для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f4088-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f4088-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f4088-117">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="f4088-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="f4088-118">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f4088-119">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="f4088-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="f4088-120">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f4088-121">Задает скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="f4088-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f4088-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4088-122">Parent Elements</span></span>

|<span data-ttu-id="f4088-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4088-123">Element</span></span>|<span data-ttu-id="f4088-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f4088-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4088-125">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="f4088-126">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="f4088-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f4088-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="f4088-127">Remarks</span></span>

<span data-ttu-id="f4088-128">Дополнительные сведения о компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="f4088-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f4088-129">Пример</span><span class="sxs-lookup"><span data-stu-id="f4088-129">Example</span></span>

<span data-ttu-id="f4088-130">В следующем примере показан элемент `WideEntry`, определяющий один элемент `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="f4088-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="f4088-131">Элемент `WideItem` определяет свойство или скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="f4088-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="f4088-132">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="f4088-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4088-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4088-133">See Also</span></span>

[<span data-ttu-id="f4088-134">Элемент FormatString для Видеитем для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f4088-135">Элемент PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f4088-136">Элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f4088-137">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="f4088-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="f4088-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4088-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
