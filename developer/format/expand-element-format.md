---
title: Разверните элемент (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858580"
---
# <a name="expand-element-format"></a><span data-ttu-id="db00f-102">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="db00f-102">Expand Element (Format)</span></span>

<span data-ttu-id="db00f-103">Указывает, каким образом объект коллекции расширяется для данного определения.</span><span class="sxs-lookup"><span data-stu-id="db00f-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="db00f-104">Элемент конфигурации элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) EnumerableExpansion (формат) разверните элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="db00f-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db00f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db00f-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db00f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db00f-106">Attributes and Elements</span></span>

<span data-ttu-id="db00f-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Expand` элемент.</span><span class="sxs-lookup"><span data-stu-id="db00f-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db00f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db00f-108">Attributes</span></span>

<span data-ttu-id="db00f-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="db00f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db00f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db00f-110">Child Elements</span></span>

<span data-ttu-id="db00f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="db00f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db00f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db00f-112">Parent Elements</span></span>

|<span data-ttu-id="db00f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="db00f-113">Element</span></span>|<span data-ttu-id="db00f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="db00f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db00f-115">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="db00f-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="db00f-116">Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="db00f-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db00f-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="db00f-117">Text Value</span></span>

<span data-ttu-id="db00f-118">Укажите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="db00f-118">Specify one of the following values:</span></span>

- <span data-ttu-id="db00f-119">EnumOnly: Отображаются только свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="db00f-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="db00f-120">CoreOnly — Отображаются только свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="db00f-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="db00f-121">Оба: Отображает свойства объектов в коллекции и свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="db00f-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="db00f-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="db00f-122">Remarks</span></span>

<span data-ttu-id="db00f-123">Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="db00f-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="db00f-124">В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="db00f-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="db00f-125">По умолчанию задается для отображения только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="db00f-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="db00f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="db00f-126">See Also</span></span>

[<span data-ttu-id="db00f-127">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="db00f-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
