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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363303"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="bdb42-102">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="bdb42-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="bdb42-103">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="bdb42-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="bdb42-104">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)</span><span class="sxs-lookup"><span data-stu-id="bdb42-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bdb42-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdb42-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bdb42-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bdb42-106">Attributes and Elements</span></span>

<span data-ttu-id="bdb42-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EnumerableExpansions`.</span><span class="sxs-lookup"><span data-stu-id="bdb42-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="bdb42-108">Количество дочерних элементов, которые можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="bdb42-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="bdb42-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bdb42-109">Attributes</span></span>

<span data-ttu-id="bdb42-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="bdb42-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bdb42-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bdb42-111">Child Elements</span></span>

|<span data-ttu-id="bdb42-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="bdb42-112">Element</span></span>|<span data-ttu-id="bdb42-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bdb42-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdb42-114">Элемент Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="bdb42-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="bdb42-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bdb42-115">Optional element.</span></span><br /><br /> <span data-ttu-id="bdb42-116">Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="bdb42-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bdb42-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bdb42-117">Parent Elements</span></span>

|<span data-ttu-id="bdb42-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="bdb42-118">Element</span></span>|<span data-ttu-id="bdb42-119">Описание</span><span class="sxs-lookup"><span data-stu-id="bdb42-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdb42-120">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="bdb42-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="bdb42-121">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="bdb42-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bdb42-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="bdb42-122">Remarks</span></span>

<span data-ttu-id="bdb42-123">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="bdb42-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="bdb42-124">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="bdb42-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdb42-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdb42-125">See Also</span></span>

[<span data-ttu-id="bdb42-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdb42-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
