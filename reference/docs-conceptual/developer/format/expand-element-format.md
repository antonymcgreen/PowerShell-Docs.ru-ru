---
title: Элемент Expand (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368743"
---
# <a name="expand-element-format"></a><span data-ttu-id="caad0-102">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="caad0-102">Expand Element (Format)</span></span>

<span data-ttu-id="caad0-103">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="caad0-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="caad0-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) развернуть элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="caad0-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="caad0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caad0-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="caad0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="caad0-106">Attributes and Elements</span></span>

<span data-ttu-id="caad0-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Expand`.</span><span class="sxs-lookup"><span data-stu-id="caad0-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="caad0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="caad0-108">Attributes</span></span>

<span data-ttu-id="caad0-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="caad0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="caad0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="caad0-110">Child Elements</span></span>

<span data-ttu-id="caad0-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="caad0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="caad0-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="caad0-112">Parent Elements</span></span>

|<span data-ttu-id="caad0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="caad0-113">Element</span></span>|<span data-ttu-id="caad0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="caad0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="caad0-115">Элемент Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="caad0-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="caad0-116">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="caad0-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="caad0-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="caad0-117">Text Value</span></span>

<span data-ttu-id="caad0-118">Укажите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="caad0-118">Specify one of the following values:</span></span>

- <span data-ttu-id="caad0-119">Енумонли: отображает только свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="caad0-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="caad0-120">Кореонли: отображает только свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="caad0-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="caad0-121">Оба: отображает свойства объектов в коллекции и свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="caad0-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="caad0-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="caad0-122">Remarks</span></span>

<span data-ttu-id="caad0-123">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="caad0-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="caad0-124">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="caad0-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="caad0-125">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="caad0-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="caad0-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="caad0-126">See Also</span></span>

[<span data-ttu-id="caad0-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="caad0-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
