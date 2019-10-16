---
title: Элемент PropertyName для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364943"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="85ce1-102">Элемент PropertyName для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="85ce1-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="85ce1-103">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="85ce1-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="85ce1-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="85ce1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="85ce1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85ce1-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85ce1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85ce1-106">Attributes and Elements</span></span>

<span data-ttu-id="85ce1-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="85ce1-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="85ce1-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85ce1-108">Attributes</span></span>

<span data-ttu-id="85ce1-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="85ce1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="85ce1-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85ce1-110">Child Elements</span></span>

<span data-ttu-id="85ce1-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="85ce1-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="85ce1-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85ce1-112">Parent Elements</span></span>

|<span data-ttu-id="85ce1-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="85ce1-113">Element</span></span>|<span data-ttu-id="85ce1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="85ce1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85ce1-115">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="85ce1-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="85ce1-116">Определяет свойство или скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="85ce1-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="85ce1-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="85ce1-117">Text Value</span></span>

<span data-ttu-id="85ce1-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="85ce1-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="85ce1-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="85ce1-119">Remarks</span></span>

<span data-ttu-id="85ce1-120">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="85ce1-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="85ce1-121">Пример</span><span class="sxs-lookup"><span data-stu-id="85ce1-121">Example</span></span>

<span data-ttu-id="85ce1-122">В этом примере показано расширенное представление, в котором отображается значение свойства ProcessName объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="85ce1-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="85ce1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="85ce1-123">See Also</span></span>

[<span data-ttu-id="85ce1-124">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="85ce1-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="85ce1-125">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="85ce1-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="85ce1-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="85ce1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)