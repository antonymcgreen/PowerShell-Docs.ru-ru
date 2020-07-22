---
title: Размещение справки на основе комментариев в функциях
ms.date: 09/12/2016
ms.openlocfilehash: c7a8f8db6c71fa2ef12aaa4df0f78815626ec8d6
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893209"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="96412-102">Размещение справки на основе комментариев в функциях</span><span class="sxs-lookup"><span data-stu-id="96412-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="96412-103">В этом разделе объясняется, куда поместить справку на основе комментариев для функции, чтобы командлет привязывает `Get-Help` раздел справки на основе комментариев с правильной функцией.</span><span class="sxs-lookup"><span data-stu-id="96412-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="96412-104">Размещение справки на основе комментариев для функции</span><span class="sxs-lookup"><span data-stu-id="96412-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="96412-105">В начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="96412-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="96412-106">В конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="96412-106">At the end of the function body.</span></span>

- <span data-ttu-id="96412-107">Перед `Function` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="96412-107">Before the `Function` keyword.</span></span> <span data-ttu-id="96412-108">Если функция находится в сценарии или модуле скрипта, между последней строкой справки на основе комментариев и ключевым словом не может быть больше одной пустой строки `Function` .</span><span class="sxs-lookup"><span data-stu-id="96412-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="96412-109">В противном случае `Get-Help` связывает справку со сценарием, а не с функцией.</span><span class="sxs-lookup"><span data-stu-id="96412-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="96412-110">Примеры размещения справки в функции</span><span class="sxs-lookup"><span data-stu-id="96412-110">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="96412-111">В следующих примерах показаны все три параметра размещения для справки на основе комментариев для функции.</span><span class="sxs-lookup"><span data-stu-id="96412-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="96412-112">Справка в начале тела функции</span><span class="sxs-lookup"><span data-stu-id="96412-112">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="96412-113">В следующем примере показано, как на основе комментариев в начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="96412-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="96412-114">Справка в конце тела функции</span><span class="sxs-lookup"><span data-stu-id="96412-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="96412-115">В следующем примере показано, как комментарии основаны на комментариях в конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="96412-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="96412-116">Справка перед ключевым словом функции</span><span class="sxs-lookup"><span data-stu-id="96412-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="96412-117">В следующих примерах показаны комментарии на основе строки перед ключевым словом function.</span><span class="sxs-lookup"><span data-stu-id="96412-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
