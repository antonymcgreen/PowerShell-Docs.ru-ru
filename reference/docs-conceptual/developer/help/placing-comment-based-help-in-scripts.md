---
title: Размещение справки на основе комментариев в скриптах | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361183"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="0388e-102">Размещение справки на основе комментариев в сценариях</span><span class="sxs-lookup"><span data-stu-id="0388e-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="0388e-103">В этом разделе объясняется, куда разместить справку на основе комментариев для скрипта, чтобы командлет `Get-Help` сопоставленный с комментариями раздел справки с скриптами, а не с функциями, которые могут быть в скрипте.</span><span class="sxs-lookup"><span data-stu-id="0388e-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="0388e-104">Размещение справки на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="0388e-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="0388e-105">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="0388e-105">At the beginning of the script file.</span></span> <span data-ttu-id="0388e-106">Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.</span><span class="sxs-lookup"><span data-stu-id="0388e-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="0388e-107">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="0388e-107">At the end of the script file.</span></span>

  <span data-ttu-id="0388e-108">Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="0388e-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="0388e-109">В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.</span><span class="sxs-lookup"><span data-stu-id="0388e-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="0388e-110">Примеры размещения справки в сценарии</span><span class="sxs-lookup"><span data-stu-id="0388e-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="0388e-111">В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="0388e-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="0388e-112">Справка в начале сценария</span><span class="sxs-lookup"><span data-stu-id="0388e-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="0388e-113">В следующем примере показано, как на основе комментариев в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="0388e-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="0388e-114">Справка в конце скрипта</span><span class="sxs-lookup"><span data-stu-id="0388e-114">Help at the End of a Script</span></span>

 <span data-ttu-id="0388e-115">В следующем примере показано, как на основе комментариев в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="0388e-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```