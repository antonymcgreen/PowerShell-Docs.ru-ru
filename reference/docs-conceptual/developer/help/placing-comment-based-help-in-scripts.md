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
ms.openlocfilehash: 1bebfbd822963830363012060067c656d7709543
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565532"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="96c16-102">Размещение справки на основе комментариев в сценариях</span><span class="sxs-lookup"><span data-stu-id="96c16-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="96c16-103">В этом разделе объясняется, куда поместить справку на основе комментариев для сценария, чтобы `Get-Help` командлет привязывает раздел справки на основе комментариев с скриптами, а не с функциями, которые могут быть в скрипте.</span><span class="sxs-lookup"><span data-stu-id="96c16-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="96c16-104">Размещение справки на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="96c16-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="96c16-105">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="96c16-105">At the beginning of the script file.</span></span> <span data-ttu-id="96c16-106">Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.</span><span class="sxs-lookup"><span data-stu-id="96c16-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="96c16-107">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="96c16-107">At the end of the script file.</span></span>

  <span data-ttu-id="96c16-108">Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="96c16-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="96c16-109">В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.</span><span class="sxs-lookup"><span data-stu-id="96c16-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="96c16-110">Примеры размещения справки в сценарии</span><span class="sxs-lookup"><span data-stu-id="96c16-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="96c16-111">В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="96c16-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="96c16-112">Справка в начале сценария</span><span class="sxs-lookup"><span data-stu-id="96c16-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="96c16-113">В следующем примере показано, как на основе комментариев в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="96c16-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="96c16-114">Справка в конце скрипта</span><span class="sxs-lookup"><span data-stu-id="96c16-114">Help at the End of a Script</span></span>

 <span data-ttu-id="96c16-115">В следующем примере показано, как на основе комментариев в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="96c16-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```
