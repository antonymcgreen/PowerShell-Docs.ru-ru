---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода командлетов
description: Примеры кода командлетов
ms.openlocfilehash: 91dd2019300504697ad9a7a0c155a04600d09c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652920"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="536ce-103">Примеры кода командлетов</span><span class="sxs-lookup"><span data-stu-id="536ce-103">Examples of Cmdlet Code</span></span>

<span data-ttu-id="536ce-104">В этом разделе приводятся примеры кода командлетов, которые можно использовать для написания собственных командлетов.</span><span class="sxs-lookup"><span data-stu-id="536ce-104">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="536ce-105">Пошаговые инструкции по написанию командлетов см. в [руководствах по написанию командлетов](./tutorials-for-writing-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="536ce-105">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="536ce-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="536ce-106">In This Section</span></span>

<span data-ttu-id="536ce-107">[Написание простого командлета](./how-to-write-a-simple-cmdlet.md) В этом примере показана базовая структура кода командлета.</span><span class="sxs-lookup"><span data-stu-id="536ce-107">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="536ce-108">[Как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md) В этом примере показано, как объявить различные типы параметров.</span><span class="sxs-lookup"><span data-stu-id="536ce-108">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="536ce-109">[Объявление наборов параметров](./how-to-declare-parameter-sets.md) В этом примере показано, как объявить наборы параметров, которые могут изменить действие, выполняемое командлетом.</span><span class="sxs-lookup"><span data-stu-id="536ce-109">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="536ce-110">[Проверка входных параметров](./how-to-validate-parameter-input.md) В этих примерах показано, как проверить входные данные параметра.</span><span class="sxs-lookup"><span data-stu-id="536ce-110">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="536ce-111">[Объявление динамических параметров](./how-to-declare-dynamic-parameters.md) В этом примере показано, как объявить параметр, добавляемый во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="536ce-111">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="536ce-112">[Как вызывать скрипты в командлете](./how-to-invoke-scripts-within-a-cmdlet.md) В этом примере показано, как вызвать скрипт, передаваемый в командлет.</span><span class="sxs-lookup"><span data-stu-id="536ce-112">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="536ce-113">[Переопределение методов обработки входных данных](./how-to-override-input-processing-methods.md) В этих примерах показана базовая структура, используемая для переопределения методов BeginProcessing, ProcessRecord и EndProcessing.</span><span class="sxs-lookup"><span data-stu-id="536ce-113">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="536ce-114">[Поддержка вызовов ShouldProcess](./how-to-request-confirmations.md) В этом примере показано, как вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из командлета.</span><span class="sxs-lookup"><span data-stu-id="536ce-114">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="536ce-115">[Поддержка транзакций](./how-to-support-transactions.md) В этом примере показано, как указать, что командлет поддерживает транзакции и как реализовать действие, выполняемое при использовании командлета в транзакции.</span><span class="sxs-lookup"><span data-stu-id="536ce-115">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="536ce-116">[Поддержка заданий](./how-to-support-jobs.md) В этом примере показано, как поддерживать задания при записи командлетов.</span><span class="sxs-lookup"><span data-stu-id="536ce-116">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="536ce-117">[Вызов командлета из командлета](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) В этом примере показано, как вызвать командлет из другого командлета, который позволяет добавлять функциональные возможности вызванного командлета в разрабатываемый командлет.</span><span class="sxs-lookup"><span data-stu-id="536ce-117">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="536ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="536ce-118">See Also</span></span>

[<span data-ttu-id="536ce-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="536ce-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
