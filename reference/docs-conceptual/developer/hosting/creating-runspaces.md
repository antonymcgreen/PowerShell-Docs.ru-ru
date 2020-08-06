---
title: Создание пространств выполнения | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0c27e2bf54e16a3bdc93c4b91629893bb1cc1e3e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779579"
---
# <a name="creating-runspaces"></a><span data-ttu-id="bbd5d-102">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="bbd5d-102">Creating Runspaces</span></span>

<span data-ttu-id="bbd5d-103">Пространство выполнения — это операционная среда для команд, которые вызываются ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="bbd5d-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="bbd5d-104">Эта среда включает в себя команды и данные, которые в настоящее время присутствуют, и все ограничения языка, применяемые в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="bbd5d-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="bbd5d-105">Ведущие приложения могут использовать пространство выполнения по умолчанию, предоставляемое Windows PowerShell, включающее все доступные основные команды, или создать пользовательское пространство выполнения, включающее только подмножество доступных команд.</span><span class="sxs-lookup"><span data-stu-id="bbd5d-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="bbd5d-106">Чтобы создать настраиваемое пространство выполнения, создайте объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) и назначьте его пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbd5d-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="bbd5d-107">Задачи пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="bbd5d-107">Runspace tasks</span></span>

1. [<span data-ttu-id="bbd5d-108">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="bbd5d-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="bbd5d-109">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="bbd5d-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="bbd5d-110">Создание нескольких пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="bbd5d-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="bbd5d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bbd5d-111">See Also</span></span>
