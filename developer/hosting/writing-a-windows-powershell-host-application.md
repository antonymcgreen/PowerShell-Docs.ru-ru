---
title: Создание приложения Windows PowerShell узла | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: 2039e181becd1b39fc3d6cf0cdbcf0c20e9fc206
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863180"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="6d576-102">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d576-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="6d576-103">Windows PowerShell можно размещать в приложении.</span><span class="sxs-lookup"><span data-stu-id="6d576-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="6d576-104">Ведущее приложение можно определить пространство выполнения, где находятся команды запуска, открыть сеансы на локальном или удаленном компьютере и вызова команд, которые либо синхронно или асинхронно в зависимости от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="6d576-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="6d576-105">Следующих разделах объясняется, как создать приложение, на котором размещена</span><span class="sxs-lookup"><span data-stu-id="6d576-105">The following topics explain how to create an application that hosts</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6d576-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="6d576-106">In This Section</span></span>

<span data-ttu-id="6d576-107">[Примеры использования узла PowerShell Windows](./windows-powershell-host-quickstart.md) инструкции и примеры кода, чтобы приступить к работе над созданием ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="6d576-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="6d576-108">[Создание пространства выполнения](./creating-runspaces.md) набор разделы, в которых описаны способы создания пространства выполнения, чтобы выполнить команду Windows PowerShell в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="6d576-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="6d576-109">[Добавление и вызова команд](./adding-and-invoking-commands.md) объясняется, как создавать и запускать конвейер команд в своем хост-приложении...</span><span class="sxs-lookup"><span data-stu-id="6d576-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="6d576-110">[Создание удаленного пространства выполнения](./creating-remote-runspaces.md) Expains способ подключения к удаленному компьютеру в пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="6d576-110">[Creating remote runspaces](./creating-remote-runspaces.md) Expains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="6d576-111">[Создание собственного пользовательского интерфейса](./creating-a-custom-user-interface.md) представляет пользовательские интерфейсы и ссылки на примеры.</span><span class="sxs-lookup"><span data-stu-id="6d576-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="6d576-112">[Примеры приложений узлов](./host-application-samples.md) в этом разделе содержатся образцы приложений завершения узла.</span><span class="sxs-lookup"><span data-stu-id="6d576-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d576-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6d576-113">See Also</span></span>

[<span data-ttu-id="6d576-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d576-114">Windows PowerShell</span></span>](http://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)