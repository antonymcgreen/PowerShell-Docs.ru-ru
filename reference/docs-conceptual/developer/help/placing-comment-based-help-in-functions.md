---
title: Размещение справки на основе комментариев в функциях | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367783"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="06cab-102">Размещение справки на основе комментариев в функциях</span><span class="sxs-lookup"><span data-stu-id="06cab-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="06cab-103">В этом разделе объясняется, куда поместить справку на основе комментариев для функции, чтобы командлет `Get-Help` свяжет раздел справки на основе комментариев с правильной функцией.</span><span class="sxs-lookup"><span data-stu-id="06cab-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="06cab-104">Размещение справки на основе комментариев для функции</span><span class="sxs-lookup"><span data-stu-id="06cab-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="06cab-105">В начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="06cab-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="06cab-106">В конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="06cab-106">At the end of the function body.</span></span>

- <span data-ttu-id="06cab-107">Перед ключевым словом `Function`.</span><span class="sxs-lookup"><span data-stu-id="06cab-107">Before the `Function` keyword.</span></span> <span data-ttu-id="06cab-108">Если функция находится в сценарии или модуле скрипта, между последней строкой справки на основе комментариев и ключевым словом `Function` не может быть больше одной пустой строки.</span><span class="sxs-lookup"><span data-stu-id="06cab-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="06cab-109">В противном случае `Get-Help` связывает справку со сценарием, а не с функцией.</span><span class="sxs-lookup"><span data-stu-id="06cab-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="06cab-110">Примеры размещения справки в функции</span><span class="sxs-lookup"><span data-stu-id="06cab-110">Examples of Help Placement in a Function</span></span>

 <span data-ttu-id="06cab-111">В следующих примерах показаны все три параметра размещения для справки на основе комментариев для функции.</span><span class="sxs-lookup"><span data-stu-id="06cab-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="06cab-112">Справка в начале тела функции</span><span class="sxs-lookup"><span data-stu-id="06cab-112">Help at the Beginning of a Function Body</span></span>

 <span data-ttu-id="06cab-113">В следующем примере показано, как на основе комментариев в начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="06cab-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="06cab-114">Справка в конце тела функции</span><span class="sxs-lookup"><span data-stu-id="06cab-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="06cab-115">В следующем примере показано, как комментарии основаны на комментариях в конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="06cab-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="06cab-116">Справка перед ключевым словом функции</span><span class="sxs-lookup"><span data-stu-id="06cab-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="06cab-117">В следующих примерах показаны комментарии на основе строки перед ключевым словом function.</span><span class="sxs-lookup"><span data-stu-id="06cab-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```