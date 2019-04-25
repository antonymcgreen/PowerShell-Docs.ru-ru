---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 5280ef5ff95679dc8721be8f5f81031a4ffe796f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085255"
---
# <a name="updates-to-fileinfo-object"></a><span data-ttu-id="69706-102">Изменения объекта FileInfo</span><span class="sxs-lookup"><span data-stu-id="69706-102">Updates to FileInfo object</span></span>
<span data-ttu-id="69706-103">Сведения о версии файла могут вводить пользователя в заблуждение, особенно в случаях, когда файл был исправлен.</span><span class="sxs-lookup"><span data-stu-id="69706-103">File version information can be misleading, particularly in cases where the file was patched.</span></span> <span data-ttu-id="69706-104">Этот выпуск WMF 5.0 добавляет новые свойства **FileVersionRaw** и **ProductVersionRaw** сценария для объектов FileInfo.</span><span class="sxs-lookup"><span data-stu-id="69706-104">This release of WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to FileInfo objects.</span></span> <span data-ttu-id="69706-105">Ниже приведены свойства, отображаемые для powershell.exe (при условии, что $pid является идентификатором процесса PowerShell).</span><span class="sxs-lookup"><span data-stu-id="69706-105">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117
