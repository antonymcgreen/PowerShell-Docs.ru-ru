---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент DisplayError (формат)
description: Элемент DisplayError (формат)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649921"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="78418-103">Элемент DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="78418-103">DisplayError Element (Format)</span></span>

<span data-ttu-id="78418-104">Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="78418-104">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="78418-105">Элемент Configuration (Format) Дефаултсеттингс элемент (Format) DisplayError (формат)</span><span class="sxs-lookup"><span data-stu-id="78418-105">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78418-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78418-106">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78418-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78418-107">Attributes and Elements</span></span>

<span data-ttu-id="78418-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DisplayError` элемента.</span><span class="sxs-lookup"><span data-stu-id="78418-108">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="78418-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78418-109">Attributes</span></span>

<span data-ttu-id="78418-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78418-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78418-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78418-111">Child Elements</span></span>

<span data-ttu-id="78418-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78418-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78418-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78418-113">Parent Elements</span></span>

|<span data-ttu-id="78418-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="78418-114">Element</span></span>|<span data-ttu-id="78418-115">Описание</span><span class="sxs-lookup"><span data-stu-id="78418-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78418-116">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="78418-116">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="78418-117">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="78418-117">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78418-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="78418-118">Remarks</span></span>

<span data-ttu-id="78418-119">По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым.</span><span class="sxs-lookup"><span data-stu-id="78418-119">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="78418-120">Если этот элемент имеет значение true, будет отображена строка #ERR.</span><span class="sxs-lookup"><span data-stu-id="78418-120">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="78418-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="78418-121">See Also</span></span>

[<span data-ttu-id="78418-122">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="78418-122">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="78418-123">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="78418-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
