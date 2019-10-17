---
ms.date: 09/25/2019
keywords: powershell,командлет
title: Использование документации по PowerShell
ms.openlocfilehash: 9e3d5828d6bdb4ef14701994f146354a041efaea
ms.sourcegitcommit: a80bb79b85deab8ae3c21de56d1ee432fdd92628
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2019
ms.locfileid: "72281648"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="3541f-103">Использование документации по PowerShell</span><span class="sxs-lookup"><span data-stu-id="3541f-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="3541f-104">Добро пожаловать в интерактивную документацию по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3541f-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="3541f-105">Этот сайт содержит справочник по командлетам для следующих версий PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3541f-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="3541f-106">PowerShell 7 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="3541f-106">PowerShell 7 (preview)</span></span>
- <span data-ttu-id="3541f-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="3541f-107">PowerShell 6</span></span>
- <span data-ttu-id="3541f-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="3541f-108">PowerShell 5.1</span></span>
- <span data-ttu-id="3541f-109">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3541f-109">PowerShell 5.0</span></span>
- <span data-ttu-id="3541f-110">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="3541f-110">PowerShell 4.0</span></span>
- <span data-ttu-id="3541f-111">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="3541f-111">PowerShell 3.0</span></span>

## <a name="selecting-your-version"></a><span data-ttu-id="3541f-112">Выбор версии</span><span class="sxs-lookup"><span data-stu-id="3541f-112">Selecting your version</span></span>

<span data-ttu-id="3541f-113">По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3541f-113">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="3541f-114">Некоторые командлеты работают по-разному в различных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3541f-114">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="3541f-115">Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3541f-115">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="3541f-116">Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3541f-116">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Средство выбора](images/how-to-use-docs/picker-vall.gif)

<span data-ttu-id="3541f-118">Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="3541f-118">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="3541f-119">В следующем примере показаны выходные данные для Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="3541f-119">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="searching-for-articles"></a><span data-ttu-id="3541f-120">Поиск статей</span><span class="sxs-lookup"><span data-stu-id="3541f-120">Searching for articles</span></span>

<span data-ttu-id="3541f-121">Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии.</span><span class="sxs-lookup"><span data-stu-id="3541f-121">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="3541f-122">Просто введите слово, которое есть в заголовке статьи.</span><span class="sxs-lookup"><span data-stu-id="3541f-122">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="3541f-123">На странице отображается список соответствующих статей.</span><span class="sxs-lookup"><span data-stu-id="3541f-123">The page displays a list of matching articles.</span></span> <span data-ttu-id="3541f-124">Можно также выбрать вариант поиска по всему сайту из этого списка.</span><span class="sxs-lookup"><span data-stu-id="3541f-124">You can also select the option to search the entire site from that list.</span></span>

![Поле фильтра](images/how-to-use-docs/filter-search.gif)
