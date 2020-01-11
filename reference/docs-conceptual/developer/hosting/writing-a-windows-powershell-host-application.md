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
ms.openlocfilehash: fe0393634a1e5bb1a3d4a98ccf245e199beb0f16
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75869917"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="02135-102">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02135-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="02135-103">Windows PowerShell можно разместить в приложении.</span><span class="sxs-lookup"><span data-stu-id="02135-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="02135-104">Ведущее приложение может определить пространство выполнения, в котором выполняются команды, открывать сеансы на локальном или удаленном компьютере и вызывать команды синхронно или асинхронно в зависимости от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="02135-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="02135-105">В следующих разделах объясняется, как создать приложение, в котором размещается Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02135-105">The following topics explain how to create an application that hosts Windows PowerShell.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="02135-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="02135-106">In This Section</span></span>

<span data-ttu-id="02135-107">[Краткое руководство по узлу Windows PowerShell](./windows-powershell-host-quickstart.md) Содержит инструкции и примеры кода, позволяющие приступить к созданию ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="02135-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="02135-108">[Создание пространств](./creating-runspaces.md) выполнения Набор разделов, в которых объясняется, как создавать пространства выполнения для команды Windows PowerShell в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="02135-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="02135-109">[Добавление и вызов команд](./adding-and-invoking-commands.md) Объясняется, как создать и запустить конвейер команд в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="02135-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="02135-110">[Создание удаленных пространств](./creating-remote-runspaces.md) выполнения Объясняет, как подключить пространство выполнения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="02135-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="02135-111">[Создание настраиваемого пользовательского интерфейса](./creating-a-custom-user-interface.md) Содержит общие сведения о пользовательских интерфейсах и ссылки на примеры.</span><span class="sxs-lookup"><span data-stu-id="02135-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="02135-112">[Примеры ведущих приложений](./host-application-samples.md) Этот раздел содержит примеры полных ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="02135-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>
