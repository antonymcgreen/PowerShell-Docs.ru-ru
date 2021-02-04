---
ms.date: 07/29/2020
keywords: powershell,командлет
ms.topic: how-to
title: Использование документации по PowerShell
description: В этой статье описывается, как использовать функции данного сайта, включая фильтрацию при поиске и выбор версий.
ms.openlocfilehash: 4779e6e4b17c461d71e9d613d1184b9ce2e7ab7b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "98216088"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="34603-104">Использование документации по PowerShell</span><span class="sxs-lookup"><span data-stu-id="34603-104">How to use the PowerShell documentation</span></span>

<span data-ttu-id="34603-105">Добро пожаловать в интерактивную документацию по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34603-105">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="34603-106">Этот сайт содержит справочник по командлетам для следующих версий PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34603-106">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="34603-107">PowerShell 7.2 (предварительный выпуск)</span><span class="sxs-lookup"><span data-stu-id="34603-107">PowerShell 7.2 (prerelease)</span></span>
- <span data-ttu-id="34603-108">PowerShell 7.1 (текущая версия)</span><span class="sxs-lookup"><span data-stu-id="34603-108">PowerShell 7.1 (current)</span></span>
- <span data-ttu-id="34603-109">PowerShell 7.0 (LTS)</span><span class="sxs-lookup"><span data-stu-id="34603-109">PowerShell 7.0 (LTS)</span></span>
- <span data-ttu-id="34603-110">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="34603-110">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="34603-111">Поиск статей и выбор версии</span><span class="sxs-lookup"><span data-stu-id="34603-111">Finding articles and selecting a version</span></span>

<span data-ttu-id="34603-112">Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии.</span><span class="sxs-lookup"><span data-stu-id="34603-112">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="34603-113">Просто введите слово, которое есть в заголовке статьи.</span><span class="sxs-lookup"><span data-stu-id="34603-113">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="34603-114">На странице отображается список соответствующих статей.</span><span class="sxs-lookup"><span data-stu-id="34603-114">The page displays a list of matching articles.</span></span> <span data-ttu-id="34603-115">Можно также выбрать вариант поиска по всему сайту из этого списка.</span><span class="sxs-lookup"><span data-stu-id="34603-115">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="34603-116">По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34603-116">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="34603-117">Некоторые командлеты работают по-разному в различных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34603-117">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="34603-118">Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34603-118">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="34603-119">Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34603-119">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Использование средства выбора версий](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="34603-121">Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="34603-121">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="34603-122">В следующем примере показаны выходные данные для Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="34603-122">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="34603-123">Если вы не знакомы с PowerShell и вам нужна помощь в понимании синтаксиса команды, см. раздел [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span><span class="sxs-lookup"><span data-stu-id="34603-123">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="34603-124">Поиск статей для предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="34603-124">Finding articles for previous versions</span></span>

<span data-ttu-id="34603-125">Документация по предыдущим версиям PowerShell сохранена в архиве на сайте [предыдущих версий](https://aka.ms/PSLegacyDocs).</span><span class="sxs-lookup"><span data-stu-id="34603-125">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="34603-126">Этот сайт содержит документацию по следующим темам:</span><span class="sxs-lookup"><span data-stu-id="34603-126">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="34603-127">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="34603-127">PowerShell 3.0</span></span>
- <span data-ttu-id="34603-128">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="34603-128">PowerShell 4.0</span></span>
- <span data-ttu-id="34603-129">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="34603-129">PowerShell 5.0</span></span>
- <span data-ttu-id="34603-130">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="34603-130">PowerShell 6</span></span>
- <span data-ttu-id="34603-131">Рабочие процессы PowerShell</span><span class="sxs-lookup"><span data-stu-id="34603-131">PowerShell Workflows</span></span>
- <span data-ttu-id="34603-132">PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="34603-132">PowerShell Web Access</span></span>
