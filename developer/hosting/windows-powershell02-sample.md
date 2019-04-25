---
title: Пример PowerShell02 Windows | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 89ad17257ebac56105a93672317a149515e80d32
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082521"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="9b521-102">Пример Windows PowerShell02</span><span class="sxs-lookup"><span data-stu-id="9b521-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="9b521-103">В этом примере показано, как выполнять команды асинхронно с помощью пространства выполнения пула пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="9b521-103">This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="9b521-104">В примере список команд и затем выполняет эти команды, пока подсистемы Windows PowerShell открывается пространство из пула, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="9b521-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b521-105">Требования</span><span class="sxs-lookup"><span data-stu-id="9b521-105">Requirements</span></span>

- <span data-ttu-id="9b521-106">В этом примере требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b521-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9b521-107">Демонстрирует</span><span class="sxs-lookup"><span data-stu-id="9b521-107">Demonstrates</span></span>

<span data-ttu-id="9b521-108">Этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="9b521-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="9b521-109">Создание объекта RunspacePool с минимальным и максимальным количеством пространства выполнения может быть открыто одновременно.</span><span class="sxs-lookup"><span data-stu-id="9b521-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>

- <span data-ttu-id="9b521-110">Создание списка команд.</span><span class="sxs-lookup"><span data-stu-id="9b521-110">Creating a list of commands.</span></span>

- <span data-ttu-id="9b521-111">Асинхронное выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="9b521-111">Running the commands asynchronously.</span></span>

- <span data-ttu-id="9b521-112">Вызов [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) метод, чтобы увидеть, сколько пространства выполнения предоставляются бесплатно.</span><span class="sxs-lookup"><span data-stu-id="9b521-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>

- <span data-ttu-id="9b521-113">Запись выходных данных команды с [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.</span><span class="sxs-lookup"><span data-stu-id="9b521-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="9b521-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9b521-114">Example</span></span>

<span data-ttu-id="9b521-115">В этом примере показано, как открыть пространства выполнения пула пространство выполнения и асинхронное выполнение команд в пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="9b521-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

[!code-csharp[PowerShell02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a><span data-ttu-id="9b521-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9b521-116">See Also</span></span>

[<span data-ttu-id="9b521-117">Создание приложения Windows PowerShell узла</span><span class="sxs-lookup"><span data-stu-id="9b521-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)