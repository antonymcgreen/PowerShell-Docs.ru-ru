---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент DefaultSettings (формат)
description: Элемент DefaultSettings (формат)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666728"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="8a3f2-103">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-103">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="8a3f2-104">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-104">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="8a3f2-105">К общим параметрам относятся отображение ошибок, перенос текста в таблицы, определение порядка развертывания коллекций и многое другое.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-105">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="8a3f2-106">Элемент Configuration (Format) Дефаултсеттингс (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-106">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a3f2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a3f2-107">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a3f2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a3f2-108">Attributes and Elements</span></span>

<span data-ttu-id="8a3f2-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемента.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-109">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a3f2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a3f2-110">Attributes</span></span>

<span data-ttu-id="8a3f2-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a3f2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a3f2-112">Child Elements</span></span>

|<span data-ttu-id="8a3f2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a3f2-113">Element</span></span>|<span data-ttu-id="8a3f2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a3f2-115">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-115">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="8a3f2-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-116">Optional element.</span></span><br /><br /> <span data-ttu-id="8a3f2-117">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-117">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="8a3f2-118">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-118">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="8a3f2-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-119">Optional element.</span></span><br /><br /> <span data-ttu-id="8a3f2-120">Определяет различные способы развертывания объектов .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-120">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="8a3f2-121">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-121">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="8a3f2-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8a3f2-123">Указывает минимальное число свойств, которое должен иметь объект для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-123">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="8a3f2-124">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-124">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="8a3f2-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-125">Optional element.</span></span><br /><br /> <span data-ttu-id="8a3f2-126">Указывает, что полная запись об ошибке отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-126">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="8a3f2-127">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-127">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="8a3f2-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-128">Optional element.</span></span><br /><br /> <span data-ttu-id="8a3f2-129">Указывает, что данные в таблице перемещаются на следующую строку, если она не умещается в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-129">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8a3f2-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a3f2-130">Parent Elements</span></span>

|<span data-ttu-id="8a3f2-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a3f2-131">Element</span></span>|<span data-ttu-id="8a3f2-132">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3f2-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a3f2-133">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="8a3f2-133">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="8a3f2-134">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="8a3f2-134">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8a3f2-135">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8a3f2-135">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="8a3f2-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a3f2-136">See Also</span></span>

[<span data-ttu-id="8a3f2-137">Элемент настройки</span><span class="sxs-lookup"><span data-stu-id="8a3f2-137">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="8a3f2-138">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-138">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="8a3f2-139">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-139">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="8a3f2-140">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-140">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="8a3f2-141">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-141">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="8a3f2-142">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="8a3f2-142">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="8a3f2-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3f2-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
