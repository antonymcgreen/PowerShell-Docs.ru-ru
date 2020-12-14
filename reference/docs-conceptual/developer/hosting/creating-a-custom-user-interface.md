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
# <a name="creating-a-custom-user-interface"></a>Создание собственного пользовательского интерфейса

Windows PowerShell предоставляет абстрактные классы и интерфейсы, позволяющие создать настраиваемый интерактивный пользовательский интерфейс, в котором размещается подсистема Windows PowerShell. Чтобы создать пользовательский интерфейс, необходимо реализовать класс [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) . При необходимости можно также реализовать классы [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)и [System. Management. Automation. host. пшостусеринтерфаце](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) , а также интерфейсы [System. Management. Automation. host. ихостсуппортсинтерактивесессион](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) и [System. Management. Automation. host. ихостуисуппортсмултиплечоицеселектион](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .
