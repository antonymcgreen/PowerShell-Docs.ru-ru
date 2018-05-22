---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 9ca12ad3f0729a2e9595d7ca5ccf9041e47658a3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="archive-cmdlets"></a><span data-ttu-id="1074c-102">Командлеты Archive</span><span class="sxs-lookup"><span data-stu-id="1074c-102">Archive cmdlets</span></span>

<span data-ttu-id="1074c-103">Два новых командлета **Compress-Archive** и **Expand-Archive** позволяют сжимать и распаковывать ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="1074c-103">Two new cmdlets, **Compress-Archive** and **Expand-Archive**, let you compress and expand ZIP files.</span></span>

## <a name="compress-archive"></a><span data-ttu-id="1074c-104">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="1074c-104">Compress-Archive</span></span>
<span data-ttu-id="1074c-105">Командлет **Compress-Archive** создает новый файл архива из указанных файлов.</span><span class="sxs-lookup"><span data-stu-id="1074c-105">The **Compress-Archive** cmdlet creates a new archive file from specified files.</span></span> <span data-ttu-id="1074c-106">Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один для упрощения обработки и хранения.</span><span class="sxs-lookup"><span data-stu-id="1074c-106">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span> <span data-ttu-id="1074c-107">Файл архива можно сжать с помощью алгоритма, указанного в параметре **-CompressionLevel**.</span><span class="sxs-lookup"><span data-stu-id="1074c-107">An archive file can be compressed by using a compression algorithm specified in the **-CompressionLevel** parameter.</span></span>
```powershell
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
```

## <a name="expand-archive"></a><span data-ttu-id="1074c-108">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="1074c-108">Expand-Archive</span></span>
<span data-ttu-id="1074c-109">Командлет **Expand-Archive** извлекает файлы из указанного файла архива.</span><span class="sxs-lookup"><span data-stu-id="1074c-109">The **Expand-Archive** cmdlet extracts files from a specified archive file.</span></span> <span data-ttu-id="1074c-110">Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один для упрощения обработки и хранения.</span><span class="sxs-lookup"><span data-stu-id="1074c-110">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span>
```powershell
Expand-Archive -LiteralPath <String> [-DestinationPath] <String>
Expand-Archive [-Path] <String> [-DestinationPath] <String>
```
