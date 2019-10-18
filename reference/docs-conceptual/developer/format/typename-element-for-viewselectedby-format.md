---
title: Элемент TypeName для Виевселектедби (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361443"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="fe46c-102">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fe46c-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="fe46c-103">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="fe46c-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="fe46c-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби Element (Format) TypeName для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="fe46c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe46c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe46c-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe46c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fe46c-106">Attributes and Elements</span></span>

<span data-ttu-id="fe46c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="fe46c-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe46c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fe46c-108">Attributes</span></span>

<span data-ttu-id="fe46c-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="fe46c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe46c-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fe46c-110">Child Elements</span></span>

<span data-ttu-id="fe46c-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="fe46c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fe46c-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fe46c-112">Parent Elements</span></span>

|<span data-ttu-id="fe46c-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="fe46c-113">Element</span></span>|<span data-ttu-id="fe46c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fe46c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe46c-115">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="fe46c-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="fe46c-116">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="fe46c-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fe46c-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="fe46c-117">Text Value</span></span>

<span data-ttu-id="fe46c-118">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="fe46c-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe46c-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="fe46c-119">Remarks</span></span>

<span data-ttu-id="fe46c-120">Дополнительные сведения об использовании этого элемента в различных представлениях см. в статьях [Создание табличного представления](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание расширенного представления](./creating-a-wide-view.md)и [пользовательские компоненты представления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="fe46c-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe46c-121">Пример</span><span class="sxs-lookup"><span data-stu-id="fe46c-121">Example</span></span>

<span data-ttu-id="fe46c-122">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="fe46c-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="fe46c-123">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="fe46c-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="fe46c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe46c-124">See Also</span></span>

[<span data-ttu-id="fe46c-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="fe46c-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="fe46c-126">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="fe46c-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="fe46c-127">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="fe46c-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fe46c-128">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="fe46c-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="fe46c-129">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="fe46c-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="fe46c-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe46c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
