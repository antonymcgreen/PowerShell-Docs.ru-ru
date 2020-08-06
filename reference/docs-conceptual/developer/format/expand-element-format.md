---
title: Элемент Expand (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783659"
---
# <a name="expand-element-format"></a><span data-ttu-id="0b287-102">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="0b287-102">Expand Element (Format)</span></span>

<span data-ttu-id="0b287-103">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="0b287-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="0b287-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) развернуть элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="0b287-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b287-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b287-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b287-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b287-106">Attributes and Elements</span></span>

<span data-ttu-id="0b287-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Expand` элемента.</span><span class="sxs-lookup"><span data-stu-id="0b287-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b287-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b287-108">Attributes</span></span>

<span data-ttu-id="0b287-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b287-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b287-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b287-110">Child Elements</span></span>

<span data-ttu-id="0b287-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b287-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b287-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b287-112">Parent Elements</span></span>

|<span data-ttu-id="0b287-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b287-113">Element</span></span>|<span data-ttu-id="0b287-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0b287-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b287-115">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0b287-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="0b287-116">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b287-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0b287-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0b287-117">Text Value</span></span>

<span data-ttu-id="0b287-118">Укажите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="0b287-118">Specify one of the following values:</span></span>

- <span data-ttu-id="0b287-119">Енумонли: отображает только свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0b287-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="0b287-120">Кореонли: отображает только свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="0b287-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="0b287-121">Оба: отображает свойства объектов в коллекции и свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="0b287-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b287-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b287-122">Remarks</span></span>

<span data-ttu-id="0b287-123">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0b287-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="0b287-124">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="0b287-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="0b287-125">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0b287-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b287-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b287-126">See Also</span></span>

[<span data-ttu-id="0b287-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b287-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
