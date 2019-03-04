---
title: Учебник StopProc | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a142aeb6-9c11-44a0-b34f-1f9470fa347b
caps.latest.revision: 5
ms.openlocfilehash: 6e1c8a4709988adfa59bda14eb3af52b0a79f1df
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856360"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="048af-102">Руководство по StopProc</span><span class="sxs-lookup"><span data-stu-id="048af-102">StopProc Tutorial</span></span>

<span data-ttu-id="048af-103">В этом разделе содержится руководство по созданию командлет Stop-Proc, который очень похожа на [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) командлет, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="048af-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="048af-104">Этот учебник содержит фрагменты кода, которые иллюстрируют, как реализованы командлеты и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="048af-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>
<span data-ttu-id="048af-105">В этом разделе содержится руководство по созданию командлет Stop-Proc, который очень похожа на [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) командлет, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="048af-105">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="048af-106">Этот учебник содержит фрагменты кода, которые иллюстрируют, как реализованы командлеты и объяснение кода.</span><span class="sxs-lookup"><span data-stu-id="048af-106">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="048af-107">Разделы в данном руководстве</span><span class="sxs-lookup"><span data-stu-id="048af-107">Topics in this Tutorial</span></span>

<span data-ttu-id="048af-108">Подразделы в этом руководстве предназначены для прочтения последовательно, каждый раздел, основываясь на тех, которые обсуждались в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="048af-108">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="048af-109">[Создание командлета, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md) в этом разделе описывается, как создать командлет, поддерживающий изменения системы, такие как остановка процесса, выполняющегося на компьютере.</span><span class="sxs-lookup"><span data-stu-id="048af-109">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="048af-110">[Добавление пользовательских сообщений Your командлету](./adding-user-messages-to-your-cmdlet.md) в этом разделе описывается добавление возможность записи пользовательских сообщений, сообщений отладки, предупреждающие сообщения и сведения о ходе выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="048af-110">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="048af-111">[Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) в этом разделе описывается, как создать командлет, который поддерживает псевдонимы параметра "," Справка "и" Развертывание знаков подстановки.</span><span class="sxs-lookup"><span data-stu-id="048af-111">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="048af-112">[Добавление параметра в командлетах](./adding-parameter-sets-to-a-cmdlet.md) в этом разделе описывается добавление наборов параметров в командлет.</span><span class="sxs-lookup"><span data-stu-id="048af-112">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="048af-113">Наборы параметров позволяют командлет для работы, на какие параметры задаются пользователем по-разному основе.</span><span class="sxs-lookup"><span data-stu-id="048af-113">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="048af-114">См. также</span><span class="sxs-lookup"><span data-stu-id="048af-114">See Also</span></span>

[<span data-ttu-id="048af-115">Создание командлета, который изменяет системы</span><span class="sxs-lookup"><span data-stu-id="048af-115">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="048af-116">Добавление пользовательских сообщений в командлет</span><span class="sxs-lookup"><span data-stu-id="048af-116">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="048af-117">Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета</span><span class="sxs-lookup"><span data-stu-id="048af-117">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="048af-118">Добавление параметра наборов в командлетах</span><span class="sxs-lookup"><span data-stu-id="048af-118">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="048af-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="048af-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
