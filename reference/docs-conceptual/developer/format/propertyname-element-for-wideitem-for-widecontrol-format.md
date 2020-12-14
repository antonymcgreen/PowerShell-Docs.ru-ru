---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента WideItem для элемента WideControl (формат)
description: Элемент PropertyName для элемента WideItem для элемента WideControl (формат)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665623"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="ff9c8-103">Элемент PropertyName для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff9c8-103">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="ff9c8-104">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-104">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="ff9c8-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ff9c8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff9c8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff9c8-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff9c8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff9c8-107">Attributes and Elements</span></span>

<span data-ttu-id="ff9c8-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-108">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff9c8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff9c8-109">Attributes</span></span>

<span data-ttu-id="ff9c8-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff9c8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff9c8-111">Child Elements</span></span>

<span data-ttu-id="ff9c8-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ff9c8-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff9c8-113">Parent Elements</span></span>

|<span data-ttu-id="ff9c8-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff9c8-114">Element</span></span>|<span data-ttu-id="ff9c8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ff9c8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff9c8-116">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ff9c8-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="ff9c8-117">Определяет свойство или скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-117">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ff9c8-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ff9c8-118">Text Value</span></span>

<span data-ttu-id="ff9c8-119">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="ff9c8-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff9c8-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ff9c8-120">Remarks</span></span>

<span data-ttu-id="ff9c8-121">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="ff9c8-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff9c8-122">Пример</span><span class="sxs-lookup"><span data-stu-id="ff9c8-122">Example</span></span>

<span data-ttu-id="ff9c8-123">В этом примере показано расширенное представление, в котором отображается значение свойства ProcessName объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="ff9c8-123">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="ff9c8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff9c8-124">See Also</span></span>

[<span data-ttu-id="ff9c8-125">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ff9c8-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="ff9c8-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="ff9c8-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ff9c8-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff9c8-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
