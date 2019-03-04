---
title: Учебник GetProc | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4663905f-560a-4e39-9b03-6db2c315c322
caps.latest.revision: 6
ms.openlocfilehash: bbd07a0d0abd30742b7e02482adedae3af43aca4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862460"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="1570e-102">Руководство по GetProc</span><span class="sxs-lookup"><span data-stu-id="1570e-102">GetProc Tutorial</span></span>

<span data-ttu-id="1570e-103">Этот раздел содержит руководство для создания командлет Get-Proc, — очень похоже на [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1570e-103">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="1570e-104">Этот учебник содержит фрагменты кода, которые иллюстрируют, как реализованы командлеты и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="1570e-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="1570e-105">Разделы в данном руководстве</span><span class="sxs-lookup"><span data-stu-id="1570e-105">Topics in this Tutorial</span></span>

<span data-ttu-id="1570e-106">Подразделы в этом руководстве предназначены для прочтения последовательно, каждый раздел, основываясь на тех, которые обсуждались в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="1570e-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="1570e-107">[Создание командлета без параметров](./creating-a-cmdlet-without-parameters.md) в этом разделе описывается, как создать командлет, который извлекает данные из локального компьютера без использования параметров, а затем записывает данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1570e-107">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="1570e-108">[Добавление параметров командной строки процесса Input](./adding-parameters-that-process-command-line-input.md) в этом разделе описывается добавление параметра в командлет Get-Proc, так что этот командлет может обработать входные данные, на основе явных объектов передается командлету.</span><span class="sxs-lookup"><span data-stu-id="1570e-108">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="1570e-109">Реализацию, описанную здесь извлекает процессов на основе их имени и затем записывает данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1570e-109">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="1570e-110">[Добавление параметров, входные данные конвейера процесс](./adding-parameters-that-process-pipeline-input.md) в этом разделе описывается добавление параметра в командлет Get-Proc, так что этот командлет может обработать объекты, передаваемый через конвейер.</span><span class="sxs-lookup"><span data-stu-id="1570e-110">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="1570e-111">Командлет реализации описано здесь извлекает процессов на основе объектов, переданных в командлет и затем записывает данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1570e-111">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="1570e-112">[Добавление отчетов об ошибках устранимые Your командлету](./adding-non-terminating-error-reporting-to-your-cmdlet.md) в этом разделе описывается добавление устранимые ошибки reporting в командлет.</span><span class="sxs-lookup"><span data-stu-id="1570e-112">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="1570e-113">Реализация обнаруживает устранимые ошибки, которые возникают при обработке входных данных и записывает в поток ошибок записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1570e-113">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="1570e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1570e-114">See Also</span></span>

[<span data-ttu-id="1570e-115">Создание командлета без параметров</span><span class="sxs-lookup"><span data-stu-id="1570e-115">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="1570e-116">Добавление параметров, которые обрабатывают данные в командной строке</span><span class="sxs-lookup"><span data-stu-id="1570e-116">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="1570e-117">Добавление параметров конвейера обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="1570e-117">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="1570e-118">Добавление устранимые ошибки Reporting командлета</span><span class="sxs-lookup"><span data-stu-id="1570e-118">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="1570e-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1570e-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
