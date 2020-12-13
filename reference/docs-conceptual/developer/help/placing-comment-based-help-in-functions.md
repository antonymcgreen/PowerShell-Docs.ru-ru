---
ms.date: 09/12/2016
ms.topic: reference
title: Размещение справки на основе комментариев в функциях
description: Размещение справки на основе комментариев в функциях
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658208"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="83843-103">Размещение справки на основе комментариев в функциях</span><span class="sxs-lookup"><span data-stu-id="83843-103">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="83843-104">В этом разделе объясняется, куда поместить справку на основе комментариев для функции, чтобы командлет привязывает `Get-Help` раздел справки на основе комментариев с правильной функцией.</span><span class="sxs-lookup"><span data-stu-id="83843-104">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="83843-105">Размещение Comment-Based справки по функции</span><span class="sxs-lookup"><span data-stu-id="83843-105">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="83843-106">В начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="83843-106">At the beginning of the function body.</span></span>

- <span data-ttu-id="83843-107">В конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="83843-107">At the end of the function body.</span></span>

- <span data-ttu-id="83843-108">Перед `Function` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="83843-108">Before the `Function` keyword.</span></span> <span data-ttu-id="83843-109">Если функция находится в сценарии или модуле скрипта, между последней строкой справки на основе комментариев и ключевым словом не может быть больше одной пустой строки `Function` .</span><span class="sxs-lookup"><span data-stu-id="83843-109">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="83843-110">В противном случае `Get-Help` связывает справку со сценарием, а не с функцией.</span><span class="sxs-lookup"><span data-stu-id="83843-110">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="83843-111">Примеры размещения справки в функции</span><span class="sxs-lookup"><span data-stu-id="83843-111">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="83843-112">В следующих примерах показаны все три параметра размещения для справки на основе комментариев для функции.</span><span class="sxs-lookup"><span data-stu-id="83843-112">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="83843-113">Справка в начале тела функции</span><span class="sxs-lookup"><span data-stu-id="83843-113">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="83843-114">В следующем примере показано, как на основе комментариев в начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="83843-114">The following example shows comment-based at the beginning of a function body.</span></span>

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="83843-115">Справка в конце тела функции</span><span class="sxs-lookup"><span data-stu-id="83843-115">Help at the End of a Function Body</span></span>

 <span data-ttu-id="83843-116">В следующем примере показано, как комментарии основаны на комментариях в конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="83843-116">The following example shows comment-based at the end of a function body.</span></span>

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="83843-117">Справка перед ключевым словом функции</span><span class="sxs-lookup"><span data-stu-id="83843-117">Help Before the Function Keyword</span></span>

 <span data-ttu-id="83843-118">В следующих примерах показаны комментарии на основе строки перед ключевым словом function.</span><span class="sxs-lookup"><span data-stu-id="83843-118">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
