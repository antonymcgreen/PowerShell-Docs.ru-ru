---
ms.date: 09/12/2016
ms.topic: reference
title: Размещение справки на основе комментариев в сценариях
description: Размещение справки на основе комментариев в сценариях
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645435"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="1d813-103">Размещение справки на основе комментариев в сценариях</span><span class="sxs-lookup"><span data-stu-id="1d813-103">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="1d813-104">В этом разделе объясняется, куда поместить справку на основе комментариев для сценария, чтобы `Get-Help` командлет привязывает раздел справки на основе комментариев с скриптами, а не с функциями, которые могут быть в скрипте.</span><span class="sxs-lookup"><span data-stu-id="1d813-104">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="1d813-105">Размещение Comment-Based справки по сценарию</span><span class="sxs-lookup"><span data-stu-id="1d813-105">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="1d813-106">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d813-106">At the beginning of the script file.</span></span>

  <span data-ttu-id="1d813-107">Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.</span><span class="sxs-lookup"><span data-stu-id="1d813-107">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="1d813-108">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d813-108">At the end of the script file.</span></span>

  <span data-ttu-id="1d813-109">Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="1d813-109">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="1d813-110">В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.</span><span class="sxs-lookup"><span data-stu-id="1d813-110">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="1d813-111">Примеры размещения справки в сценарии</span><span class="sxs-lookup"><span data-stu-id="1d813-111">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="1d813-112">В следующих примерах показаны параметры размещения для скрипта справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="1d813-112">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="1d813-113">Справка в начале сценария</span><span class="sxs-lookup"><span data-stu-id="1d813-113">Help at the Beginning of a Script</span></span>

<span data-ttu-id="1d813-114">В следующем примере показано, как на основе комментариев в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d813-114">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="1d813-115">Справка в конце скрипта</span><span class="sxs-lookup"><span data-stu-id="1d813-115">Help at the End of a Script</span></span>

 <span data-ttu-id="1d813-116">В следующем примере показано, как на основе комментариев в конце скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d813-116">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
