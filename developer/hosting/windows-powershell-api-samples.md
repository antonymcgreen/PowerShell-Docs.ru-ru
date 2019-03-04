---
title: Примеры Windows PowerShell API | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860780"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="0b2dd-102">Примеры API Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b2dd-102">Windows PowerShell API Samples</span></span>

<span data-ttu-id="0b2dd-103">Этот раздел содержит примеры кода, демонстрирующие способы создания пространства выполнения, ограничить функциональные возможности и асинхронно выполнять команды, используя пул пространств выполнения для предоставления пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-103">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="0b2dd-104">Microsoft Visual Studio можно использовать для создания консольного приложения и затем скопируйте код из подразделы этого раздела в ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0b2dd-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="0b2dd-105">In This Section</span></span>

<span data-ttu-id="0b2dd-106">[Пример PowerShell01](./windows-powershell01-sample.md) в этом примере показано, как использовать [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта, чтобы ограничить функциональные возможности пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-106">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="0b2dd-107">Выходные данные в этом примере показано, как ограничить языковой режим пространства выполнения, как пометить командлет как частные, как добавить и командлеты remove и поставщиков, как добавить прокси-команды и многое другое.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-107">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="0b2dd-108">[Пример PowerShell02](./windows-powershell02-sample.md) в этом примере показано, как выполнять команды асинхронно с помощью пространства выполнения пула пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-108">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="0b2dd-109">В примере список команд и затем выполняет эти команды, пока подсистемы Windows PowerShell открывается пространство из пула, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0b2dd-109">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>