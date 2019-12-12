---
title: Файлы форматирования Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 3ec127d5ff60754de5d7f1ac73f2965524228b9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365013"
---
# <a name="windows-powershell-formatting-files"></a>Файлы форматирования Windows PowerShell

Windows PowerShell предоставляет несколько файлов форматирования (. Format. ps1xml), которые находятся в каталоге установки (`$pshome`). Каждый из этих файлов определяет отображение по умолчанию для определенного набора объектов .NET. Эти файлы никогда не следует изменять. Однако их можно использовать в качестве справочной документации по созданию собственных файлов форматирования.

`Certificate.Format.ps1xml` определяет отображение объектов в хранилище сертификатов, например сертификаты x. 509 и хранилища сертификатов.

`DotNetTypes.Format.ps1xml` определяет отображение различных объектов .NET, таких как CultureInfo, FileVersionInfo и объекты EventLogEntry.

`FileSystem.Format.ps1xml` определяет отображение объектов файловой системы, таких как объекты файлов и каталогов.

`Help.Format.ps1xml` определяет различные представления, используемые командлетом [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) , такие как подробные представления, полные, параметры и примеры представлений.

`PowerShellCore.Format.ps1xml` определяет отображение объектов, создаваемых командлетами Windows PowerShell Core, таких как объекты, возвращаемые командлетами [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) и [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) .

`PowerShellTrace.Format.ps1xml` определяет отображение объектов трассировки, таких как созданные с помощью командлета [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) .

`Registry.Format.ps1xml` определяет отображение объектов реестра, таких как объекты key и Entry.

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
