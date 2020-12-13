---
ms.date: 09/13/2016
ms.topic: reference
title: Руководство по StopProc
description: Руководство по StopProc
ms.openlocfilehash: 95229ee3c4905d295bd6991fe8ccf8c9840c3cdd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646423"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="e8895-103">Руководство по StopProc</span><span class="sxs-lookup"><span data-stu-id="e8895-103">StopProc Tutorial</span></span>

<span data-ttu-id="e8895-104">В этом разделе приводится руководство по созданию командлета Stop-Proc, который очень похож [на командлет,](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8895-104">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="e8895-105">В этом учебнике содержатся фрагменты кода, иллюстрирующие реализацию командлетов и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="e8895-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="e8895-106">Подразделы этого руководства</span><span class="sxs-lookup"><span data-stu-id="e8895-106">Topics in this Tutorial</span></span>

<span data-ttu-id="e8895-107">Подразделы этого учебника предназначены для последовательного чтения, и каждый раздел строится на предмет того, что обсуждалось в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="e8895-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="e8895-108">[Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md) В этом разделе описывается создание командлета, который поддерживает системные изменения, такие как остановка процесса, выполняющегося на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8895-108">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="e8895-109">[Добавление сообщений пользователя в командлет](./adding-user-messages-to-your-cmdlet.md) В этом разделе описывается, как добавить возможность записи пользовательских сообщений, сообщений об отладке, предупреждающих сообщений и сведений о ходе выполнения в командлет.</span><span class="sxs-lookup"><span data-stu-id="e8895-109">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="e8895-110">[Добавление псевдонимов, расширение подстановочных знаков и Справка по параметрам командлета](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) В этом разделе описывается создание командлета, поддерживающего псевдонимы параметров, справку и расширение с использованием подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="e8895-110">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="e8895-111">[Добавление наборов параметров в командлеты](./adding-parameter-sets-to-a-cmdlet.md) В этом разделе описывается добавление наборов параметров в командлет.</span><span class="sxs-lookup"><span data-stu-id="e8895-111">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="e8895-112">Наборы параметров позволяют командлету взаимодействовать по-разному в зависимости от того, какие параметры задаются пользователем.</span><span class="sxs-lookup"><span data-stu-id="e8895-112">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8895-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8895-113">See Also</span></span>

[<span data-ttu-id="e8895-114">Создание командлета, который изменяет систему</span><span class="sxs-lookup"><span data-stu-id="e8895-114">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="e8895-115">Добавление пользовательских сообщений в командлет</span><span class="sxs-lookup"><span data-stu-id="e8895-115">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="e8895-116">Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета</span><span class="sxs-lookup"><span data-stu-id="e8895-116">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="e8895-117">Добавление наборов параметров в командлеты</span><span class="sxs-lookup"><span data-stu-id="e8895-117">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="e8895-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8895-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
