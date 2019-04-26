---
title: TypeName-элемент для ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083762"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="2b2ac-102">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2b2ac-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="2b2ac-103">Указывает объект .NET, который отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="2b2ac-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент ViewSelectedBy (формат) TypeName элемент конфигурации для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2b2ac-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b2ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b2ac-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b2ac-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2b2ac-106">Attributes and Elements</span></span>

<span data-ttu-id="2b2ac-107">В следующих разделах атрибуты, дочерние и родительские элементы из `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b2ac-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b2ac-108">Attributes</span></span>

<span data-ttu-id="2b2ac-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b2ac-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b2ac-110">Child Elements</span></span>

<span data-ttu-id="2b2ac-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b2ac-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b2ac-112">Parent Elements</span></span>

|<span data-ttu-id="2b2ac-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b2ac-113">Element</span></span>|<span data-ttu-id="2b2ac-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2b2ac-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b2ac-115">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2b2ac-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="2b2ac-116">Определяет объекты .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b2ac-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2b2ac-117">Text Value</span></span>

<span data-ttu-id="2b2ac-118">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b2ac-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="2b2ac-119">Remarks</span></span>

<span data-ttu-id="2b2ac-120">Дополнительные сведения о том, как этот элемент используется в различных представлениях см. в разделе [Создание представления таблицы](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание широкое представление](./creating-a-wide-view.md), и [ Пользовательское представление компонентов](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2b2ac-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b2ac-121">Пример</span><span class="sxs-lookup"><span data-stu-id="2b2ac-121">Example</span></span>

<span data-ttu-id="2b2ac-122">В следующем примере показано, как указать [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект для представления списка.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="2b2ac-123">Ту же схему используется для таблицы, расширенных и настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="2b2ac-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="2b2ac-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2b2ac-124">See Also</span></span>

[<span data-ttu-id="2b2ac-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="2b2ac-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2b2ac-126">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="2b2ac-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2b2ac-127">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="2b2ac-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2b2ac-128">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="2b2ac-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2b2ac-129">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2b2ac-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="2b2ac-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b2ac-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
