---
title: Примеры Windows PowerShell API | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082589"
---
# <a name="windows-powershell-api-samples"></a>Примеры API Windows PowerShell

Этот раздел содержит примеры кода, демонстрирующие способы создания пространства выполнения, ограничить функциональные возможности и асинхронно выполнять команды, используя пул пространств выполнения для предоставления пространства выполнения. Microsoft Visual Studio можно использовать для создания консольного приложения и затем скопируйте код из подразделы этого раздела в ведущее приложение.

## <a name="in-this-section"></a>Содержание

[Пример PowerShell01](./windows-powershell01-sample.md) в этом примере показано, как использовать [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта, чтобы ограничить функциональные возможности пространства выполнения. Выходные данные в этом примере показано, как ограничить языковой режим пространства выполнения, как пометить командлет как частные, как добавить и командлеты remove и поставщиков, как добавить прокси-команды и многое другое.

[Пример PowerShell02](./windows-powershell02-sample.md) в этом примере показано, как выполнять команды асинхронно с помощью пространства выполнения пула пространства выполнения. В примере список команд и затем выполняет эти команды, пока подсистемы Windows PowerShell открывается пространство из пула, при необходимости.