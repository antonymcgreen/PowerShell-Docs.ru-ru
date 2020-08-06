---
title: Элемент PropertyName для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7728f960a67faa99eaafb4a4934674e119b8af27
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780480"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="97aa6-102">Элемент PropertyName для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="97aa6-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="97aa6-103">Указывает свойство объекта, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="97aa6-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="97aa6-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) PropertyName для Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="97aa6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97aa6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97aa6-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97aa6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97aa6-106">Attributes and Elements</span></span>

<span data-ttu-id="97aa6-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="97aa6-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="97aa6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97aa6-108">Attributes</span></span>

<span data-ttu-id="97aa6-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="97aa6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97aa6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97aa6-110">Child Elements</span></span>

<span data-ttu-id="97aa6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="97aa6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="97aa6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97aa6-112">Parent Elements</span></span>

|<span data-ttu-id="97aa6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="97aa6-113">Element</span></span>|<span data-ttu-id="97aa6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="97aa6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97aa6-115">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="97aa6-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="97aa6-116">Определяет свойство или скрипт, значение которого отображается в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="97aa6-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="97aa6-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="97aa6-117">Text Value</span></span>

<span data-ttu-id="97aa6-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="97aa6-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="97aa6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="97aa6-119">Remarks</span></span>

<span data-ttu-id="97aa6-120">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="97aa6-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="97aa6-121">Пример</span><span class="sxs-lookup"><span data-stu-id="97aa6-121">Example</span></span>

<span data-ttu-id="97aa6-122">В этом примере показано расширенное представление, в котором отображается значение свойства ProcessName объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="97aa6-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="97aa6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="97aa6-123">See Also</span></span>

[<span data-ttu-id="97aa6-124">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="97aa6-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="97aa6-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="97aa6-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="97aa6-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="97aa6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
