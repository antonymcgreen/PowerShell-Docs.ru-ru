---
title: Руководство по proc | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: cc99cb4de8e3b8fcab8eac28b21162764aecd8a1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784271"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="5ecb4-102">Руководство по GetProc</span><span class="sxs-lookup"><span data-stu-id="5ecb4-102">GetProc Tutorial</span></span>

<span data-ttu-id="5ecb4-103">В этом разделе содержится руководство по созданию командлета Get-proc, который очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-103">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="5ecb4-104">В этом учебнике содержатся фрагменты кода, иллюстрирующие реализацию командлетов и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="5ecb4-105">Подразделы этого руководства</span><span class="sxs-lookup"><span data-stu-id="5ecb4-105">Topics in this Tutorial</span></span>

<span data-ttu-id="5ecb4-106">Подразделы этого учебника предназначены для последовательного чтения, и каждый раздел строится на предмет того, что обсуждалось в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="5ecb4-107">[Создание командлета без параметров](./creating-a-cmdlet-without-parameters.md) В этом разделе описывается создание командлета, который получает сведения с локального компьютера без использования параметров, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-107">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="5ecb4-108">[Добавление параметров, обрабатывающих входные данные командной строки](./adding-parameters-that-process-command-line-input.md) В этом разделе описывается, как добавить параметр в командлет Get-proc, чтобы командлет мог обрабатывать входные данные на основе явных объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-108">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="5ecb4-109">Описанная здесь реализация извлекает процессы на основе их имени, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-109">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="5ecb4-110">[Добавление параметров, обрабатывающих входные данные конвейера](./adding-parameters-that-process-pipeline-input.md) В этом разделе описывается, как добавить параметр в командлет Get-proc, чтобы командлет мог обрабатывать объекты, переданные в него через конвейер.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-110">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="5ecb4-111">Описанный здесь командлет реализации извлекает процессы на основе объектов, переданных в командлет, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-111">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="5ecb4-112">[Добавление в командлет незавершающего сообщения об ошибках](./adding-non-terminating-error-reporting-to-your-cmdlet.md) В этом разделе описывается добавление непрерывающих отчетов об ошибках в командлет.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-112">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="5ecb4-113">Описанная здесь реализация определяет неустранимые ошибки, возникающие при обработке входных данных, и записывает запись об ошибке в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="5ecb4-113">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ecb4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5ecb4-114">See Also</span></span>

[<span data-ttu-id="5ecb4-115">Создание командлета без параметров</span><span class="sxs-lookup"><span data-stu-id="5ecb4-115">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="5ecb4-116">Добавление параметров, обрабатывающих входные данные командной строки</span><span class="sxs-lookup"><span data-stu-id="5ecb4-116">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="5ecb4-117">Добавление параметров для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="5ecb4-117">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="5ecb4-118">Добавление в командлет незавершающего сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="5ecb4-118">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="5ecb4-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ecb4-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
