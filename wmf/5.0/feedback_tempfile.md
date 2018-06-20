---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 08f431c27cd0ee769518b5246af2fa95aa499d54
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34217997"
---
# <a name="new-temporaryfile"></a><span data-ttu-id="79593-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="79593-102">New-TemporaryFile</span></span>
<span data-ttu-id="79593-103">Иногда в сценариях необходимо создать временный файл.</span><span class="sxs-lookup"><span data-stu-id="79593-103">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="79593-104">Для этого удобно использовать командлет **New-TemporaryFile**:</span><span class="sxs-lookup"><span data-stu-id="79593-104">You can easily do this with the **New-TemporaryFile** cmdlet:</span></span>

<span data-ttu-id="79593-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="79593-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span></span>

<span data-ttu-id="79593-106">PS C:\\&gt; $tempFile.FullName</span><span class="sxs-lookup"><span data-stu-id="79593-106">PS C:\\&gt; $tempFile.FullName</span></span>

<span data-ttu-id="79593-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span><span class="sxs-lookup"><span data-stu-id="79593-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span></span>
