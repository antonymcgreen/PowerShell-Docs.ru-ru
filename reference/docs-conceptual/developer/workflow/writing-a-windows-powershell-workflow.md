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
ms.openlocfilehash: 0f8a9938a1685e9abc2f1dbfb18c3b2b9008d9be
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564932"
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

- [Добавление действий Windows PowerShell в инструментарий Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)

- [Создание рабочего процесса с помощью сценария Windows PowerShell](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [Импорт и вызов рабочего процесса Windows PowerShell](./importing-and-invoking-a-windows-powershell-workflow.md)

- [Создание действия рабочего процесса из командлета Windows PowerShell](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)
