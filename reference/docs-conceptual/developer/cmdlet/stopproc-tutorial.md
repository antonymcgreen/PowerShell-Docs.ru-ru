---
title: Учебник по Стоппрок | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e298c729b7ac59141638052d19b95ab77aa25cd6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786481"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="a6ec1-102">Руководство по StopProc</span><span class="sxs-lookup"><span data-stu-id="a6ec1-102">StopProc Tutorial</span></span>

<span data-ttu-id="a6ec1-103">В этом разделе приводится руководство по созданию командлета "останавливает- [обработать](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) ", который очень похож на командлет, предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="a6ec1-104">В этом учебнике содержатся фрагменты кода, иллюстрирующие реализацию командлетов и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="a6ec1-105">Подразделы этого руководства</span><span class="sxs-lookup"><span data-stu-id="a6ec1-105">Topics in this Tutorial</span></span>

<span data-ttu-id="a6ec1-106">Подразделы этого учебника предназначены для последовательного чтения, и каждый раздел строится на предмет того, что обсуждалось в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="a6ec1-107">[Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md) В этом разделе описывается создание командлета, который поддерживает системные изменения, такие как остановка процесса, выполняющегося на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="a6ec1-108">[Добавление сообщений пользователя в командлет](./adding-user-messages-to-your-cmdlet.md) В этом разделе описывается, как добавить возможность записи пользовательских сообщений, сообщений об отладке, предупреждающих сообщений и сведений о ходе выполнения в командлет.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="a6ec1-109">[Добавление псевдонимов, расширение подстановочных знаков и Справка по параметрам командлета](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) В этом разделе описывается создание командлета, поддерживающего псевдонимы параметров, справку и расширение с использованием подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="a6ec1-110">[Добавление наборов параметров в командлеты](./adding-parameter-sets-to-a-cmdlet.md) В этом разделе описывается добавление наборов параметров в командлет.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="a6ec1-111">Наборы параметров позволяют командлету взаимодействовать по-разному в зависимости от того, какие параметры задаются пользователем.</span><span class="sxs-lookup"><span data-stu-id="a6ec1-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6ec1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ec1-112">See Also</span></span>

[<span data-ttu-id="a6ec1-113">Создание командлета, который изменяет систему</span><span class="sxs-lookup"><span data-stu-id="a6ec1-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="a6ec1-114">Добавление пользовательских сообщений в командлет</span><span class="sxs-lookup"><span data-stu-id="a6ec1-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="a6ec1-115">Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета</span><span class="sxs-lookup"><span data-stu-id="a6ec1-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="a6ec1-116">Добавление наборов параметров в командлеты</span><span class="sxs-lookup"><span data-stu-id="a6ec1-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="a6ec1-117">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6ec1-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
