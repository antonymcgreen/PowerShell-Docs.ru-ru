---
title: Создание рабочего процесса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366013"
---
# <a name="writing-a-windows-powershell-workflow"></a>Запись рабочего процесса Windows PowerShell

Вы можете создать рабочий процесс XAML, добавив действия, предоставляемые сборками Windows PowerShell, в конструктор рабочих процессов в Visual Studio. Следующие сборки Windows PowerShell предоставляют действия, поддерживающие рабочие процессы.

> [!IMPORTANT]
> Рабочий процесс XAML должен быть упакован в модуль, если требуется предоставить справку для рабочего процесса. Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

- [Microsoft. PowerShell. действия](/dotnet/api/Microsoft.PowerShell.Activities)

- [Microsoft. PowerShell. Core. Activitys](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [Microsoft. PowerShell. Diagnostics. Activitys](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [Microsoft. PowerShell. Management. Activitys](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [Microsoft. PowerShell. Security. Activitys](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [Microsoft. PowerShell. Utility. Activitys](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  В следующих разделах описывается создание рабочего процесса с помощью действий Windows PowerShell.

- [Добавление действий Windows PowerShell в панель элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)

- [Создание рабочего процесса с помощью сценария Windows PowerShell](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [Импорт и вызов рабочего процесса Windows PowerShell](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Создание действия рабочего процесса из командлета Windows PowerShell](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)