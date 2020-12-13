---
ms.date: 09/13/2016
ms.topic: reference
title: Пример Windows PowerShell02
description: Пример Windows PowerShell02
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657356"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="bedcc-103">Пример Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="bedcc-103">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="bedcc-104">В этом образце показано, как асинхронно выполнять команды с помощью пространств выполнения пула.</span><span class="sxs-lookup"><span data-stu-id="bedcc-104">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="bedcc-105">В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.</span><span class="sxs-lookup"><span data-stu-id="bedcc-105">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="bedcc-106">Требования</span><span class="sxs-lookup"><span data-stu-id="bedcc-106">Requirements</span></span>

- <span data-ttu-id="bedcc-107">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="bedcc-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="bedcc-108">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="bedcc-108">Demonstrates</span></span>

<span data-ttu-id="bedcc-109">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="bedcc-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="bedcc-110">Создание объекта Рунспацепул с минимальным и максимальным числом пространств выполнения, которые могут быть открыты одновременно.</span><span class="sxs-lookup"><span data-stu-id="bedcc-110">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="bedcc-111">Создание списка команд.</span><span class="sxs-lookup"><span data-stu-id="bedcc-111">Creating a list of commands.</span></span>
- <span data-ttu-id="bedcc-112">Асинхронное выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="bedcc-112">Running the commands asynchronously.</span></span>
- <span data-ttu-id="bedcc-113">Вызов метода [System. Management. Automation. пространства выполнения. рунспацепул. жетаваилаблерунспацес \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) , чтобы узнать, сколько пространств выполнения свободно.</span><span class="sxs-lookup"><span data-stu-id="bedcc-113">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="bedcc-114">Запись выходных данных команды с помощью метода [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="bedcc-114">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="bedcc-115">Пример</span><span class="sxs-lookup"><span data-stu-id="bedcc-115">Example</span></span>

<span data-ttu-id="bedcc-116">В этом образце показано, как открыть пространства выполнения пула и как асинхронно выполнять команды в этих пространствах.</span><span class="sxs-lookup"><span data-stu-id="bedcc-116">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="bedcc-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bedcc-117">See Also</span></span>

[<span data-ttu-id="bedcc-118">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bedcc-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
