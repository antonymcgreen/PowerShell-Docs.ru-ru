---
ms.date: 09/13/2016
ms.topic: reference
title: Создание пространств выполнения
description: Создание пространств выполнения
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649340"
---
# <a name="creating-runspaces"></a><span data-ttu-id="72f45-103">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="72f45-103">Creating Runspaces</span></span>

<span data-ttu-id="72f45-104">Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="72f45-104">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="72f45-105">Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="72f45-105">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="72f45-106">Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд.</span><span class="sxs-lookup"><span data-stu-id="72f45-106">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="72f45-107">Чтобы создать настраиваемое пространство выполнения, создайте объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="72f45-107">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="72f45-108">Задачи пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="72f45-108">Runspace tasks</span></span>

1. [<span data-ttu-id="72f45-109">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="72f45-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="72f45-110">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="72f45-110">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="72f45-111">Создание нескольких пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="72f45-111">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="72f45-112">См. также</span><span class="sxs-lookup"><span data-stu-id="72f45-112">See Also</span></span>
