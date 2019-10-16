---
title: Элемент Дефаултсеттингс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363873"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="484b8-102">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="484b8-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="484b8-103">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="484b8-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="484b8-104">К общим параметрам относятся отображение ошибок, перенос текста в таблицы, определение порядка развертывания коллекций и многое другое.</span><span class="sxs-lookup"><span data-stu-id="484b8-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="484b8-105">Элемент Configuration (Format) Дефаултсеттингс (формат)</span><span class="sxs-lookup"><span data-stu-id="484b8-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="484b8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="484b8-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="484b8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="484b8-107">Attributes and Elements</span></span>

<span data-ttu-id="484b8-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `DefaultSettings`.</span><span class="sxs-lookup"><span data-stu-id="484b8-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="484b8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="484b8-109">Attributes</span></span>

<span data-ttu-id="484b8-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="484b8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="484b8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="484b8-111">Child Elements</span></span>

|<span data-ttu-id="484b8-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="484b8-112">Element</span></span>|<span data-ttu-id="484b8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="484b8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="484b8-114">Элемент DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="484b8-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="484b8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="484b8-116">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="484b8-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="484b8-117">Элемент Енумерабликспансионс (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="484b8-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="484b8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="484b8-119">Определяет различные способы развертывания объектов .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="484b8-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="484b8-120">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="484b8-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="484b8-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="484b8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="484b8-122">Указывает минимальное число свойств, которое должен иметь объект для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="484b8-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="484b8-123">Элемент ShowError (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="484b8-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="484b8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="484b8-125">Указывает, что полная запись об ошибке отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="484b8-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="484b8-126">Элемент Враптаблес (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="484b8-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="484b8-127">Optional element.</span></span><br /><br /> <span data-ttu-id="484b8-128">Указывает, что данные в таблице перемещаются на следующую строку, если она не умещается в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="484b8-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="484b8-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="484b8-129">Parent Elements</span></span>

|<span data-ttu-id="484b8-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="484b8-130">Element</span></span>|<span data-ttu-id="484b8-131">Описание</span><span class="sxs-lookup"><span data-stu-id="484b8-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="484b8-132">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="484b8-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="484b8-133">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="484b8-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="484b8-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="484b8-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="484b8-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="484b8-135">See Also</span></span>

[<span data-ttu-id="484b8-136">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="484b8-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="484b8-137">Элемент DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="484b8-138">Элемент Енумерабликспансионс (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="484b8-139">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="484b8-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="484b8-140">Элемент ShowError (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="484b8-141">Элемент Враптаблес (Format)</span><span class="sxs-lookup"><span data-stu-id="484b8-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="484b8-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="484b8-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
