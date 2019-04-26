---
title: Элемент ScriptBlock для WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064209"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="92969-102">Элемент ScriptBlock для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="92969-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="92969-103">Указывает сценарий, значение которого отображается в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="92969-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="92969-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) элемент WideItem (формат) ScriptBlock элемент конфигурации для WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="92969-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92969-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92969-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92969-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92969-106">Attributes and Elements</span></span>

<span data-ttu-id="92969-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="92969-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92969-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92969-108">Attributes</span></span>

<span data-ttu-id="92969-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="92969-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92969-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92969-110">Child Elements</span></span>

<span data-ttu-id="92969-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="92969-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92969-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92969-112">Parent Elements</span></span>

|<span data-ttu-id="92969-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="92969-113">Element</span></span>|<span data-ttu-id="92969-114">Описание</span><span class="sxs-lookup"><span data-stu-id="92969-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92969-115">Элемент WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="92969-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="92969-116">Определяет блок свойство или скрипта, значение которого отображается в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="92969-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92969-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="92969-117">Text Value</span></span>

<span data-ttu-id="92969-118">Укажите сценарий, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="92969-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="92969-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="92969-119">Remarks</span></span>

<span data-ttu-id="92969-120">Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="92969-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="92969-121">Пример</span><span class="sxs-lookup"><span data-stu-id="92969-121">Example</span></span>

<span data-ttu-id="92969-122">В этом примере показано `WideItem` элемент, который определяет скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="92969-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="92969-123">См. также</span><span class="sxs-lookup"><span data-stu-id="92969-123">See Also</span></span>

[<span data-ttu-id="92969-124">Элемент WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="92969-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="92969-125">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="92969-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="92969-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="92969-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
