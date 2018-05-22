---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 9ca12ad3f0729a2e9595d7ca5ccf9041e47658a3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="archive-cmdlets"></a>Командлеты Archive

Два новых командлета **Compress-Archive** и **Expand-Archive** позволяют сжимать и распаковывать ZIP-файлы.

## <a name="compress-archive"></a>Compress-Archive
Командлет **Compress-Archive** создает новый файл архива из указанных файлов. Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один для упрощения обработки и хранения. Файл архива можно сжать с помощью алгоритма, указанного в параметре **-CompressionLevel**.
```powershell
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
```

## <a name="expand-archive"></a>Expand-Archive
Командлет **Expand-Archive** извлекает файлы из указанного файла архива. Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один для упрощения обработки и хранения.
```powershell
Expand-Archive -LiteralPath <String> [-DestinationPath] <String>
Expand-Archive [-Path] <String> [-DestinationPath] <String>
```
