---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для WideItem для WideControl (формат)
description: Элемент ScriptBlock для WideItem для WideControl (формат)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659869"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="639c4-103">Элемент ScriptBlock для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="639c4-103">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="639c4-104">Задает скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="639c4-104">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="639c4-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="639c4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="639c4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="639c4-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="639c4-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="639c4-107">Attributes and Elements</span></span>

<span data-ttu-id="639c4-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="639c4-108">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="639c4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="639c4-109">Attributes</span></span>

<span data-ttu-id="639c4-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="639c4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="639c4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="639c4-111">Child Elements</span></span>

<span data-ttu-id="639c4-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="639c4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="639c4-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="639c4-113">Parent Elements</span></span>

|<span data-ttu-id="639c4-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="639c4-114">Element</span></span>|<span data-ttu-id="639c4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="639c4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="639c4-116">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="639c4-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="639c4-117">Определяет свойство или блок скрипта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="639c4-117">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="639c4-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="639c4-118">Text Value</span></span>

<span data-ttu-id="639c4-119">Укажите скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="639c4-119">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="639c4-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="639c4-120">Remarks</span></span>

<span data-ttu-id="639c4-121">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="639c4-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="639c4-122">Пример</span><span class="sxs-lookup"><span data-stu-id="639c4-122">Example</span></span>

<span data-ttu-id="639c4-123">В этом примере показан `WideItem` элемент, определяющий скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="639c4-123">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="639c4-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="639c4-124">See Also</span></span>

[<span data-ttu-id="639c4-125">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="639c4-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="639c4-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="639c4-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="639c4-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="639c4-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
