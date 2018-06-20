---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Фильтрация результатов поиска
ms.openlocfilehash: eafbc993a37eaee7413102ef9d669a6b07d6ff6e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188814"
---
# <a name="filtering-search-results"></a><span data-ttu-id="350a3-103">Фильтрация результатов поиска</span><span class="sxs-lookup"><span data-stu-id="350a3-103">Filtering search results</span></span>

<span data-ttu-id="350a3-104">На [вкладке "Элементы"](https://www.powershellgallery.com/items) отображаются все доступные элементы в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="350a3-104">The [Items tab](https://www.powershellgallery.com/items) displays all available items in the PowerShell Gallery.</span></span>

<span data-ttu-id="350a3-105">Есть несколько способов фильтрации, сортировки и поиска элементов.</span><span class="sxs-lookup"><span data-stu-id="350a3-105">There are several ways to filter, sort, and search the items.</span></span>
<span data-ttu-id="350a3-106">Чтобы узнать больше о каком-либо элементе, щелкните его.</span><span class="sxs-lookup"><span data-stu-id="350a3-106">To see more details about a particular item, click the item.</span></span>

## <a name="filter-by"></a><span data-ttu-id="350a3-107">Фильтровать по</span><span class="sxs-lookup"><span data-stu-id="350a3-107">Filter By</span></span>

<span data-ttu-id="350a3-108">В раскрывающемся списке в разделе "Фильтровать по" можно отфильтровать результаты по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="350a3-108">The drop-down under "Filter By" allows users to filter the results by:</span></span>
- <span data-ttu-id="350a3-109">"Включить предварительные выпуски";</span><span class="sxs-lookup"><span data-stu-id="350a3-109">Include Prerelease</span></span>
- <span data-ttu-id="350a3-110">"Только стабильные".</span><span class="sxs-lookup"><span data-stu-id="350a3-110">Stable Only</span></span>

<span data-ttu-id="350a3-111">Сведения о параметрах "Предварительный выпуск" и "Стабильный" см. в статье о [добавленной функции управления предварительными выпусками в PowerShellGet и коллекции PowerShell](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) в блоге команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="350a3-111">For information about "Prerelease" and "Stable", see [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) in the PowerShell Team Blog.</span></span>

<span data-ttu-id="350a3-112">Установив флажки в раскрывающемся списке, можно отфильтровать результаты по:</span><span class="sxs-lookup"><span data-stu-id="350a3-112">The checkboxes under the drop-down allow users to filter the results by:</span></span>
- <span data-ttu-id="350a3-113">Типы элементов</span><span class="sxs-lookup"><span data-stu-id="350a3-113">Item Types</span></span>
  - <span data-ttu-id="350a3-114">Модуль</span><span class="sxs-lookup"><span data-stu-id="350a3-114">Module</span></span>
  - <span data-ttu-id="350a3-115">Скрипт</span><span class="sxs-lookup"><span data-stu-id="350a3-115">Script</span></span>
- <span data-ttu-id="350a3-116">Категории</span><span class="sxs-lookup"><span data-stu-id="350a3-116">Categories</span></span>
  - <span data-ttu-id="350a3-117">Командлет</span><span class="sxs-lookup"><span data-stu-id="350a3-117">Cmdlet</span></span>
  - <span data-ttu-id="350a3-118">Ресурс DSC</span><span class="sxs-lookup"><span data-stu-id="350a3-118">DSC Resource</span></span>
  - <span data-ttu-id="350a3-119">Функция</span><span class="sxs-lookup"><span data-stu-id="350a3-119">Function</span></span>
  - <span data-ttu-id="350a3-120">Возможность роли</span><span class="sxs-lookup"><span data-stu-id="350a3-120">Role Capability</span></span>
  - <span data-ttu-id="350a3-121">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="350a3-121">Workflow</span></span>

<span data-ttu-id="350a3-122">Чтобы просмотреть только модули в коллекции PowerShell, щелкните "Модуль" в списке типов элементов.</span><span class="sxs-lookup"><span data-stu-id="350a3-122">To see only modules in the PowerShell Gallery, check Module in the Item Types.</span></span>
<span data-ttu-id="350a3-123">Аналогичным образом, чтобы просмотреть только скрипты в коллекции PowerShell, щелкните "Скрипт" в списке с типами элементов.</span><span class="sxs-lookup"><span data-stu-id="350a3-123">Similarly, to see only scripts in the PowerShell Gallery, check Script in the Item Types.</span></span>

> [!NOTE]
> <span data-ttu-id="350a3-124">При обработке фильтрами используется инклюзивный подход.</span><span class="sxs-lookup"><span data-stu-id="350a3-124">Filters are inclusive.</span></span>
> <span data-ttu-id="350a3-125">Пример. Элемент, содержащий как командлеты, так и функции, будет отображаться как при выборе категорий "Командлет" или "Функция" (как по-отдельности, так и вместе).</span><span class="sxs-lookup"><span data-stu-id="350a3-125">Example: An item containing both cmdlets and functions will appear if either Cmdlet or Function (or both) are checked.</span></span>
> <span data-ttu-id="350a3-126">Если ни одна из этих категорий не выбрана, элемент не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="350a3-126">If neither are selected, the item will not appear.</span></span>
> <span data-ttu-id="350a3-127">Аналогично, если выбираются все категории, будут отображаться только элементы, содержащие хотя бы одну из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="350a3-127">Similarly, if all categories are selected, only items containing one of those categories will appear.</span></span>
> <span data-ttu-id="350a3-128">**Элементы, которые не принадлежат ни к одной из этих категорий, отображаться не будут.**</span><span class="sxs-lookup"><span data-stu-id="350a3-128">**Items that do not belong to any of those categories will not appear.**</span></span>

## <a name="sort-by"></a><span data-ttu-id="350a3-129">Сортировать по</span><span class="sxs-lookup"><span data-stu-id="350a3-129">Sort By</span></span>

<span data-ttu-id="350a3-130">Раскрывающийся список "Сортировать по" позволяет сортировать результаты по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="350a3-130">The Sort By drop-down allows users to sort the results by:</span></span>
- <span data-ttu-id="350a3-131">"Популярность" — определяется по числу скачиваний;</span><span class="sxs-lookup"><span data-stu-id="350a3-131">Popularity - Popularity is determined by Download Count</span></span>
- <span data-ttu-id="350a3-132">A–Z — в алфавитном порядке по имени элемента;</span><span class="sxs-lookup"><span data-stu-id="350a3-132">A-Z - Alphabetically by item name</span></span>
- <span data-ttu-id="350a3-133">"Последние" — элементы располагаются в порядке даты их публикации.</span><span class="sxs-lookup"><span data-stu-id="350a3-133">Recent - Items appear in order of publish date</span></span>

## <a name="search-box"></a><span data-ttu-id="350a3-134">Поле поиска</span><span class="sxs-lookup"><span data-stu-id="350a3-134">Search Box</span></span>

<span data-ttu-id="350a3-135">Поле поиска позволяет искать элементы по ключевым словам.</span><span class="sxs-lookup"><span data-stu-id="350a3-135">The Search Box allows users to search the items on keywords.</span></span>
<span data-ttu-id="350a3-136">Дополнительные сведения см. в статье [Синтаксис поиска по коллекции](search-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="350a3-136">For more information, see [Gallery Search Syntax](search-syntax.md).</span></span>