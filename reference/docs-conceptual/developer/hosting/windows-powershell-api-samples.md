---
title: Примеры API Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360843"
---
# <a name="windows-powershell-api-samples"></a>Примеры API Windows PowerShell

В этом разделе содержится пример кода, в котором показано, как создавать пространства выполнения, ограничивающие функциональные возможности, и как асинхронно выполнять команды с помощью пула пространства для предоставления пространств. С помощью Microsoft Visual Studio можно создать консольное приложение, а затем скопировать код из разделов этого раздела в ведущее приложение.

## <a name="in-this-section"></a>Содержание

[Пример PowerShell01](./windows-powershell01-sample.md) В этом примере показано, как использовать объект [System. Management. Automation.](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) пространствей Initialsessionstate для ограничения функциональности пространства выполнения. В выходных данных этого примера показано, как ограничить языковой режим пространства выполнения, как пометить командлет как частный, добавить и удалить командлеты и поставщики, добавить команду прокси-сервера и многое другое.

[Пример PowerShell02](./windows-powershell02-sample.md) В этом примере показано, как асинхронно выполнять команды с помощью пространств выполнения пула. В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.