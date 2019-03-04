---
title: Элемент WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862630"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="b6e42-102">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="b6e42-103">Определяет свойство или скрипта, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="b6e42-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="b6e42-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) WideItem элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e42-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6e42-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6e42-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6e42-106">Attributes and Elements</span></span>

<span data-ttu-id="b6e42-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="b6e42-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="b6e42-108">Элемент `FormatString` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b6e42-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="b6e42-109">Тем не менее, необходимо указать `PropertyName` или `ScriptBlock` элемент, но нельзя одновременно задать.</span><span class="sxs-lookup"><span data-stu-id="b6e42-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6e42-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6e42-110">Attributes</span></span>

<span data-ttu-id="b6e42-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b6e42-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6e42-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6e42-112">Child Elements</span></span>

|<span data-ttu-id="b6e42-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6e42-113">Element</span></span>|<span data-ttu-id="b6e42-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e42-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6e42-115">Элемент FormatString для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="b6e42-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b6e42-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b6e42-117">Задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.</span><span class="sxs-lookup"><span data-stu-id="b6e42-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="b6e42-118">Элемент PropertyName для WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="b6e42-119">Задает свойство объекта, значение которого отображается в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="b6e42-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="b6e42-120">Элемент ScriptBlock для WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="b6e42-121">Указывает сценарий, значение которого отображается в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="b6e42-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b6e42-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6e42-122">Parent Elements</span></span>

|<span data-ttu-id="b6e42-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6e42-123">Element</span></span>|<span data-ttu-id="b6e42-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e42-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6e42-125">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="b6e42-126">Предоставляет определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="b6e42-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6e42-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="b6e42-127">Remarks</span></span>

<span data-ttu-id="b6e42-128">Дополнительные сведения о компонентах широкое представление, см. в разделе [широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="b6e42-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b6e42-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b6e42-129">Example</span></span>

<span data-ttu-id="b6e42-130">В следующем примере показан `WideEntry` элемент, который определяет одно `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="b6e42-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="b6e42-131">`WideItem` Элемент определяет свойства или скрипта, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="b6e42-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="b6e42-132">Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="b6e42-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e42-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b6e42-133">See Also</span></span>

[<span data-ttu-id="b6e42-134">Элемент FormatString для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="b6e42-135">Элемент PropertyName для WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="b6e42-136">Элемент ScriptBlock для WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="b6e42-137">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e42-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="b6e42-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6e42-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
