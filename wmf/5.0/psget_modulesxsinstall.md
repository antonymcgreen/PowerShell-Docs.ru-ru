---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 0a481fb9d4f2aab89bc448c71b01f1d541cf24bc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085088"
---
# <a name="side-by-side-version-support-on-powershell-50-or-newer"></a><span data-ttu-id="b4105-102">Поддержка параллельных версий в PowerShell 5.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="b4105-102">Side-by-Side Version Support on PowerShell 5.0 or newer</span></span>

<span data-ttu-id="b4105-103">Теперь в командлетах Install-Module, Update-Module и Publish-Module, выполняемых в Windows PowerShell 5.0 или более поздней версии, имеется поддержка параллельных (SxS) версий модуля.</span><span class="sxs-lookup"><span data-stu-id="b4105-103">There is now side-by-side (SxS) module version support in Install-Module, Update-Module, and Publish-Module cmdlets that run in Windows PowerShell 5.0 or newer.</span></span>
<span data-ttu-id="b4105-104">Кроме того, мы добавили в командлет Publish-Module параметр -RequiredVersion для указания публикуемой версии.</span><span class="sxs-lookup"><span data-stu-id="b4105-104">Also, we have added a -RequiredVersion parameter to the Publish-Module cmdlet to specify the version to be published.</span></span> <span data-ttu-id="b4105-105">Параметр Path теперь поддерживает базовый путь к модулю с папкой версии.</span><span class="sxs-lookup"><span data-stu-id="b4105-105">The Path parameter now supports the module base path with the version folder.</span></span>

<span data-ttu-id="b4105-106">**Примеры использования Install-Module**</span><span class="sxs-lookup"><span data-stu-id="b4105-106">**Install-Module examples:**</span></span>
```powershell
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.0 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name : PSScriptAnalyzer
Version : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.1 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name       : PSScriptAnalyzer
Version    : 1.1.1
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.1
Name       : PSScriptAnalyzer
Version    : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

Get-InstalledModule -Name PSScriptAnalyzer -AllVersions

Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.1.0      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis...
1.1.1      PSScriptAnalyzer                    Module     PSGallery            PSScriptAnalyzer provides script analysis...
```
