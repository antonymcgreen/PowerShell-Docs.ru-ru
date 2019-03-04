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
ms.openlocfilehash: 59cc0514087cc52438e0d1271b8b77a7799eb32c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855670"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="44569-102">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="44569-103">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="44569-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="44569-104">Общие параметры включают отображение ошибок, переноса текста в таблицах, определение развернуты как коллекции и многое другое.</span><span class="sxs-lookup"><span data-stu-id="44569-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="44569-105">Элемент DefaultSettings конфигурации элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44569-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44569-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44569-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44569-107">Attributes and Elements</span></span>

<span data-ttu-id="44569-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44569-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44569-109">Attributes</span></span>

<span data-ttu-id="44569-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="44569-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44569-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44569-111">Child Elements</span></span>

|<span data-ttu-id="44569-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="44569-112">Element</span></span>|<span data-ttu-id="44569-113">Описание</span><span class="sxs-lookup"><span data-stu-id="44569-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44569-114">Элемент DisplayError (Frmat)</span><span class="sxs-lookup"><span data-stu-id="44569-114">DisplayError Element (Frmat)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="44569-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-115">Optional element.</span></span><br /><br /> <span data-ttu-id="44569-116">Указывает, что строка #ERR отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="44569-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="44569-117">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="44569-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-118">Optional element.</span></span><br /><br /> <span data-ttu-id="44569-119">Определяет, что объекты .NET, разворачиваются, когда они отображаются в представлении различным образом.</span><span class="sxs-lookup"><span data-stu-id="44569-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="44569-120">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="44569-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-121">Optional element.</span></span><br /><br /> <span data-ttu-id="44569-122">Указывает минимальное число свойств, которые объект должен иметь для отображения объекта в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="44569-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="44569-123">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="44569-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-124">Optional element.</span></span><br /><br /> <span data-ttu-id="44569-125">Указывает, что запись об ошибке полный отображаются при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="44569-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="44569-126">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="44569-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44569-127">Optional element.</span></span><br /><br /> <span data-ttu-id="44569-128">Указывает, что данные в таблице перемещается на следующую строку, если оно не поместится в ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="44569-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="44569-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44569-129">Parent Elements</span></span>

|<span data-ttu-id="44569-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="44569-130">Element</span></span>|<span data-ttu-id="44569-131">Описание</span><span class="sxs-lookup"><span data-stu-id="44569-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44569-132">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="44569-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="44569-133">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="44569-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44569-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="44569-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="44569-135">См. также</span><span class="sxs-lookup"><span data-stu-id="44569-135">See Also</span></span>

[<span data-ttu-id="44569-136">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="44569-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="44569-137">Элемент DisplayError (Frmat)</span><span class="sxs-lookup"><span data-stu-id="44569-137">DisplayError Element (Frmat)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="44569-138">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="44569-139">PropertyCountForTable (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="44569-140">Элемент ShowError (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="44569-141">Элемент WrapTables (формат)</span><span class="sxs-lookup"><span data-stu-id="44569-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="44569-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="44569-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
