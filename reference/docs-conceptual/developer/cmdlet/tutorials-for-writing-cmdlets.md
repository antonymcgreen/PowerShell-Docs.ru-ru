---
ms.date: 09/13/2016
ms.topic: reference
title: Руководства по написанию командлетов
description: Руководства по написанию командлетов
ms.openlocfilehash: 7ec20b845f8547d346c3777bd52984337d37b83a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646377"
---
# <a name="tutorials-for-writing-cmdlets"></a><span data-ttu-id="e1bca-103">Руководства по написанию командлетов</span><span class="sxs-lookup"><span data-stu-id="e1bca-103">Tutorials for Writing Cmdlets</span></span>

<span data-ttu-id="e1bca-104">В этом разделе содержатся учебники по написанию командлетов.</span><span class="sxs-lookup"><span data-stu-id="e1bca-104">This section contains tutorials for writing cmdlets.</span></span> <span data-ttu-id="e1bca-105">В эти учебники входит код, необходимый для написания командлетов, а также объясняется, зачем нужен код.</span><span class="sxs-lookup"><span data-stu-id="e1bca-105">These tutorials include the code needed to write the cmdlets, plus an explanation of why the code is needed.</span></span> <span data-ttu-id="e1bca-106">Эти разделы будут очень полезны для тех, кто только начинает писать командлеты.</span><span class="sxs-lookup"><span data-stu-id="e1bca-106">These topics will be very helpful for those who are just starting to write cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1bca-107">Сведения о том, кому нужны примеры кода с меньшим описанием, см. в разделе [примеры командлетов](./cmdlet-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1bca-107">For those who want code examples with less description, see [Cmdlet Samples](./cmdlet-samples.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e1bca-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e1bca-108">In This Section</span></span>

<span data-ttu-id="e1bca-109">[Учебник по INPROC](./getproc-tutorial.md) . в этом учебнике описывается определение класса командлета и Добавление базовых функций, таких как добавление параметров и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e1bca-109">[GetProc Tutorial](./getproc-tutorial.md) - This tutorial describes how to define a cmdlet class and add basic functionality such as adding parameters and reporting errors.</span></span> <span data-ttu-id="e1bca-110">Командлет, описанный в этом руководстве, очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bca-110">The cmdlet described in this tutorial is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="e1bca-111">[Учебник по стоппрок](./stopproc-tutorial.md) . в этом учебнике описывается, как определить командлет и добавить такие функции, как запросы пользователя, поддержка подстановочных знаков и использование наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="e1bca-111">[StopProc Tutorial](./stopproc-tutorial.md) - This tutorial describes how to define a cmdlet and add functionality such as user prompts, wildcard support, and the use of parameter sets.</span></span> <span data-ttu-id="e1bca-112">Описанный здесь командлет выполняет ту же задачу, что и командлет [-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bca-112">The cmdlet described here performs the same task as the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="e1bca-113">[Учебник по селектстр](./selectstr-tutorial.md) . в этом учебнике описывается, как определить командлет, обращающийся к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="e1bca-113">[SelectStr Tutorial](./selectstr-tutorial.md) - This tutorial describes how to define a cmdlet that accesses a data store.</span></span> <span data-ttu-id="e1bca-114">Описанный здесь командлет выполняет ту же задачу, что и командлет [Select-String](/powershell/module/microsoft.powershell.utility/select-string) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bca-114">The cmdlet described here performs the same task as the [Select-String](/powershell/module/microsoft.powershell.utility/select-string) cmdlet provided by Windows PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1bca-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1bca-115">See Also</span></span>

[<span data-ttu-id="e1bca-116">Руководство по GetProc</span><span class="sxs-lookup"><span data-stu-id="e1bca-116">GetProc Tutorial</span></span>](./getproc-tutorial.md)

[<span data-ttu-id="e1bca-117">Руководство по StopProc</span><span class="sxs-lookup"><span data-stu-id="e1bca-117">StopProc Tutorial</span></span>](./stopproc-tutorial.md)

[<span data-ttu-id="e1bca-118">Руководство по SelectStr</span><span class="sxs-lookup"><span data-stu-id="e1bca-118">SelectStr Tutorial</span></span>](./selectstr-tutorial.md)

[<span data-ttu-id="e1bca-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1bca-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
