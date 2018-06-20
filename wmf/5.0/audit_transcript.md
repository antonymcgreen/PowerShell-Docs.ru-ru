---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 5e17b0a78f6e860c6144d2e81c426bb26126a85f
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222457"
---
# <a name="enhanced-transcription-options"></a><span data-ttu-id="a486b-102">Расширенные параметры транскрибирования</span><span class="sxs-lookup"><span data-stu-id="a486b-102">Enhanced Transcription Options</span></span>

<span data-ttu-id="a486b-103">Транскрибирование Windows PowerShell было улучшено и теперь распространяется на все приложения размещения (например, интегрированную среду сценариев Windows), а не только узел консоли (powershell.exe).</span><span class="sxs-lookup"><span data-stu-id="a486b-103">Windows PowerShell transcription has been improved to apply to all hosting applications (such as Windows PowerShell ISE) rather than just the console host (powershell.exe).</span></span>

<span data-ttu-id="a486b-104">Кроме того, сама эта функциональность была обновлена, чтобы поддерживать произвольное вложенные записи, дополнительные метаданные в заголовке полученной записи и задание каталога выходных данных транскрибирования (для поддержки централизованного сбора журналов).</span><span class="sxs-lookup"><span data-stu-id="a486b-104">In addition to extending for transcripting, the transcripting functionality itself has been updated to support arbitrary nesting of transcripts, additional metadata in the resulting transcript header, and setting a transcription output directory (to support centralized log collection).</span></span>

<span data-ttu-id="a486b-105">Параметры транскрибирования (в том числе включение записи во всей системе) можно настроить с помощью параметра групповой политики **Включить транскрипции PowerShell** ("Административные шаблоны" -> "Компоненты Windows" -> "Windows PowerShell").</span><span class="sxs-lookup"><span data-stu-id="a486b-105">Transcription options (including enabling a system-wide transcript) can be configured with the **Turn on PowerShell Transcription** Group Policy setting (in Administrative Templates -> Windows Components -> Windows PowerShell).</span></span>
