---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Синтаксис поиска по коллекции
ms.openlocfilehash: aabcaa1f1b5b641ab5033c9ba2e358477c84a23b
ms.sourcegitcommit: e24525046dd37166b9d83eeecdc534726316f429
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2018
ms.locfileid: "52742862"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="3ff24-103">Синтаксис поиска по коллекции</span><span class="sxs-lookup"><span data-stu-id="3ff24-103">Gallery Search Syntax</span></span>

<span data-ttu-id="3ff24-104">Можно найти в коллекции PowerShell с помощью [веб-сайте коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="3ff24-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span>
<span data-ttu-id="3ff24-105">Веб-сайт коллекции PowerShell содержит текстовое окно где слова, фразы и выражения можно использовать для сужения результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="3ff24-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="3ff24-106">Поиск по ключевым словам</span><span class="sxs-lookup"><span data-stu-id="3ff24-106">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="3ff24-107">Поиск пытается найти соответствующие документы, содержащие все три ключевые слова и вернуть соответствующие документы.</span><span class="sxs-lookup"><span data-stu-id="3ff24-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="3ff24-108">Поиск с использованием ключевых слов и фраз</span><span class="sxs-lookup"><span data-stu-id="3ff24-108">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="3ff24-109">При вводе фразы, заключенной в кавычки (""), выполняется поиск конкретной фразы, а не отдельных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="3ff24-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="3ff24-110">Соответствующие документы обычно содержат точную фразу azure sql, включая варианты (с другим регистром букв, например Azure SQL), а также обычно содержат слово "развертывание".</span><span class="sxs-lookup"><span data-stu-id="3ff24-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="3ff24-111">Фильтрация по полям</span><span class="sxs-lookup"><span data-stu-id="3ff24-111">Filtering on fields</span></span>

<span data-ttu-id="3ff24-112">Вы можете выполнять поиск конкретного идентификатора пакета (ID, Id или id) или других полей, указывая перед условиями поиска имя поля.</span><span class="sxs-lookup"><span data-stu-id="3ff24-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="3ff24-113">В настоящее время для поиска доступны следующие поля: Id, Version, Tags, Author, Owner, Functions, Cmdlets, DscResources и PowerShellVersion.</span><span class="sxs-lookup"><span data-stu-id="3ff24-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="3ff24-114">[В чем отличие между идентификатором и заголовком?</span><span class="sxs-lookup"><span data-stu-id="3ff24-114">[What's the difference between ID and Title?</span></span> <span data-ttu-id="3ff24-115">Идентификатор — это имя, используемое в консоли.</span><span class="sxs-lookup"><span data-stu-id="3ff24-115">ID is the name you use in the console.</span></span> <span data-ttu-id="3ff24-116">Заголовок — это то, что отображается в верхней части страницы пакета в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="3ff24-116">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="3ff24-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ff24-117">Examples</span></span>

    ID:PSReadline
    
<span data-ttu-id="3ff24-118">Находит все пакеты с Идентификатором, содержащая «PSReadline».</span><span class="sxs-lookup"><span data-stu-id="3ff24-118">finds packages with an ID containing "PSReadline".</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="3ff24-119">— еще один способ поиска пакетов с текстом AzureRM.Profile в поле ID.</span><span class="sxs-lookup"><span data-stu-id="3ff24-119">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="3ff24-120">Фильтр Id — это сопоставление вложенных строк, поэтому при следующем поиске:</span><span class="sxs-lookup"><span data-stu-id="3ff24-120">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="3ff24-121">Это обеспечивает результаты, содержащие AzureRM.Profile "и «Azure.Storage более поздней».</span><span class="sxs-lookup"><span data-stu-id="3ff24-121">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="3ff24-122">можно также выполнить поиск с несколькими ключевыми словами в одном поле;</span><span class="sxs-lookup"><span data-stu-id="3ff24-122">You can also search for multiple keywords in a single field.</span></span> 

    id:azure tags:intellisense

<span data-ttu-id="3ff24-123">И может выполнять поиск фраз с использованием двойных кавычек:</span><span class="sxs-lookup"><span data-stu-id="3ff24-123">And you can perform phrase searches using double quotes:</span></span>

    id:"azure.storage"

<span data-ttu-id="3ff24-124">Чтобы найти все пакеты с тегом DSC:</span><span class="sxs-lookup"><span data-stu-id="3ff24-124">To search all packages with DSC tag.</span></span>

    Tags:DSC

<span data-ttu-id="3ff24-125">Чтобы найти все пакеты с указанной функцией:</span><span class="sxs-lookup"><span data-stu-id="3ff24-125">To search all packages with the specified function.</span></span>

    Functions:Get-TreeSize

<span data-ttu-id="3ff24-126">Чтобы найти все пакеты с указанным командлетом:</span><span class="sxs-lookup"><span data-stu-id="3ff24-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:Get-AzureRmEnvironment

<span data-ttu-id="3ff24-127">Чтобы найти все пакеты с указанным именем ресурса DSC:</span><span class="sxs-lookup"><span data-stu-id="3ff24-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:xArchive

<span data-ttu-id="3ff24-128">Чтобы найти все пакеты с указанной версией PowerShellVersion:</span><span class="sxs-lookup"><span data-stu-id="3ff24-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:2.0

<span data-ttu-id="3ff24-129">Наконец, если вы используете поле, которое не поддерживается, например commands, мы просто проигнорируем его и выполним поиск по всем полям.</span><span class="sxs-lookup"><span data-stu-id="3ff24-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="3ff24-130">Поэтому следующий запрос</span><span class="sxs-lookup"><span data-stu-id="3ff24-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="3ff24-131">интерпретируется точно так же, как этот запрос:</span><span class="sxs-lookup"><span data-stu-id="3ff24-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
