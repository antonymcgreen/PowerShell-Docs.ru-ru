---
title: Создание пространства выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082946"
---
# <a name="creating-runspaces"></a><span data-ttu-id="f3d63-102">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="f3d63-102">Creating Runspaces</span></span>

<span data-ttu-id="f3d63-103">Пространства выполнения является операционной среды для команды, которые вызываются ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="f3d63-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="f3d63-104">Эта среда включает в себя команды и данных, которые в настоящее время отсутствуют и каких-либо ограничений языка, которые в настоящее время применяются.</span><span class="sxs-lookup"><span data-stu-id="f3d63-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="f3d63-105">Размещение приложений можно использовать пространству выполнения по умолчанию, предоставляемый Windows PowerShell, которая включает в себя все доступные основные команды, или создания пользовательских пространства выполнения, которая включает только подмножество доступных команд.</span><span class="sxs-lookup"><span data-stu-id="f3d63-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="f3d63-106">Можно создать настраиваемые пространство выполнения, создав [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта и его назначение вашего пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3d63-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="f3d63-107">Пространства выполнения задачи</span><span class="sxs-lookup"><span data-stu-id="f3d63-107">Runspace tasks</span></span>

1. [<span data-ttu-id="f3d63-108">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="f3d63-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="f3d63-109">Создание ограниченное пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="f3d63-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="f3d63-110">Создание несколькими средами</span><span class="sxs-lookup"><span data-stu-id="f3d63-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="f3d63-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d63-111">See Also</span></span>
