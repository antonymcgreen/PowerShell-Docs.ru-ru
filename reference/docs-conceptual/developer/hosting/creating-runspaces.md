---
title: Создание пространств выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367583"
---
# <a name="creating-runspaces"></a><span data-ttu-id="e35a0-102">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="e35a0-102">Creating Runspaces</span></span>

<span data-ttu-id="e35a0-103">Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="e35a0-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="e35a0-104">Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="e35a0-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="e35a0-105">Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд.</span><span class="sxs-lookup"><span data-stu-id="e35a0-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="e35a0-106">Чтобы создать настраиваемое пространство выполнения, создайте объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="e35a0-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="e35a0-107">Задачи пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="e35a0-107">Runspace tasks</span></span>

1. [<span data-ttu-id="e35a0-108">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="e35a0-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="e35a0-109">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="e35a0-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="e35a0-110">Создание нескольких пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="e35a0-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="e35a0-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="e35a0-111">See Also</span></span>
