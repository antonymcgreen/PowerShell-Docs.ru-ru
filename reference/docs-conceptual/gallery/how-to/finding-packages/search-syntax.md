---
ms.date: 06/12/2017
title: Синтаксис поиска по коллекции
description: В этой статье описывается пользовательский интерфейс, используемые для поиска содержимого в коллекции PowerShell.
ms.openlocfilehash: 7ad486095647f99056b37c2ca1a50db099a166c0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661376"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="d6885-103">Синтаксис поиска по коллекции</span><span class="sxs-lookup"><span data-stu-id="d6885-103">Gallery Search Syntax</span></span>

<span data-ttu-id="d6885-104">Выполнять поиск в коллекции PowerShell на [веб-сайте коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="d6885-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span> <span data-ttu-id="d6885-105">На веб-сайте коллекции PowerShell есть текстовое окно поиска, где можно использовать слова, фразы и выражения с ключевыми словами, чтобы сузить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="d6885-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="d6885-106">Поиск по ключевым словам</span><span class="sxs-lookup"><span data-stu-id="d6885-106">Search by Keywords</span></span>

```Syntax
dsc azure sql
```

<span data-ttu-id="d6885-107">Поисковая система пытается показать соответствующие документы, содержащие все три ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="d6885-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="d6885-108">Поиск с использованием ключевых слов и фраз</span><span class="sxs-lookup"><span data-stu-id="d6885-108">Search using Phrases and keywords</span></span>

```Syntax
"azure sql" deployment
```

<span data-ttu-id="d6885-109">При вводе фразы, заключенной в кавычки (""), выполняется поиск конкретной фразы, а не отдельных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="d6885-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span> <span data-ttu-id="d6885-110">Соответствующие документы обычно содержат точную фразу azure sql, включая варианты (с другим регистром букв, например Azure SQL), а также обычно содержат слово "развертывание".</span><span class="sxs-lookup"><span data-stu-id="d6885-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="d6885-111">Фильтрация по полям</span><span class="sxs-lookup"><span data-stu-id="d6885-111">Filtering on fields</span></span>

<span data-ttu-id="d6885-112">Вы можете выполнять поиск конкретного идентификатора пакета (ID, Id или id) или других полей, указывая перед условиями поиска имя поля.</span><span class="sxs-lookup"><span data-stu-id="d6885-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="d6885-113">В настоящее время для поиска доступны следующие поля: Id, Version, Tags, Author, Owner, Functions, Cmdlets, DscResources и PowerShellVersion.</span><span class="sxs-lookup"><span data-stu-id="d6885-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

- <span data-ttu-id="d6885-114">Идентификатор — это имя, используемое в консоли.</span><span class="sxs-lookup"><span data-stu-id="d6885-114">ID is the name you use in the console.</span></span>
- <span data-ttu-id="d6885-115">Заголовок — это то, что отображается в верхней части страницы пакета в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="d6885-115">Title is what is shown at the top of the package page in search results.</span></span>

## <a name="examples"></a><span data-ttu-id="d6885-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="d6885-116">Examples</span></span>

```Syntax
ID:PSReadline
```

<span data-ttu-id="d6885-117">Находит пакеты с идентификатором, содержащим PSReadline.</span><span class="sxs-lookup"><span data-stu-id="d6885-117">finds packages with an ID containing "PSReadline".</span></span>

```Syntax
Id:"AzureRM.Profile"
```

<span data-ttu-id="d6885-118">— еще один способ поиска пакетов с текстом AzureRM.Profile в поле ID.</span><span class="sxs-lookup"><span data-stu-id="d6885-118">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="d6885-119">Фильтр Id — это сопоставление вложенных строк, поэтому при следующем поиске:</span><span class="sxs-lookup"><span data-stu-id="d6885-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

```Syntax
Id:"azure"
```

<span data-ttu-id="d6885-120">Этот фильтр выводит результаты, содержащие AzureRM.Profile и Azure.Storage.</span><span class="sxs-lookup"><span data-stu-id="d6885-120">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="d6885-121">можно также выполнить поиск с несколькими ключевыми словами в одном поле;</span><span class="sxs-lookup"><span data-stu-id="d6885-121">You can also search for multiple keywords in a single field.</span></span>

```Syntax
id:azure tags:intellisense
```

<span data-ttu-id="d6885-122">Можно выполнять поиск фраз с использованием двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="d6885-122">And you can perform phrase searches using double quotes:</span></span>

```Syntax
id:"azure.storage"
```

<span data-ttu-id="d6885-123">Чтобы найти все пакеты с тегом DSC:</span><span class="sxs-lookup"><span data-stu-id="d6885-123">To search all packages with DSC tag.</span></span>

```Syntax
Tags:DSC
```

<span data-ttu-id="d6885-124">Чтобы найти все пакеты с указанной функцией:</span><span class="sxs-lookup"><span data-stu-id="d6885-124">To search all packages with the specified function.</span></span>

```Syntax
Functions:Get-TreeSize
```

<span data-ttu-id="d6885-125">Чтобы найти все пакеты с указанным командлетом:</span><span class="sxs-lookup"><span data-stu-id="d6885-125">To search all packages with the specified cmdlet.</span></span>

```Syntax
Cmdlets:Get-AzureRmEnvironment
```

<span data-ttu-id="d6885-126">Чтобы найти все пакеты с указанным именем ресурса DSC:</span><span class="sxs-lookup"><span data-stu-id="d6885-126">To search all packages with the specified DSC Resource name.</span></span>

```Syntax
DscResources:xArchive
```

<span data-ttu-id="d6885-127">Чтобы найти все пакеты с указанной версией PowerShellVersion:</span><span class="sxs-lookup"><span data-stu-id="d6885-127">To search all packages with the specified PowerShellVersion</span></span>

```Syntax
PowerShellVersion:2.0
```

<span data-ttu-id="d6885-128">Наконец, если вы используете поле, которое не поддерживается, например commands, мы просто проигнорируем его и выполним поиск по всем полям.</span><span class="sxs-lookup"><span data-stu-id="d6885-128">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="d6885-129">Поэтому следующий запрос</span><span class="sxs-lookup"><span data-stu-id="d6885-129">So the following query</span></span>

```Syntax
commands:blobs storage
```

<span data-ttu-id="d6885-130">интерпретируется точно так же, как этот запрос:</span><span class="sxs-lookup"><span data-stu-id="d6885-130">Is interpreted exactly the same as this query:</span></span>

```Syntax
blobs storage
```
