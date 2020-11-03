---
description: Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: ffa499fd618d0d31dec470b0c35c902eba26eb0a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232286"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="6a7bc-104">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="6a7bc-104">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="6a7bc-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6a7bc-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6a7bc-106">Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-106">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="6a7bc-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6a7bc-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6a7bc-108">Упрощенный синтаксис, представленный в Windows PowerShell 3,0, позволяет создавать некоторые команды фильтров без использования блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-108">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="6a7bc-109">Упрощенный синтаксис более похож на естественный язык и в основном полезен для коллекций объектов, которые передаются в команды, и `Where-Object` `ForEach-Object` их соответствующие псевдонимы `where` и `foreach` .</span><span class="sxs-lookup"><span data-stu-id="6a7bc-109">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="6a7bc-110">Можно использовать метод для членов коллекции (чаще всего это массив), не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-110">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="6a7bc-111">Рассмотрим следующие два вызова:</span><span class="sxs-lookup"><span data-stu-id="6a7bc-111">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="6a7bc-112">Стандартный синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a7bc-112">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="6a7bc-113">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a7bc-113">Simplified syntax</span></span>

<span data-ttu-id="6a7bc-114">В упрощенном синтаксисе операторы сравнения, работающие с членами объектов в коллекции, обрабатываются как параметры.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-114">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="6a7bc-115">Можно вызвать метод для объектов в коллекции, не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-115">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="6a7bc-116">Сравните следующие два вызова с теми, которые относятся к предыдущему примеру:</span><span class="sxs-lookup"><span data-stu-id="6a7bc-116">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="6a7bc-117">Хотя оба синтаксиса работают, упрощенный синтаксис возвращает результаты, не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-117">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="6a7bc-118">Имя метода `GetKeyAlgorithm` рассматривается как параметр `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="6a7bc-118">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="6a7bc-119">Вторая команда возвращает те же результаты, но без ошибок, поскольку упрощенный синтаксис не пытается вернуть результаты для элементов, для которых указанный аргумент не был применен.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-119">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="6a7bc-120">В этом примере `Process` свойство `Description` передается в качестве параметра имени члена в `ForEach-Object` команду.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-120">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="6a7bc-121">Результаты представляют собой описания активных процессов.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-121">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="6a7bc-122">В этом примере `DirectoryInfo` метод `GetFiles` передается в качестве параметра имени члена `ForEach-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-122">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="6a7bc-123">Метод вызывается с параметром шаблона поиска `.*` .</span><span class="sxs-lookup"><span data-stu-id="6a7bc-123">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="6a7bc-124">Результаты представляют собой `FileInfo` записи для всех скрытых файлов в стиле UNIX в домашних каталогах пользователей.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-124">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="6a7bc-125">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="6a7bc-125">SEE ALSO</span></span>

- [<span data-ttu-id="6a7bc-126">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="6a7bc-126">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="6a7bc-127">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="6a7bc-127">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="6a7bc-128">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6a7bc-128">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="6a7bc-129">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="6a7bc-129">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
