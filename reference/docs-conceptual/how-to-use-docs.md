---
ms.date: 07/29/2020
keywords: powershell,командлет
title: Использование документации по PowerShell
description: В этой статье описывается, как использовать функции данного сайта, включая фильтрацию при поиске и выбор версий.
ms.openlocfilehash: 32f0c613e10329cc4830386b744e766eeeab0187
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501122"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="6c01b-104">Использование документации по PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c01b-104">How to use the PowerShell documentation</span></span>

<span data-ttu-id="6c01b-105">Добро пожаловать в интерактивную документацию по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c01b-105">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="6c01b-106">Этот сайт содержит справочник по командлетам для следующих версий PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6c01b-106">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="6c01b-107">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="6c01b-107">PowerShell 7</span></span>
- <span data-ttu-id="6c01b-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="6c01b-108">PowerShell 6</span></span>
- <span data-ttu-id="6c01b-109">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="6c01b-109">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="6c01b-110">Поиск статей и выбор версии</span><span class="sxs-lookup"><span data-stu-id="6c01b-110">Finding articles and selecting a version</span></span>

<span data-ttu-id="6c01b-111">Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии.</span><span class="sxs-lookup"><span data-stu-id="6c01b-111">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="6c01b-112">Просто введите слово, которое есть в заголовке статьи.</span><span class="sxs-lookup"><span data-stu-id="6c01b-112">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="6c01b-113">На странице отображается список соответствующих статей.</span><span class="sxs-lookup"><span data-stu-id="6c01b-113">The page displays a list of matching articles.</span></span> <span data-ttu-id="6c01b-114">Можно также выбрать вариант поиска по всему сайту из этого списка.</span><span class="sxs-lookup"><span data-stu-id="6c01b-114">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="6c01b-115">По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c01b-115">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="6c01b-116">Некоторые командлеты работают по-разному в различных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c01b-116">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="6c01b-117">Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c01b-117">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="6c01b-118">Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c01b-118">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Использование средства выбора версий](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="6c01b-120">Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="6c01b-120">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="6c01b-121">В следующем примере показаны выходные данные для Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="6c01b-121">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="6c01b-122">Если вы не знакомы с PowerShell и вам нужна помощь в понимании синтаксиса команды, см. раздел [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span><span class="sxs-lookup"><span data-stu-id="6c01b-122">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="6c01b-123">Поиск статей для предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="6c01b-123">Finding articles for previous versions</span></span>

<span data-ttu-id="6c01b-124">Документация по предыдущим версиям PowerShell сохранена в архиве на сайте [предыдущих версий](https://aka.ms/PSLegacyDocs).</span><span class="sxs-lookup"><span data-stu-id="6c01b-124">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="6c01b-125">Этот сайт содержит документацию по следующим темам:</span><span class="sxs-lookup"><span data-stu-id="6c01b-125">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="6c01b-126">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="6c01b-126">PowerShell 3.0</span></span>
- <span data-ttu-id="6c01b-127">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="6c01b-127">PowerShell 4.0</span></span>
- <span data-ttu-id="6c01b-128">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c01b-128">PowerShell 5.0</span></span>
- <span data-ttu-id="6c01b-129">Рабочие процессы PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c01b-129">PowerShell Workflows</span></span>
- <span data-ttu-id="6c01b-130">PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="6c01b-130">PowerShell Web Access</span></span>
