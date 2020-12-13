---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента ViewSelectedBy (формат)
description: Элемент TypeName для элемента ViewSelectedBy (формат)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667731"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="324ec-103">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="324ec-103">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="324ec-104">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="324ec-104">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="324ec-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби Element (Format) TypeName для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="324ec-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="324ec-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="324ec-106">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="324ec-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="324ec-107">Attributes and Elements</span></span>

<span data-ttu-id="324ec-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="324ec-108">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="324ec-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="324ec-109">Attributes</span></span>

<span data-ttu-id="324ec-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="324ec-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="324ec-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="324ec-111">Child Elements</span></span>

<span data-ttu-id="324ec-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="324ec-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="324ec-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="324ec-113">Parent Elements</span></span>

|<span data-ttu-id="324ec-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="324ec-114">Element</span></span>|<span data-ttu-id="324ec-115">Описание</span><span class="sxs-lookup"><span data-stu-id="324ec-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="324ec-116">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="324ec-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="324ec-117">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="324ec-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="324ec-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="324ec-118">Text Value</span></span>

<span data-ttu-id="324ec-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="324ec-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="324ec-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="324ec-120">Remarks</span></span>

<span data-ttu-id="324ec-121">Дополнительные сведения об использовании этого элемента в различных представлениях см. в статьях [Создание табличного представления](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание расширенного представления](./creating-a-wide-view.md)и [пользовательские компоненты представления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="324ec-121">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="324ec-122">Пример</span><span class="sxs-lookup"><span data-stu-id="324ec-122">Example</span></span>

<span data-ttu-id="324ec-123">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="324ec-123">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="324ec-124">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="324ec-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="324ec-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="324ec-125">See Also</span></span>

[<span data-ttu-id="324ec-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="324ec-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="324ec-127">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="324ec-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="324ec-128">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="324ec-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="324ec-129">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="324ec-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="324ec-130">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="324ec-130">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="324ec-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="324ec-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
