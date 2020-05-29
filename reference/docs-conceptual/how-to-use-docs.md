---
ms.date: 05/22/2020
keywords: powershell,командлет
title: Использование документации по PowerShell
ms.openlocfilehash: 259eb1eea1dc7e8b5ae5730f97c938b838a320bf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808271"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="a6d29-103">Использование документации по PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d29-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="a6d29-104">Добро пожаловать в интерактивную документацию по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d29-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="a6d29-105">Этот сайт содержит справочник по командлетам для следующих версий PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a6d29-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="a6d29-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="a6d29-106">PowerShell 7</span></span>
- <span data-ttu-id="a6d29-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="a6d29-107">PowerShell 6</span></span>
- <span data-ttu-id="a6d29-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a6d29-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="a6d29-109">Поиск статей и выбор версии</span><span class="sxs-lookup"><span data-stu-id="a6d29-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="a6d29-110">Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии.</span><span class="sxs-lookup"><span data-stu-id="a6d29-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="a6d29-111">Просто введите слово, которое есть в заголовке статьи.</span><span class="sxs-lookup"><span data-stu-id="a6d29-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="a6d29-112">На странице отображается список соответствующих статей.</span><span class="sxs-lookup"><span data-stu-id="a6d29-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="a6d29-113">Можно также выбрать вариант поиска по всему сайту из этого списка.</span><span class="sxs-lookup"><span data-stu-id="a6d29-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="a6d29-114">По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d29-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="a6d29-115">Некоторые командлеты работают по-разному в различных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d29-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="a6d29-116">Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d29-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="a6d29-117">Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d29-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Средство выбора](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="a6d29-119">Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="a6d29-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="a6d29-120">В следующем примере показаны выходные данные для Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="a6d29-120">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="a6d29-121">Поиск статей для предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="a6d29-121">Finding articles for previous versions</span></span>

<span data-ttu-id="a6d29-122">Документация по предыдущим версиям PowerShell сохранена в архиве на сайте [предыдущих версий](https://aka.ms/PSLegacyDocs).</span><span class="sxs-lookup"><span data-stu-id="a6d29-122">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="a6d29-123">Этот сайт содержит документацию по следующим темам:</span><span class="sxs-lookup"><span data-stu-id="a6d29-123">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="a6d29-124">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="a6d29-124">PowerShell 3.0</span></span>
- <span data-ttu-id="a6d29-125">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="a6d29-125">PowerShell 4.0</span></span>
- <span data-ttu-id="a6d29-126">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a6d29-126">PowerShell 5.0</span></span>
- <span data-ttu-id="a6d29-127">Рабочие процессы PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d29-127">PowerShell Workflows</span></span>
- <span data-ttu-id="a6d29-128">PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="a6d29-128">PowerShell Web Access</span></span>
