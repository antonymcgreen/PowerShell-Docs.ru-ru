---
title: Пример PowerShell02 для Windows | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779392"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="5c069-102">Пример Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="5c069-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="5c069-103">В этом образце показано, как асинхронно выполнять команды с помощью пространств выполнения пула.</span><span class="sxs-lookup"><span data-stu-id="5c069-103">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="5c069-104">В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.</span><span class="sxs-lookup"><span data-stu-id="5c069-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c069-105">Требования</span><span class="sxs-lookup"><span data-stu-id="5c069-105">Requirements</span></span>

- <span data-ttu-id="5c069-106">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="5c069-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5c069-107">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="5c069-107">Demonstrates</span></span>

<span data-ttu-id="5c069-108">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="5c069-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="5c069-109">Создание объекта Рунспацепул с минимальным и максимальным числом пространств выполнения, которые могут быть открыты одновременно.</span><span class="sxs-lookup"><span data-stu-id="5c069-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="5c069-110">Создание списка команд.</span><span class="sxs-lookup"><span data-stu-id="5c069-110">Creating a list of commands.</span></span>
- <span data-ttu-id="5c069-111">Асинхронное выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="5c069-111">Running the commands asynchronously.</span></span>
- <span data-ttu-id="5c069-112">Вызов метода [System. Management. Automation. пространства выполнения. рунспацепул. жетаваилаблерунспацес \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) , чтобы узнать, сколько пространств выполнения свободно.</span><span class="sxs-lookup"><span data-stu-id="5c069-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="5c069-113">Запись выходных данных команды с помощью метода [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="5c069-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="5c069-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5c069-114">Example</span></span>

<span data-ttu-id="5c069-115">В этом образце показано, как открыть пространства выполнения пула и как асинхронно выполнять команды в этих пространствах.</span><span class="sxs-lookup"><span data-stu-id="5c069-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="5c069-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5c069-116">See Also</span></span>

[<span data-ttu-id="5c069-117">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c069-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
