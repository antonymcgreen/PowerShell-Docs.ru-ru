---
title: Элемент Енумерабликспансионс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774020"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="32ef9-102">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="32ef9-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="32ef9-103">Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="32ef9-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="32ef9-104">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)</span><span class="sxs-lookup"><span data-stu-id="32ef9-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="32ef9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32ef9-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32ef9-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32ef9-106">Attributes and Elements</span></span>

<span data-ttu-id="32ef9-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемента.</span><span class="sxs-lookup"><span data-stu-id="32ef9-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="32ef9-108">Количество дочерних элементов, которые можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="32ef9-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="32ef9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32ef9-109">Attributes</span></span>

<span data-ttu-id="32ef9-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="32ef9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32ef9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32ef9-111">Child Elements</span></span>

|<span data-ttu-id="32ef9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="32ef9-112">Element</span></span>|<span data-ttu-id="32ef9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="32ef9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32ef9-114">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="32ef9-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="32ef9-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="32ef9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="32ef9-116">Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="32ef9-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="32ef9-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32ef9-117">Parent Elements</span></span>

|<span data-ttu-id="32ef9-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="32ef9-118">Element</span></span>|<span data-ttu-id="32ef9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="32ef9-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32ef9-120">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="32ef9-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="32ef9-121">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="32ef9-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="32ef9-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="32ef9-122">Remarks</span></span>

<span data-ttu-id="32ef9-123">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="32ef9-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="32ef9-124">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="32ef9-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="32ef9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="32ef9-125">See Also</span></span>

[<span data-ttu-id="32ef9-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="32ef9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
