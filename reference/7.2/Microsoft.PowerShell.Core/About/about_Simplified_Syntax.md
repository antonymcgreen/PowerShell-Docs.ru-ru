---
description: Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: dbd30d566414f784e7d5eca04af716c2bf1642b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604300"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="88966-103">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="88966-103">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="88966-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="88966-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="88966-105">Описывает более простые и естественные способы использования фильтров скриптов для коллекций объектов.</span><span class="sxs-lookup"><span data-stu-id="88966-105">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="88966-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="88966-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="88966-107">Упрощенный синтаксис, представленный в Windows PowerShell 3,0, позволяет создавать некоторые команды фильтров без использования блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="88966-107">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="88966-108">Упрощенный синтаксис более похож на естественный язык и в основном полезен для коллекций объектов, которые передаются в команды, и `Where-Object` `ForEach-Object` их соответствующие псевдонимы `where` и `foreach` .</span><span class="sxs-lookup"><span data-stu-id="88966-108">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="88966-109">Можно использовать метод для членов коллекции (чаще всего это массив), не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="88966-109">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="88966-110">Рассмотрим следующие два вызова:</span><span class="sxs-lookup"><span data-stu-id="88966-110">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="88966-111">Стандартный синтаксис</span><span class="sxs-lookup"><span data-stu-id="88966-111">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="88966-112">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="88966-112">Simplified syntax</span></span>

<span data-ttu-id="88966-113">В упрощенном синтаксисе операторы сравнения, работающие с членами объектов в коллекции, обрабатываются как параметры.</span><span class="sxs-lookup"><span data-stu-id="88966-113">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="88966-114">Можно вызвать метод для объектов в коллекции, не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="88966-114">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="88966-115">Сравните следующие два вызова с теми, которые относятся к предыдущему примеру:</span><span class="sxs-lookup"><span data-stu-id="88966-115">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="88966-116">Хотя оба синтаксиса работают, упрощенный синтаксис возвращает результаты, не ссылаясь на автоматическую переменную `$_` внутри блока script.</span><span class="sxs-lookup"><span data-stu-id="88966-116">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="88966-117">Имя метода `GetKeyAlgorithm` рассматривается как параметр `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="88966-117">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="88966-118">Вторая команда возвращает те же результаты, но без ошибок, поскольку упрощенный синтаксис не пытается вернуть результаты для элементов, для которых указанный аргумент не был применен.</span><span class="sxs-lookup"><span data-stu-id="88966-118">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="88966-119">В этом примере `Process` свойство `Description` передается в качестве параметра имени члена в `ForEach-Object` команду.</span><span class="sxs-lookup"><span data-stu-id="88966-119">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="88966-120">Результаты представляют собой описания активных процессов.</span><span class="sxs-lookup"><span data-stu-id="88966-120">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="88966-121">В этом примере `DirectoryInfo` метод `GetFiles` передается в качестве параметра имени члена `ForEach-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="88966-121">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="88966-122">Метод вызывается с параметром шаблона поиска `.*` .</span><span class="sxs-lookup"><span data-stu-id="88966-122">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="88966-123">Результаты представляют собой `FileInfo` записи для всех скрытых файлов в стиле UNIX в домашних каталогах пользователей.</span><span class="sxs-lookup"><span data-stu-id="88966-123">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="88966-124">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="88966-124">SEE ALSO</span></span>

- [<span data-ttu-id="88966-125">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="88966-125">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="88966-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="88966-126">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="88966-127">Where-Object</span><span class="sxs-lookup"><span data-stu-id="88966-127">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="88966-128">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="88966-128">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

