---
title: Элемент Енумерабликспансионс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363303"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="31928-102">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="31928-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="31928-103">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="31928-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="31928-104">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)</span><span class="sxs-lookup"><span data-stu-id="31928-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="31928-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31928-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="31928-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="31928-106">Attributes and Elements</span></span>

<span data-ttu-id="31928-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EnumerableExpansions`.</span><span class="sxs-lookup"><span data-stu-id="31928-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="31928-108">Количество дочерних элементов, которые можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="31928-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="31928-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="31928-109">Attributes</span></span>

<span data-ttu-id="31928-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="31928-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="31928-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="31928-111">Child Elements</span></span>

|<span data-ttu-id="31928-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="31928-112">Element</span></span>|<span data-ttu-id="31928-113">Описание</span><span class="sxs-lookup"><span data-stu-id="31928-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31928-114">Элемент Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="31928-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="31928-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="31928-115">Optional element.</span></span><br /><br /> <span data-ttu-id="31928-116">Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="31928-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="31928-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="31928-117">Parent Elements</span></span>

|<span data-ttu-id="31928-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="31928-118">Element</span></span>|<span data-ttu-id="31928-119">Описание</span><span class="sxs-lookup"><span data-stu-id="31928-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31928-120">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="31928-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="31928-121">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="31928-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="31928-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="31928-122">Remarks</span></span>

<span data-ttu-id="31928-123">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="31928-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="31928-124">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="31928-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="31928-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="31928-125">See Also</span></span>

[<span data-ttu-id="31928-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="31928-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
