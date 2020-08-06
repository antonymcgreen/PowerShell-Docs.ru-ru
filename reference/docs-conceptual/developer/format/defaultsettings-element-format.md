---
title: Элемент Дефаултсеттингс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787739"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="b9ae5-102">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="b9ae5-103">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="b9ae5-104">К общим параметрам относятся отображение ошибок, перенос текста в таблицы, определение порядка развертывания коллекций и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="b9ae5-105">Элемент Configuration (Format) Дефаултсеттингс (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b9ae5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9ae5-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b9ae5-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9ae5-107">Attributes and Elements</span></span>

<span data-ttu-id="b9ae5-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемента.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b9ae5-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9ae5-109">Attributes</span></span>

<span data-ttu-id="b9ae5-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b9ae5-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9ae5-111">Child Elements</span></span>

|<span data-ttu-id="b9ae5-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9ae5-112">Element</span></span>|<span data-ttu-id="b9ae5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b9ae5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b9ae5-114">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="b9ae5-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b9ae5-116">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="b9ae5-117">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="b9ae5-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b9ae5-119">Определяет различные способы развертывания объектов .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="b9ae5-120">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="b9ae5-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="b9ae5-122">Указывает минимальное число свойств, которое должен иметь объект для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="b9ae5-123">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="b9ae5-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="b9ae5-125">Указывает, что полная запись об ошибке отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="b9ae5-126">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="b9ae5-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-127">Optional element.</span></span><br /><br /> <span data-ttu-id="b9ae5-128">Указывает, что данные в таблице перемещаются на следующую строку, если она не умещается в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b9ae5-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9ae5-129">Parent Elements</span></span>

|<span data-ttu-id="b9ae5-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9ae5-130">Element</span></span>|<span data-ttu-id="b9ae5-131">Описание</span><span class="sxs-lookup"><span data-stu-id="b9ae5-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b9ae5-132">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="b9ae5-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="b9ae5-133">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="b9ae5-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b9ae5-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9ae5-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b9ae5-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b9ae5-135">See Also</span></span>

[<span data-ttu-id="b9ae5-136">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="b9ae5-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="b9ae5-137">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="b9ae5-138">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="b9ae5-139">Пропертикаунтфортабле (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="b9ae5-140">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="b9ae5-141">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="b9ae5-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="b9ae5-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9ae5-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
