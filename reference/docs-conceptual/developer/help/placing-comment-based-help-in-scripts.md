---
title: Размещение справки на основе комментариев в сценариях
ms.date: 09/12/2016
ms.openlocfilehash: a3ade6c3138826b924939056b9d1ffb233006d44
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893192"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="20033-102">Размещение справки на основе комментариев в сценариях</span><span class="sxs-lookup"><span data-stu-id="20033-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="20033-103">В этом разделе объясняется, куда поместить справку на основе комментариев для сценария, чтобы `Get-Help` командлет привязывает раздел справки на основе комментариев с скриптами, а не с функциями, которые могут быть в скрипте.</span><span class="sxs-lookup"><span data-stu-id="20033-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="20033-104">Размещение справки на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="20033-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="20033-105">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="20033-105">At the beginning of the script file.</span></span>

  <span data-ttu-id="20033-106">Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.</span><span class="sxs-lookup"><span data-stu-id="20033-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="20033-107">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="20033-107">At the end of the script file.</span></span>

  <span data-ttu-id="20033-108">Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="20033-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="20033-109">В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.</span><span class="sxs-lookup"><span data-stu-id="20033-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="20033-110">Примеры размещения справки в сценарии</span><span class="sxs-lookup"><span data-stu-id="20033-110">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="20033-111">В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="20033-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="20033-112">Справка в начале сценария</span><span class="sxs-lookup"><span data-stu-id="20033-112">Help at the Beginning of a Script</span></span>

<span data-ttu-id="20033-113">В следующем примере показано, как на основе комментариев в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="20033-113">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="20033-114">Справка в конце скрипта</span><span class="sxs-lookup"><span data-stu-id="20033-114">Help at the End of a Script</span></span>

 <span data-ttu-id="20033-115">В следующем примере показано, как на основе комментариев в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="20033-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
