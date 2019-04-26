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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066351"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="33951-102">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="33951-103">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="33951-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="33951-104">Общие параметры включают отображение ошибок, переноса текста в таблицах, определение развернуты как коллекции и многое другое.</span><span class="sxs-lookup"><span data-stu-id="33951-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="33951-105">Элемент DefaultSettings конфигурации элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="33951-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33951-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33951-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33951-107">Attributes and Elements</span></span>

<span data-ttu-id="33951-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="33951-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33951-109">Attributes</span></span>

<span data-ttu-id="33951-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="33951-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="33951-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33951-111">Child Elements</span></span>

|<span data-ttu-id="33951-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="33951-112">Element</span></span>|<span data-ttu-id="33951-113">Описание</span><span class="sxs-lookup"><span data-stu-id="33951-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33951-114">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="33951-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-115">Optional element.</span></span><br /><br /> <span data-ttu-id="33951-116">Указывает, что строка #ERR отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="33951-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="33951-117">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="33951-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-118">Optional element.</span></span><br /><br /> <span data-ttu-id="33951-119">Определяет, что объекты .NET, разворачиваются, когда они отображаются в представлении различным образом.</span><span class="sxs-lookup"><span data-stu-id="33951-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="33951-120">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="33951-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-121">Optional element.</span></span><br /><br /> <span data-ttu-id="33951-122">Указывает минимальное число свойств, которые объект должен иметь для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="33951-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="33951-123">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="33951-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-124">Optional element.</span></span><br /><br /> <span data-ttu-id="33951-125">Указывает, что запись об ошибке полный отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="33951-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="33951-126">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="33951-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33951-127">Optional element.</span></span><br /><br /> <span data-ttu-id="33951-128">Указывает, что данные в таблице перемещается на следующую строку, если оно не поместится в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="33951-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33951-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33951-129">Parent Elements</span></span>

|<span data-ttu-id="33951-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="33951-130">Element</span></span>|<span data-ttu-id="33951-131">Описание</span><span class="sxs-lookup"><span data-stu-id="33951-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33951-132">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="33951-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="33951-133">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="33951-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33951-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="33951-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="33951-135">См. также</span><span class="sxs-lookup"><span data-stu-id="33951-135">See Also</span></span>

[<span data-ttu-id="33951-136">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="33951-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="33951-137">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="33951-138">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="33951-139">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="33951-140">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="33951-141">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="33951-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="33951-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="33951-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
