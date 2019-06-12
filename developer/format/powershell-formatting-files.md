---
title: Windows PowerShell файлов форматирования | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: 4ec9e10647b752cc62b1eabb897ada3dc03c93eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66830263"
---
# <a name="windows-powershell-formatting-files"></a>Файлы форматирования Windows PowerShell

Windows PowerShell предоставляет несколько файлов форматирования (. format.ps1xml), которые находятся в каталоге установки (`$pshome`). Каждый из этих файлов определяет отображение по умолчанию для определенного набора объектов .NET. Эти файлы никогда не должны изменяться. Тем не менее вы их можно использовать как ссылку для создания собственных пользовательских файлов форматирования.

`Certificate.Format.ps1xml` Определяет отображение объектов в хранилище сертификатов, таких как сертификаты x.509 и хранилищам сертификатов.

`DotNetTypes.Format.ps1xml` Определяет отображение прочих объектов .NET, таких как объекты CultureInfo, FileVersionInfo и EventLogEntry.

`FileSystem.Format.ps1xml` Определяет отображение объектов файловой системы, такие как объекты файлов и каталогов.

`Help.Format.ps1xml` Определяет различные представления, используемые [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета, такие как подробные, full, параметров и пример представления.

`PowerShellCore.Format.ps1xml` Определяет отображение объектов, созданных основные командлеты Windows PowerShell, например объекты, возвращенные [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) и [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) командлетов.

`PowerShellTrace.Format.ps1xml` Определяет отображение объектов трассировки, которые созданы при [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) командлета.

`Registry.Format.ps1xml` Определяет отображение объектов реестра, таких как ключ и запись объектов.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
