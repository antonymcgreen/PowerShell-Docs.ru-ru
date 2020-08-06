---
title: Файлы форматирования Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 54fae12163f8d439c2acc24df17ed140a556cba0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783506"
---
# <a name="windows-powershell-formatting-files"></a>Файлы форматирования Windows PowerShell

Windows PowerShell предоставляет несколько файлов форматирования (.format.ps1XML), которые находятся в каталоге установки ( `$pshome` ). Каждый из этих файлов определяет отображение по умолчанию для определенного набора объектов .NET. Эти файлы никогда не следует изменять. Однако их можно использовать в качестве справочной документации по созданию собственных файлов форматирования.

`Certificate.Format.ps1xml`Определяет отображение объектов в хранилище сертификатов, таких как сертификаты x. 509 и хранилища сертификатов.

`DotNetTypes.Format.ps1xml`Определяет отображение различных объектов .NET, таких как CultureInfo, FileVersionInfo и объекты EventLogEntry.

`FileSystem.Format.ps1xml`Определяет отображение объектов файловой системы, таких как объекты файлов и каталогов.

`Help.Format.ps1xml`Определяет различные представления, используемые командлетом [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) , такие как подробные представления, полные, параметры и примеры представлений.

`PowerShellCore.Format.ps1xml`Определяет отображение объектов, созданных основными командлетами Windows PowerShell, например объекты, возвращаемые командлетами [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) и [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) .

`PowerShellTrace.Format.ps1xml`Определяет отображение объектов трассировки, таких как созданные с помощью командлета [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) .

`Registry.Format.ps1xml`Определяет отображение объектов реестра, таких как объекты key и Entry.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
