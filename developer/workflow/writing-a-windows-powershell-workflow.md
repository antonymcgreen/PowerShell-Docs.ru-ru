---
title: Написание рабочего процесса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080328"
---
# <a name="writing-a-windows-powershell-workflow"></a>Запись рабочего процесса Windows PowerShell

Можно создать рабочий процесс XAML путем добавления действий, предоставляемых сборок Windows PowerShell в конструктор рабочих процессов в Visual Studio. Следующие сборки Windows PowerShell предоставляют действия с поддержкой рабочих процессов.

> [!IMPORTANT]
> Рабочий процесс XAML должны быть упакованы как модуль, если вы хотите предоставить справку для рабочего процесса. Сведения о модулях см. в разделе [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

- [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities)

- [Microsoft.Powershell.Core.Activities](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [Microsoft.Powershell.Diagnostics.Activities](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [Microsoft.Powershell.Security.Activities](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [Microsoft.Powershell.Utility.Activities](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  Ниже описаны способы создания рабочего процесса с помощью действий Windows PowerShell.

- [Добавление действия Windows PowerShell в область элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)

- [Создание рабочего процесса с помощью сценария Windows PowerShell](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [Импорт и вызова рабочего процесса Windows PowerShell](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Создание действия рабочего процесса из командлета Windows PowerShell](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)