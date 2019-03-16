---
title: Примеры кода, командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fed2f68-ce6d-4a8f-bf21-f94f27a155c2
caps.latest.revision: 9
ms.openlocfilehash: 936728d64f30a08fb9e2fa9ccef103683594aa3e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056266"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="6645e-102">Примеры кода командлетов</span><span class="sxs-lookup"><span data-stu-id="6645e-102">Examples of Cmdlet Code</span></span>

<span data-ttu-id="6645e-103">В этом разделе содержатся примеры кода командлет, который можно использовать для написания собственных командлетов.</span><span class="sxs-lookup"><span data-stu-id="6645e-103">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6645e-104">Пошаговые инструкции для написания командлетов, см. в разделе [учебники для написания командлетов](./tutorials-for-writing-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="6645e-104">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6645e-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="6645e-105">In This Section</span></span>

<span data-ttu-id="6645e-106">[Как написать простой командлет](./how-to-write-a-simple-cmdlet.md) в этом примере показана базовая структура кода командлета.</span><span class="sxs-lookup"><span data-stu-id="6645e-106">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="6645e-107">[Как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md) в этом примере показан способ объявления различных типов параметров.</span><span class="sxs-lookup"><span data-stu-id="6645e-107">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="6645e-108">[Как объявить наборы параметров](./how-to-declare-parameter-sets.md) в этом примере показано, как объявить наборы параметров, которые могут изменяться командлет выполняет действие.</span><span class="sxs-lookup"><span data-stu-id="6645e-108">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="6645e-109">[Как проверить входной параметр](./how-to-validate-parameter-input.md) этих примерах показано, как для проверки входных параметров.</span><span class="sxs-lookup"><span data-stu-id="6645e-109">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="6645e-110">[Как объявить динамических параметров](./how-to-declare-dynamic-parameters.md) в этом примере показано, как объявить параметр, который добавляется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6645e-110">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="6645e-111">[Как вызывать скрипты в командлет](./how-to-invoke-scripts-within-a-cmdlet.md) в этом примере показано, как вызвать скрипт, который передается в командлет.</span><span class="sxs-lookup"><span data-stu-id="6645e-111">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="6645e-112">[Как переопределить методы обработки ввода](./how-to-override-input-processing-methods.md) в следующих примерах используется для переопределения методов BeginProcessing, ProcessRecord и EndProcessing базовую структуру.</span><span class="sxs-lookup"><span data-stu-id="6645e-112">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="6645e-113">[Как обращений в службу поддержки ShouldProcess](./how-to-request-confirmations.md) в этом примере показано, как [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы должны вызываться из командлета.</span><span class="sxs-lookup"><span data-stu-id="6645e-113">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="6645e-114">[Как для поддержки транзакций](./how-to-support-transactions.md) в этом примере показано, как указать, что командлет поддерживает транзакции и как реализовать действие, выполняемое при использовании с командлетом в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="6645e-114">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="6645e-115">[Как задания поддерживают](./how-to-support-jobs.md) в этом примере показано, как для поддержки задания при написании командлетов.</span><span class="sxs-lookup"><span data-stu-id="6645e-115">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="6645e-116">[Как вызвать командлет из в командлет](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) в этом примере показано, как для вызова командлета из в другой командлет, который позволяет добавлять функциональные возможности вызванного командлета в командлет, вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="6645e-116">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="6645e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6645e-117">See Also</span></span>

[<span data-ttu-id="6645e-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6645e-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
