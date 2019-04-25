---
title: Размещение справки на основе комментариев в сценарии | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083235"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="40525-102">Размещение справки на основе комментариев в сценариях</span><span class="sxs-lookup"><span data-stu-id="40525-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="40525-103">В этом разделе объясняется, где разместить справки на основе комментариев по сценарию, чтобы `Get-Help` командлет связывает раздел справки, основанной на комментариях, с помощью сценариев, а не все функции, которые могут быть в скрипте.</span><span class="sxs-lookup"><span data-stu-id="40525-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="40525-104">Размещение основанной на комментариях справку для скрипта</span><span class="sxs-lookup"><span data-stu-id="40525-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="40525-105">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="40525-105">At the beginning of the script file.</span></span> <span data-ttu-id="40525-106">Скрипт справки может стоять в скрипт только комментарии и пустые строки.</span><span class="sxs-lookup"><span data-stu-id="40525-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="40525-107">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="40525-107">At the end of the script file.</span></span>

  <span data-ttu-id="40525-108">При объявлении функции, первый элемент в тексте сценария (после Справка) должен существовать по крайней мере две пустые строки между концом скрипт справки и в объявлении функции.</span><span class="sxs-lookup"><span data-stu-id="40525-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="40525-109">В противном случае справки интерпретируется как справку для функции, не справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="40525-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="40525-110">Примеры размещения справки в скрипте</span><span class="sxs-lookup"><span data-stu-id="40525-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="40525-111">Ниже приведены примеры каждого из вариантов размещения, основанной на комментариях справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="40525-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="40525-112">Помочь в начале сценария</span><span class="sxs-lookup"><span data-stu-id="40525-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="40525-113">В следующем примере показано основе комментариев в начале сценария.</span><span class="sxs-lookup"><span data-stu-id="40525-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="40525-114">Помочь в конце сценария</span><span class="sxs-lookup"><span data-stu-id="40525-114">Help at the End of a Script</span></span>

 <span data-ttu-id="40525-115">В следующем примере показано, основанной на комментариях в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="40525-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```