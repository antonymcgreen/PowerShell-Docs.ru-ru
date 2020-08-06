---
title: Элемент TypeName для Виевселектедби (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e9a391565c3e66041dd9a340455dccfce9ce929b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780038"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="ab72f-102">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ab72f-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="ab72f-103">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="ab72f-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="ab72f-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби Element (Format) TypeName для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="ab72f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab72f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab72f-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab72f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ab72f-106">Attributes and Elements</span></span>

<span data-ttu-id="ab72f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="ab72f-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab72f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ab72f-108">Attributes</span></span>

<span data-ttu-id="ab72f-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ab72f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab72f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ab72f-110">Child Elements</span></span>

<span data-ttu-id="ab72f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ab72f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ab72f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ab72f-112">Parent Elements</span></span>

|<span data-ttu-id="ab72f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab72f-113">Element</span></span>|<span data-ttu-id="ab72f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ab72f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab72f-115">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ab72f-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="ab72f-116">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="ab72f-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ab72f-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ab72f-117">Text Value</span></span>

<span data-ttu-id="ab72f-118">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="ab72f-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab72f-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab72f-119">Remarks</span></span>

<span data-ttu-id="ab72f-120">Дополнительные сведения об использовании этого элемента в различных представлениях см. в статьях [Создание табличного представления](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание расширенного представления](./creating-a-wide-view.md)и [пользовательские компоненты представления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ab72f-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="ab72f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ab72f-121">Example</span></span>

<span data-ttu-id="ab72f-122">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="ab72f-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="ab72f-123">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="ab72f-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="ab72f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ab72f-124">See Also</span></span>

[<span data-ttu-id="ab72f-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="ab72f-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ab72f-126">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="ab72f-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ab72f-127">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="ab72f-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ab72f-128">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="ab72f-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="ab72f-129">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ab72f-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="ab72f-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab72f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
