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
ms.openlocfilehash: 35efd36fd70c209e3cbeb9eff0ddf978615fffd6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854270"
---
# <a name="windows-powershell-formatting-files"></a>Файлы форматирования Windows PowerShell

Windows PowerShell предоставляет несколько файлов форматирования (. format.ps1xml), которые находятся в каталоге установки (`$pshome`). Каждый из этих файлов определяет отображение по умолчанию для определенного набора объектов .NET. Эти файлы никогда не должны изменяться. Тем не менее вы их можно использовать как ссылку для создания собственных пользовательских файлов форматирования.

Certificate.Format.ps1xml определяют способ отображения объектов в хранилище сертификатов, таких как сертификаты x.509 и хранилищам сертификатов.

DotNetTypes.Format.ps1xml определяет отображение прочих объектов .NET, таких как объекты CultureInfo, FileVersionInfo и EventLogEntry.

FileSystem.Format.ps1xml определяет отображение объектов файловой системы, такие как объекты файлов и каталогов.

Help.Format.ps1xml: определяет различные представления, используемые [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета, такие как подробные, full, параметров и пример представления.
Определяет различные представления, используемые [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) командлета, такие как подробные, full, параметров и пример представления.

PowerShellCore.Format.ps1xml определяет отображение объектов, созданных основные командлеты Windows PowerShell, например объекты, возвращенные [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) и [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) командлетов.
Определяет отображение объектов, созданных основные командлеты Windows PowerShell, например объекты, возвращенные [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) и [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) командлетов.

PowerShellTrace.Format.ps1xml определяет отображение объектов трассировки, которые созданы при [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) командлета.
Определяет отображение объектов трассировки, которые созданы при [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) командлета.

Registry.Format.ps1xml определяют способ отображения объектов реестра, таких как ключ и запись объектов.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
