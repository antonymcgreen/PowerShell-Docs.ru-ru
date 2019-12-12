---
title: Примеры API Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360843"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="2ab03-102">Примеры API Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ab03-102">Windows PowerShell API Samples</span></span>

<span data-ttu-id="2ab03-103">В этом разделе содержится пример кода, в котором показано, как создавать пространства выполнения, ограничивающие функциональные возможности, и как асинхронно выполнять команды с помощью пула пространства для предоставления пространств.</span><span class="sxs-lookup"><span data-stu-id="2ab03-103">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="2ab03-104">С помощью Microsoft Visual Studio можно создать консольное приложение, а затем скопировать код из разделов этого раздела в ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="2ab03-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2ab03-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="2ab03-105">In This Section</span></span>

<span data-ttu-id="2ab03-106">[Пример PowerShell01](./windows-powershell01-sample.md) В этом примере показано, как использовать объект [System. Management. Automation.](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) пространствей Initialsessionstate для ограничения функциональности пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ab03-106">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="2ab03-107">В выходных данных этого примера показано, как ограничить языковой режим пространства выполнения, как пометить командлет как частный, добавить и удалить командлеты и поставщики, добавить команду прокси-сервера и многое другое.</span><span class="sxs-lookup"><span data-stu-id="2ab03-107">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="2ab03-108">[Пример PowerShell02](./windows-powershell02-sample.md) В этом примере показано, как асинхронно выполнять команды с помощью пространств выполнения пула.</span><span class="sxs-lookup"><span data-stu-id="2ab03-108">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="2ab03-109">В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.</span><span class="sxs-lookup"><span data-stu-id="2ab03-109">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>