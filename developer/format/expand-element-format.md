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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066011"
---
# <a name="expand-element-format"></a><span data-ttu-id="986f6-102">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="986f6-102">Expand Element (Format)</span></span>

<span data-ttu-id="986f6-103">Указывает, каким образом объект коллекции расширяется для данного определения.</span><span class="sxs-lookup"><span data-stu-id="986f6-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="986f6-104">Элемент конфигурации элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) EnumerableExpansion (формат) разверните элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="986f6-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="986f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="986f6-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="986f6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="986f6-106">Attributes and Elements</span></span>

<span data-ttu-id="986f6-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Expand` элемент.</span><span class="sxs-lookup"><span data-stu-id="986f6-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="986f6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="986f6-108">Attributes</span></span>

<span data-ttu-id="986f6-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="986f6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="986f6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="986f6-110">Child Elements</span></span>

<span data-ttu-id="986f6-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="986f6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="986f6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="986f6-112">Parent Elements</span></span>

|<span data-ttu-id="986f6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="986f6-113">Element</span></span>|<span data-ttu-id="986f6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="986f6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="986f6-115">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="986f6-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="986f6-116">Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="986f6-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="986f6-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="986f6-117">Text Value</span></span>

<span data-ttu-id="986f6-118">Укажите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="986f6-118">Specify one of the following values:</span></span>

- <span data-ttu-id="986f6-119">EnumOnly: Отображаются только свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="986f6-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="986f6-120">CoreOnly — Отображаются только свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="986f6-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="986f6-121">Оба: Отображает свойства объектов в коллекции и свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="986f6-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="986f6-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="986f6-122">Remarks</span></span>

<span data-ttu-id="986f6-123">Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="986f6-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="986f6-124">В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="986f6-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="986f6-125">По умолчанию задается для отображения только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="986f6-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="986f6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="986f6-126">See Also</span></span>

[<span data-ttu-id="986f6-127">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="986f6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
