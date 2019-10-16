---
title: Учебники по написанию командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0b548aa-febf-45dd-bf71-2077730b9b73
caps.latest.revision: 6
ms.openlocfilehash: 767b392bd1603e83d80bad5b3fd9cb42ff142ce6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369323"
---
# <a name="tutorials-for-writing-cmdlets"></a><span data-ttu-id="3e761-102">Руководства по написанию командлетов</span><span class="sxs-lookup"><span data-stu-id="3e761-102">Tutorials for Writing Cmdlets</span></span>

<span data-ttu-id="3e761-103">В этом разделе содержатся учебники по написанию командлетов.</span><span class="sxs-lookup"><span data-stu-id="3e761-103">This section contains tutorials for writing cmdlets.</span></span> <span data-ttu-id="3e761-104">В эти учебники входит код, необходимый для написания командлетов, а также объясняется, зачем нужен код.</span><span class="sxs-lookup"><span data-stu-id="3e761-104">These tutorials include the code needed to write the cmdlets, plus an explanation of why the code is needed.</span></span> <span data-ttu-id="3e761-105">Эти разделы будут очень полезны для тех, кто только начинает писать командлеты.</span><span class="sxs-lookup"><span data-stu-id="3e761-105">These topics will be very helpful for those who are just starting to write cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e761-106">Сведения о том, кому нужны примеры кода с меньшим описанием, см. в разделе [примеры командлетов](./cmdlet-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3e761-106">For those who want code examples with less description, see [Cmdlet Samples](./cmdlet-samples.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3e761-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="3e761-107">In This Section</span></span>

<span data-ttu-id="3e761-108">[Учебник по INPROC](./getproc-tutorial.md) . в этом учебнике описывается определение класса командлета и Добавление базовых функций, таких как добавление параметров и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3e761-108">[GetProc Tutorial](./getproc-tutorial.md) - This tutorial describes how to define a cmdlet class and add basic functionality such as adding parameters and reporting errors.</span></span> <span data-ttu-id="3e761-109">Командлет, описанный в этом руководстве, очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e761-109">The cmdlet described in this tutorial is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="3e761-110">[Учебник по стоппрок](./stopproc-tutorial.md) . в этом учебнике описывается, как определить командлет и добавить такие функции, как запросы пользователя, поддержка подстановочных знаков и использование наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="3e761-110">[StopProc Tutorial](./stopproc-tutorial.md) - This tutorial describes how to define a cmdlet and add functionality such as user prompts, wildcard support, and the use of parameter sets.</span></span> <span data-ttu-id="3e761-111">Описанный здесь командлет выполняет ту же задачу, что и командлет [-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e761-111">The cmdlet described here performs the same task as the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="3e761-112">[Учебник по селектстр](./selectstr-tutorial.md) . в этом учебнике описывается, как определить командлет, обращающийся к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="3e761-112">[SelectStr Tutorial](./selectstr-tutorial.md) - This tutorial describes how to define a cmdlet that accesses a data store.</span></span> <span data-ttu-id="3e761-113">Описанный здесь командлет выполняет ту же задачу, что и командлет [Select-String](/powershell/module/microsoft.powershell.utility/select-string) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e761-113">The cmdlet described here performs the same task as the [Select-String](/powershell/module/microsoft.powershell.utility/select-string) cmdlet provided by Windows PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e761-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e761-114">See Also</span></span>

[<span data-ttu-id="3e761-115">Учебник по процедурам INPROC</span><span class="sxs-lookup"><span data-stu-id="3e761-115">GetProc Tutorial</span></span>](./getproc-tutorial.md)

[<span data-ttu-id="3e761-116">Руководство по Стоппрок</span><span class="sxs-lookup"><span data-stu-id="3e761-116">StopProc Tutorial</span></span>](./stopproc-tutorial.md)

[<span data-ttu-id="3e761-117">Руководство по Селектстр</span><span class="sxs-lookup"><span data-stu-id="3e761-117">SelectStr Tutorial</span></span>](./selectstr-tutorial.md)

[<span data-ttu-id="3e761-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e761-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
