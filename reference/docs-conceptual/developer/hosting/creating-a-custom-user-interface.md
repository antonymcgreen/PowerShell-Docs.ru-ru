---
ms.date: 09/13/2016
ms.topic: reference
title: Создание собственного пользовательского интерфейса
description: Создание собственного пользовательского интерфейса
ms.openlocfilehash: 411165f868cd524c0cef0ba9cce3188c60a7dbdf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645406"
---
# <a name="creating-a-custom-user-interface"></a><span data-ttu-id="47d22-103">Создание собственного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="47d22-103">Creating a custom user interface</span></span>

<span data-ttu-id="47d22-104">Windows PowerShell предоставляет абстрактные классы и интерфейсы, позволяющие создать настраиваемый интерактивный пользовательский интерфейс, в котором размещается подсистема Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47d22-104">Windows PowerShell provides abstract classes and interfaces that allow you to create a custom interactive UI that hosts the Windows PowerShell engine.</span></span> <span data-ttu-id="47d22-105">Чтобы создать пользовательский интерфейс, необходимо реализовать класс [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) .</span><span class="sxs-lookup"><span data-stu-id="47d22-105">To create a custom UI, you must implement the [System.Management.Automation.Host.PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) class.</span></span> <span data-ttu-id="47d22-106">При необходимости можно также реализовать классы [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)и [System. Management. Automation. host. пшостусеринтерфаце](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) , а также интерфейсы [System. Management. Automation. host. ихостсуппортсинтерактивесессион](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) и [System. Management. Automation. host. ихостуисуппортсмултиплечоицеселектион](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .</span><span class="sxs-lookup"><span data-stu-id="47d22-106">Optionally, you can also implement the [System.Management.Automation.Host.Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)and [System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) classes, and the [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) and [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) interfaces.</span></span>
