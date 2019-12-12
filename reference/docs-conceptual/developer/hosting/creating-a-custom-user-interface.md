---
title: Создание настраиваемого пользовательского интерфейса | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7286443-eed4-43d5-b809-50cdcdcba088
caps.latest.revision: 4
ms.openlocfilehash: 23518c625fe1138e1bd2bcc895274cb21d7daf8a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367633"
---
# <a name="creating-a-custom-user-interface"></a>Создание собственного пользовательского интерфейса

Windows PowerShell предоставляет абстрактные классы и интерфейсы, позволяющие создать настраиваемый интерактивный пользовательский интерфейс, в котором размещается подсистема Windows PowerShell. Чтобы создать пользовательский интерфейс, необходимо реализовать класс [System. Management. Automation. host. PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) . При необходимости можно также реализовать классы [System. Management. Automation. host. Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)и [System. Management. Automation. host. пшостусеринтерфаце](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) , а также интерфейсы [System. Management. Automation. host. ихостсуппортсинтерактивесессион](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) и [System. Management. Automation. host. ихостуисуппортсмултиплечоицеселектион](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) .
