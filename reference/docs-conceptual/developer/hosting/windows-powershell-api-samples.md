---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры API Windows PowerShell
description: Примеры API Windows PowerShell
ms.openlocfilehash: b6336ae7a2abb98cbbaa69bf6c9455f893db2d94
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657550"
---
# <a name="windows-powershell-api-samples"></a>Примеры API Windows PowerShell

В этом разделе содержится пример кода, в котором показано, как создавать пространства выполнения, ограничивающие функциональные возможности, и как асинхронно выполнять команды с помощью пула пространства для предоставления пространств. С помощью Microsoft Visual Studio можно создать консольное приложение, а затем скопировать код из разделов этого раздела в ведущее приложение.

## <a name="in-this-section"></a>в этом разделе

[Пример PowerShell01](./windows-powershell01-sample.md) В этом примере показано, как использовать объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) для ограничения функциональности пространства выполнения. В выходных данных этого примера показано, как ограничить языковой режим пространства выполнения, как пометить командлет как частный, добавить и удалить командлеты и поставщики, добавить команду прокси-сервера и многое другое.

[Пример PowerShell02](./windows-powershell02-sample.md) В этом примере показано, как асинхронно выполнять команды с помощью пространств выполнения пула. В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.
