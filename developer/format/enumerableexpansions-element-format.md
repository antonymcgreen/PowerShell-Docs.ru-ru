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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066096"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="05c7f-102">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="05c7f-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="05c7f-103">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="05c7f-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="05c7f-104">EnumerableExpansions элемент DefaultSettings (формат) элемент (формат) для конфигурации элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="05c7f-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05c7f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c7f-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05c7f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05c7f-106">Attributes and Elements</span></span>

<span data-ttu-id="05c7f-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемент.</span><span class="sxs-lookup"><span data-stu-id="05c7f-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="05c7f-108">Нет ограничений на количество дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="05c7f-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="05c7f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05c7f-109">Attributes</span></span>

<span data-ttu-id="05c7f-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="05c7f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05c7f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05c7f-111">Child Elements</span></span>

|<span data-ttu-id="05c7f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c7f-112">Element</span></span>|<span data-ttu-id="05c7f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="05c7f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05c7f-114">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="05c7f-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="05c7f-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="05c7f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="05c7f-116">Определяет определенных объектов коллекции .NET, которые будут развернуты, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="05c7f-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="05c7f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05c7f-117">Parent Elements</span></span>

|<span data-ttu-id="05c7f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c7f-118">Element</span></span>|<span data-ttu-id="05c7f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="05c7f-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05c7f-120">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="05c7f-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="05c7f-121">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="05c7f-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="05c7f-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="05c7f-122">Remarks</span></span>

<span data-ttu-id="05c7f-123">Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="05c7f-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="05c7f-124">В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="05c7f-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="05c7f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="05c7f-125">See Also</span></span>

[<span data-ttu-id="05c7f-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="05c7f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
