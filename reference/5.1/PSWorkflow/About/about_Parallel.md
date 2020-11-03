---
description: Описывает ключевое слово Parallel, которое запускает действия в рабочем процессе в параллельном режиме.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231610"
---
# <a name="about-parallel"></a><span data-ttu-id="ba3f9-104">О программе Parallel</span><span class="sxs-lookup"><span data-stu-id="ba3f9-104">About Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="ba3f9-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ba3f9-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ba3f9-106">Описывает ключевое слово Parallel, которое запускает действия в рабочем процессе в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-106">Describes the Parallel keyword, which runs the activities in a workflow in parallel.</span></span>

## <a name="long-description"></a><span data-ttu-id="ba3f9-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ba3f9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ba3f9-108">Ключевое слово Parallel параллельно запускает действия рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-108">The Parallel keyword runs workflow activities in parallel.</span></span> <span data-ttu-id="ba3f9-109">Это ключевое слово допустимо только в рабочем процессе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-109">This keyword is valid only in  Windows PowerShell  Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="ba3f9-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ba3f9-110">SYNTAX</span></span>

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a><span data-ttu-id="ba3f9-111">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ba3f9-111">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="ba3f9-112">Команды в блоке сценария Parallel могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-112">The commands in a Parallel script block can run concurrently.</span></span> <span data-ttu-id="ba3f9-113">Порядок их запуска не определен.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-113">The order in which they run is not determined.</span></span>

<span data-ttu-id="ba3f9-114">Например, в следующем рабочем процессе имеется блок сценария Parallel, в котором выполняются действия, обращающиеся к процессам и службам на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-114">For example, the following workflow includes a Parallel script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="ba3f9-115">Так как команды Get-Process и Get-Service независимы друг от друга, они могут выполняться параллельно и в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-115">Because the Get-Process and Get-Service commands are independent of each other, they can run concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

<span data-ttu-id="ba3f9-116">Параллельно выполняемые команды очень эффективны и сокращают время, необходимое для значительного выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-116">Running commands in parallel is very efficient and reduces the time it takes to complete a workflow significantly.</span></span>

<span data-ttu-id="ba3f9-117">Для выполнения выбранных команд в блоке параллельного сценария в последовательном порядке используйте ключевое слово Sequence.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-117">To run selected commands in a Parallel script block in sequential order, use the Sequence keyword.</span></span> <span data-ttu-id="ba3f9-118">Дополнительные сведения см. в разделе about_Sequence.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-118">For more information, see about_Sequence.</span></span>

<span data-ttu-id="ba3f9-119">Чтобы выполнить параллельный блок скрипта для элементов в коллекции, используйте ключевые слова ForEach или ForEach-Parallel.</span><span class="sxs-lookup"><span data-stu-id="ba3f9-119">To run a Parallel script block on items in a collection, use the ForEach or ForEach -Parallel keywords.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba3f9-120">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ba3f9-120">SEE ALSO</span></span>

<span data-ttu-id="ba3f9-121">["Запись рабочего процесса скрипта"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="ba3f9-121">["Writing a Script Workflow"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span></span>

[<span data-ttu-id="ba3f9-122">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="ba3f9-122">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="ba3f9-123">about_ForEach параллельно</span><span class="sxs-lookup"><span data-stu-id="ba3f9-123">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="ba3f9-124">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="ba3f9-124">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="ba3f9-125">about_Sequence</span><span class="sxs-lookup"><span data-stu-id="ba3f9-125">about_Sequence</span></span>](about_Sequence.md)

[<span data-ttu-id="ba3f9-126">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ba3f9-126">about_Workflows</span></span>](about_workflows.md)
