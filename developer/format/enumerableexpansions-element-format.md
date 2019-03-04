---
title: Элемент EnumerableExpansions (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860260"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="e4bd1-102">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="e4bd1-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="e4bd1-103">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="e4bd1-104">EnumerableExpansions элемент DefaultSettings (формат) элемент (формат) для конфигурации элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="e4bd1-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4bd1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4bd1-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4bd1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e4bd1-106">Attributes and Elements</span></span>

<span data-ttu-id="e4bd1-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="e4bd1-108">Нет ограничений на количество дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4bd1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e4bd1-109">Attributes</span></span>

<span data-ttu-id="e4bd1-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4bd1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e4bd1-111">Child Elements</span></span>

|<span data-ttu-id="e4bd1-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e4bd1-112">Element</span></span>|<span data-ttu-id="e4bd1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e4bd1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4bd1-114">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="e4bd1-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="e4bd1-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e4bd1-116">Определяет определенных объектов коллекции .NET, которые будут развернуты, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e4bd1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e4bd1-117">Parent Elements</span></span>

|<span data-ttu-id="e4bd1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e4bd1-118">Element</span></span>|<span data-ttu-id="e4bd1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e4bd1-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4bd1-120">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="e4bd1-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="e4bd1-121">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e4bd1-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="e4bd1-122">Remarks</span></span>

<span data-ttu-id="e4bd1-123">Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="e4bd1-124">В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e4bd1-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4bd1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e4bd1-125">See Also</span></span>

[<span data-ttu-id="e4bd1-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4bd1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
