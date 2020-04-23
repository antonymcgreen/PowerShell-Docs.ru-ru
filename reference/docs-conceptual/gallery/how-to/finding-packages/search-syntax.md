---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Синтаксис поиска по коллекции
ms.openlocfilehash: aabcaa1f1b5b641ab5033c9ba2e358477c84a23b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71328455"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="647aa-103">Синтаксис поиска по коллекции</span><span class="sxs-lookup"><span data-stu-id="647aa-103">Gallery Search Syntax</span></span>

<span data-ttu-id="647aa-104">Выполнять поиск в коллекции PowerShell на [веб-сайте коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="647aa-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span>
<span data-ttu-id="647aa-105">На веб-сайте коллекции PowerShell есть текстовое окно поиска, где можно использовать слова, фразы и выражения с ключевыми словами, чтобы сузить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="647aa-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="647aa-106">Поиск по ключевым словам</span><span class="sxs-lookup"><span data-stu-id="647aa-106">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="647aa-107">Поисковая система пытается показать соответствующие документы, содержащие все три ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="647aa-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="647aa-108">Поиск с использованием ключевых слов и фраз</span><span class="sxs-lookup"><span data-stu-id="647aa-108">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="647aa-109">При вводе фразы, заключенной в кавычки (""), выполняется поиск конкретной фразы, а не отдельных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="647aa-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="647aa-110">Соответствующие документы обычно содержат точную фразу azure sql, включая варианты (с другим регистром букв, например Azure SQL), а также обычно содержат слово "развертывание".</span><span class="sxs-lookup"><span data-stu-id="647aa-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="647aa-111">Фильтрация по полям</span><span class="sxs-lookup"><span data-stu-id="647aa-111">Filtering on fields</span></span>

<span data-ttu-id="647aa-112">Вы можете выполнять поиск конкретного идентификатора пакета (ID, Id или id) или других полей, указывая перед условиями поиска имя поля.</span><span class="sxs-lookup"><span data-stu-id="647aa-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="647aa-113">В настоящее время для поиска доступны следующие поля: Id, Version, Tags, Author, Owner, Functions, Cmdlets, DscResources и PowerShellVersion.</span><span class="sxs-lookup"><span data-stu-id="647aa-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="647aa-114">[В чем отличие между идентификатором и заголовком?</span><span class="sxs-lookup"><span data-stu-id="647aa-114">[What's the difference between ID and Title?</span></span> <span data-ttu-id="647aa-115">Идентификатор — это имя, используемое в консоли.</span><span class="sxs-lookup"><span data-stu-id="647aa-115">ID is the name you use in the console.</span></span> <span data-ttu-id="647aa-116">Заголовок — это то, что отображается в верхней части страницы пакета в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="647aa-116">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="647aa-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="647aa-117">Examples</span></span>

    ID:PSReadline
    
<span data-ttu-id="647aa-118">Находит пакеты с идентификатором, содержащим PSReadline.</span><span class="sxs-lookup"><span data-stu-id="647aa-118">finds packages with an ID containing "PSReadline".</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="647aa-119">— еще один способ поиска пакетов с текстом AzureRM.Profile в поле ID.</span><span class="sxs-lookup"><span data-stu-id="647aa-119">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="647aa-120">Фильтр Id — это сопоставление вложенных строк, поэтому при следующем поиске:</span><span class="sxs-lookup"><span data-stu-id="647aa-120">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="647aa-121">Этот фильтр выводит результаты, содержащие AzureRM.Profile и Azure.Storage.</span><span class="sxs-lookup"><span data-stu-id="647aa-121">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="647aa-122">можно также выполнить поиск с несколькими ключевыми словами в одном поле;</span><span class="sxs-lookup"><span data-stu-id="647aa-122">You can also search for multiple keywords in a single field.</span></span> 

    id:azure tags:intellisense

<span data-ttu-id="647aa-123">Можно выполнять поиск фраз с использованием двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="647aa-123">And you can perform phrase searches using double quotes:</span></span>

    id:"azure.storage"

<span data-ttu-id="647aa-124">Чтобы найти все пакеты с тегом DSC:</span><span class="sxs-lookup"><span data-stu-id="647aa-124">To search all packages with DSC tag.</span></span>

    Tags:DSC

<span data-ttu-id="647aa-125">Чтобы найти все пакеты с указанной функцией:</span><span class="sxs-lookup"><span data-stu-id="647aa-125">To search all packages with the specified function.</span></span>

    Functions:Get-TreeSize

<span data-ttu-id="647aa-126">Чтобы найти все пакеты с указанным командлетом:</span><span class="sxs-lookup"><span data-stu-id="647aa-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:Get-AzureRmEnvironment

<span data-ttu-id="647aa-127">Чтобы найти все пакеты с указанным именем ресурса DSC:</span><span class="sxs-lookup"><span data-stu-id="647aa-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:xArchive

<span data-ttu-id="647aa-128">Чтобы найти все пакеты с указанной версией PowerShellVersion:</span><span class="sxs-lookup"><span data-stu-id="647aa-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:2.0

<span data-ttu-id="647aa-129">Наконец, если вы используете поле, которое не поддерживается, например commands, мы просто проигнорируем его и выполним поиск по всем полям.</span><span class="sxs-lookup"><span data-stu-id="647aa-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="647aa-130">Поэтому следующий запрос</span><span class="sxs-lookup"><span data-stu-id="647aa-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="647aa-131">интерпретируется точно так же, как этот запрос:</span><span class="sxs-lookup"><span data-stu-id="647aa-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
