---
title: Примеры кода командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fed2f68-ce6d-4a8f-bf21-f94f27a155c2
caps.latest.revision: 9
ms.openlocfilehash: 936728d64f30a08fb9e2fa9ccef103683594aa3e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364503"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="f455d-102">Примеры кода командлетов</span><span class="sxs-lookup"><span data-stu-id="f455d-102">Examples of Cmdlet Code</span></span>

<span data-ttu-id="f455d-103">В этом разделе приводятся примеры кода командлетов, которые можно использовать для написания собственных командлетов.</span><span class="sxs-lookup"><span data-stu-id="f455d-103">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f455d-104">Пошаговые инструкции по написанию командлетов см. в [руководствах по написанию командлетов](./tutorials-for-writing-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="f455d-104">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f455d-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="f455d-105">In This Section</span></span>

<span data-ttu-id="f455d-106">[Написание простого командлета](./how-to-write-a-simple-cmdlet.md) В этом примере показана базовая структура кода командлета.</span><span class="sxs-lookup"><span data-stu-id="f455d-106">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="f455d-107">[Как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md) В этом примере показано, как объявить различные типы параметров.</span><span class="sxs-lookup"><span data-stu-id="f455d-107">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="f455d-108">[Объявление наборов параметров](./how-to-declare-parameter-sets.md) В этом примере показано, как объявить наборы параметров, которые могут изменить действие, выполняемое командлетом.</span><span class="sxs-lookup"><span data-stu-id="f455d-108">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="f455d-109">[Проверка входных параметров](./how-to-validate-parameter-input.md) В этих примерах показано, как проверить входные данные параметра.</span><span class="sxs-lookup"><span data-stu-id="f455d-109">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="f455d-110">[Объявление динамических параметров](./how-to-declare-dynamic-parameters.md) В этом примере показано, как объявить параметр, добавляемый во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f455d-110">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="f455d-111">[Как вызывать скрипты в командлете](./how-to-invoke-scripts-within-a-cmdlet.md) В этом примере показано, как вызвать скрипт, передаваемый в командлет.</span><span class="sxs-lookup"><span data-stu-id="f455d-111">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="f455d-112">[Переопределение методов обработки входных данных](./how-to-override-input-processing-methods.md) В этих примерах показана базовая структура, используемая для переопределения методов BeginProcessing, ProcessRecord и EndProcessing.</span><span class="sxs-lookup"><span data-stu-id="f455d-112">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="f455d-113">[Поддержка вызовов ShouldProcess](./how-to-request-confirmations.md) В этом примере показано, как вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из командлета.</span><span class="sxs-lookup"><span data-stu-id="f455d-113">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="f455d-114">[Поддержка транзакций](./how-to-support-transactions.md) В этом примере показано, как указать, что командлет поддерживает транзакции и как реализовать действие, выполняемое при использовании командлета в транзакции.</span><span class="sxs-lookup"><span data-stu-id="f455d-114">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="f455d-115">[Поддержка заданий](./how-to-support-jobs.md) В этом примере показано, как поддерживать задания при записи командлетов.</span><span class="sxs-lookup"><span data-stu-id="f455d-115">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="f455d-116">[Вызов командлета из командлета](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) В этом примере показано, как вызвать командлет из другого командлета, который позволяет добавлять функциональные возможности вызванного командлета в разрабатываемый командлет.</span><span class="sxs-lookup"><span data-stu-id="f455d-116">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="f455d-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f455d-117">See Also</span></span>

[<span data-ttu-id="f455d-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f455d-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
