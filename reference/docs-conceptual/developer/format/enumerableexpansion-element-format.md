---
title: Элемент Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774054"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="9114a-102">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="9114a-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="9114a-103">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="9114a-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="9114a-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион (формат)</span><span class="sxs-lookup"><span data-stu-id="9114a-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9114a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9114a-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9114a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9114a-106">Attributes and Elements</span></span>

<span data-ttu-id="9114a-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansion` элемента.</span><span class="sxs-lookup"><span data-stu-id="9114a-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9114a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9114a-108">Attributes</span></span>

<span data-ttu-id="9114a-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9114a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9114a-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9114a-110">Child Elements</span></span>

|<span data-ttu-id="9114a-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="9114a-111">Element</span></span>|<span data-ttu-id="9114a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9114a-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9114a-113">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="9114a-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="9114a-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9114a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="9114a-115">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="9114a-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="9114a-116">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="9114a-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="9114a-117">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="9114a-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9114a-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9114a-118">Parent Elements</span></span>

|<span data-ttu-id="9114a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9114a-119">Element</span></span>|<span data-ttu-id="9114a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9114a-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9114a-121">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="9114a-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="9114a-122">Определяет различные способы развертывания объектов коллекции .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="9114a-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9114a-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="9114a-123">Remarks</span></span>

<span data-ttu-id="9114a-124">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9114a-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="9114a-125">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="9114a-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="9114a-126">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9114a-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="9114a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9114a-127">See Also</span></span>

[<span data-ttu-id="9114a-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9114a-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
