---
title: Элемент ScriptBlock для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787603"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="9f8f0-102">Элемент ScriptBlock для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9f8f0-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="9f8f0-103">Задает скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="9f8f0-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) элемент ScriptBlock для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="9f8f0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f8f0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f8f0-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f8f0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9f8f0-106">Attributes and Elements</span></span>

<span data-ttu-id="9f8f0-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f8f0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9f8f0-108">Attributes</span></span>

<span data-ttu-id="9f8f0-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f8f0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9f8f0-110">Child Elements</span></span>

<span data-ttu-id="9f8f0-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9f8f0-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9f8f0-112">Parent Elements</span></span>

|<span data-ttu-id="9f8f0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9f8f0-113">Element</span></span>|<span data-ttu-id="9f8f0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9f8f0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f8f0-115">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="9f8f0-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="9f8f0-116">Определяет свойство или блок скрипта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9f8f0-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="9f8f0-117">Text Value</span></span>

<span data-ttu-id="9f8f0-118">Укажите скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f8f0-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f8f0-119">Remarks</span></span>

<span data-ttu-id="9f8f0-120">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9f8f0-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9f8f0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="9f8f0-121">Example</span></span>

<span data-ttu-id="9f8f0-122">В этом примере показан `WideItem` элемент, определяющий скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9f8f0-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="9f8f0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9f8f0-123">See Also</span></span>

[<span data-ttu-id="9f8f0-124">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="9f8f0-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="9f8f0-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="9f8f0-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9f8f0-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f8f0-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
