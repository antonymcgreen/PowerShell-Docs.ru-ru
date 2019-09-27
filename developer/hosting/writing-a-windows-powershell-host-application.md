---
title: Создание ведущего приложения Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: b44708b3bbcb974a6178323dff2302b7da121af6
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323500"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="1899a-102">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1899a-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="1899a-103">Windows PowerShell можно разместить в приложении.</span><span class="sxs-lookup"><span data-stu-id="1899a-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="1899a-104">Ведущее приложение может определить пространство выполнения, в котором выполняются команды, открывать сеансы на локальном или удаленном компьютере и вызывать команды синхронно или асинхронно в зависимости от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="1899a-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="1899a-105">В следующих разделах объясняется, как создать приложение, в котором размещается Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1899a-105">The following topics explain how to create an application that hosts Windows PowerShell.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1899a-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1899a-106">In This Section</span></span>

<span data-ttu-id="1899a-107">[Краткое руководство по узлу Windows PowerShell](./windows-powershell-host-quickstart.md) Содержит инструкции и примеры кода, позволяющие приступить к созданию ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="1899a-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="1899a-108">[Создание пространств](./creating-runspaces.md) выполнения Набор разделов, в которых объясняется, как создавать пространства выполнения для команды Windows PowerShell в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="1899a-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="1899a-109">[Добавление и вызов команд](./adding-and-invoking-commands.md) Объясняется, как создать и запустить конвейер команд в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="1899a-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="1899a-110">[Создание удаленных пространств](./creating-remote-runspaces.md) выполнения Объясняет, как подключить пространство выполнения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="1899a-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="1899a-111">[Создание настраиваемого пользовательского интерфейса](./creating-a-custom-user-interface.md) Содержит общие сведения о пользовательских интерфейсах и ссылки на примеры.</span><span class="sxs-lookup"><span data-stu-id="1899a-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="1899a-112">[Примеры ведущих приложений](./host-application-samples.md) Этот раздел содержит примеры полных ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="1899a-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="1899a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1899a-113">See Also</span></span>

[<span data-ttu-id="1899a-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1899a-114">Windows PowerShell</span></span>](https://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)
