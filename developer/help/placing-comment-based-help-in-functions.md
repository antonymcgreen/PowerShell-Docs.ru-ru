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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857950"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="7e873-102">Размещение справки на основе комментариев в функциях</span><span class="sxs-lookup"><span data-stu-id="7e873-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="7e873-103">В этом разделе объясняется, где разместить основанной на комментариях справку для функции, чтобы `Get-Help` командлет связывает раздел справки на основе комментариев с соответствующей функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="7e873-104">Размещение основанной на комментариях справку для функции</span><span class="sxs-lookup"><span data-stu-id="7e873-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="7e873-105">В начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="7e873-106">В конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-106">At the end of the function body.</span></span>

- <span data-ttu-id="7e873-107">Прежде чем `Function` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e873-107">Before the `Function` keyword.</span></span> <span data-ttu-id="7e873-108">Если функция является в скрипте или модуль сценария, не может быть более чем одну пустую строку между последней строки справки на основе комментариев и `Function` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e873-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="7e873-109">В противном случае `Get-Help` связывает справки с помощью сценария, но не функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="7e873-110">Примеры размещения Help в функции</span><span class="sxs-lookup"><span data-stu-id="7e873-110">Examples of Help Placement in a Function</span></span>

 <span data-ttu-id="7e873-111">Ниже приведены примеры каждой из трех размещения для основанной на комментариях справку для функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="7e873-112">Помочь в начале тела функции</span><span class="sxs-lookup"><span data-stu-id="7e873-112">Help at the Beginning of a Function Body</span></span>

 <span data-ttu-id="7e873-113">В следующем примере показано основе комментариев в начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="7e873-114">Помочь в конце тела функции</span><span class="sxs-lookup"><span data-stu-id="7e873-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="7e873-115">В следующем примере показано, основанной на комментариях в конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="7e873-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="7e873-116">Справка перед ключевым словом функции</span><span class="sxs-lookup"><span data-stu-id="7e873-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="7e873-117">В следующих примерах показано основе комментариев в строке до ключевого слова function.</span><span class="sxs-lookup"><span data-stu-id="7e873-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```