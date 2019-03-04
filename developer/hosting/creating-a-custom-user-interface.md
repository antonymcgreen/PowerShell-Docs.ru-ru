---
title: Создание собственного пользовательского интерфейса | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7286443-eed4-43d5-b809-50cdcdcba088
caps.latest.revision: 4
ms.openlocfilehash: 23518c625fe1138e1bd2bcc895274cb21d7daf8a
ms.sourcegitcommit: c581c4c8036edf55147e7bce4b00c860da6c5a8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2019
ms.locfileid: "56863720"
---
# <a name="creating-a-custom-user-interface"></a>Создание собственного пользовательского интерфейса

Windows PowerShell предоставляет абстрактные классы и интерфейсы, которые позволяют создавать пользовательские интерактивного пользовательского интерфейса, на котором размещена подсистема Windows PowerShell. Чтобы создать настраиваемый пользовательский Интерфейс, необходимо реализовать [System.Management.Automation.Host.PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) класса. При желании вы также можете реализовать [System.Management.Automation.Host.Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)и [System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) классов и [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) и [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) интерфейсов.
