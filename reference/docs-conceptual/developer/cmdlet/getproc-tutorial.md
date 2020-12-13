---
ms.date: 09/13/2016
ms.topic: reference
title: Руководство по GetProc
description: Руководство по GetProc
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652785"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="7f3d2-103">Руководство по GetProc</span><span class="sxs-lookup"><span data-stu-id="7f3d2-103">GetProc Tutorial</span></span>

<span data-ttu-id="7f3d2-104">В этом разделе приводится руководство по созданию командлета Get-Proc, который очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-104">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="7f3d2-105">В этом учебнике содержатся фрагменты кода, иллюстрирующие реализацию командлетов и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="7f3d2-106">Подразделы этого руководства</span><span class="sxs-lookup"><span data-stu-id="7f3d2-106">Topics in this Tutorial</span></span>

<span data-ttu-id="7f3d2-107">Подразделы этого учебника предназначены для последовательного чтения, и каждый раздел строится на предмет того, что обсуждалось в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="7f3d2-108">[Создание командлета без параметров](./creating-a-cmdlet-without-parameters.md) В этом разделе описывается создание командлета, который получает сведения с локального компьютера без использования параметров, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-108">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="7f3d2-109">[Добавление параметров, обрабатывающих Command-Line входе](./adding-parameters-that-process-command-line-input.md) В этом разделе описывается, как добавить параметр в командлет Get-Proc, чтобы командлет мог обрабатывать входные данные на основе явных объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-109">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="7f3d2-110">Описанная здесь реализация извлекает процессы на основе их имени, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-110">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="7f3d2-111">[Добавление параметров, обрабатывающих входные данные конвейера](./adding-parameters-that-process-pipeline-input.md) В этом разделе описывается, как добавить параметр в командлет Get-Proc, чтобы командлет мог обрабатывать объекты, переданные в него через конвейер.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-111">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="7f3d2-112">Описанный здесь командлет реализации извлекает процессы на основе объектов, переданных в командлет, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-112">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="7f3d2-113">[Добавление в командлет незавершающего сообщения об ошибках](./adding-non-terminating-error-reporting-to-your-cmdlet.md) В этом разделе описывается добавление непрерывающих отчетов об ошибках в командлет.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-113">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="7f3d2-114">Описанная здесь реализация определяет неустранимые ошибки, возникающие при обработке входных данных, и записывает запись об ошибке в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="7f3d2-114">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f3d2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f3d2-115">See Also</span></span>

[<span data-ttu-id="7f3d2-116">Создание командлета без параметров</span><span class="sxs-lookup"><span data-stu-id="7f3d2-116">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="7f3d2-117">Добавление параметров, обрабатывающих Command-Line входе</span><span class="sxs-lookup"><span data-stu-id="7f3d2-117">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="7f3d2-118">Добавление параметров для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="7f3d2-118">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="7f3d2-119">Добавление в командлет незавершающего сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="7f3d2-119">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="7f3d2-120">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f3d2-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
