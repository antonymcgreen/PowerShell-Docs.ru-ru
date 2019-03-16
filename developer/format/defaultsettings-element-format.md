---
title: Элемент DefaultSettings (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059071"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="3015b-102">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="3015b-103">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="3015b-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="3015b-104">Общие параметры включают отображение ошибок, переноса текста в таблицах, определение развернуты как коллекции и многое другое.</span><span class="sxs-lookup"><span data-stu-id="3015b-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="3015b-105">Элемент DefaultSettings конфигурации элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3015b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3015b-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3015b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3015b-107">Attributes and Elements</span></span>

<span data-ttu-id="3015b-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3015b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3015b-109">Attributes</span></span>

<span data-ttu-id="3015b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3015b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3015b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3015b-111">Child Elements</span></span>

|<span data-ttu-id="3015b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3015b-112">Element</span></span>|<span data-ttu-id="3015b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3015b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3015b-114">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="3015b-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3015b-116">Указывает, что строка #ERR отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="3015b-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="3015b-117">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="3015b-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3015b-119">Определяет, что объекты .NET, разворачиваются, когда они отображаются в представлении различным образом.</span><span class="sxs-lookup"><span data-stu-id="3015b-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="3015b-120">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="3015b-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3015b-122">Указывает минимальное число свойств, которые объект должен иметь для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="3015b-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="3015b-123">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="3015b-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3015b-125">Указывает, что запись об ошибке полный отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="3015b-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="3015b-126">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="3015b-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3015b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="3015b-128">Указывает, что данные в таблице перемещается на следующую строку, если оно не поместится в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="3015b-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3015b-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3015b-129">Parent Elements</span></span>

|<span data-ttu-id="3015b-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="3015b-130">Element</span></span>|<span data-ttu-id="3015b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="3015b-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3015b-132">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="3015b-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="3015b-133">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="3015b-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3015b-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="3015b-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3015b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3015b-135">See Also</span></span>

[<span data-ttu-id="3015b-136">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="3015b-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="3015b-137">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="3015b-138">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="3015b-139">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="3015b-140">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="3015b-141">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="3015b-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="3015b-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3015b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
