---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Сценарии с совместимыми выпусками PowerShell
ms.openlocfilehash: e364879f611429a8583e550fb7704431e456fbb1
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328065"
---
# <a name="script-with-compatible-powershell-editions"></a><span data-ttu-id="6e1b0-103">Сценарии с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e1b0-103">Script with compatible PowerShell editions</span></span>

<span data-ttu-id="6e1b0-104">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="6e1b0-105">**Desktop Edition:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>

- <span data-ttu-id="6e1b0-106">**Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="6e1b0-107">Запущенный выпуск PowerShell отображается в свойстве PSEdition параметра $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-107">The running edition of PowerShell is shown in the PSEdition property of $PSVersionTable.</span></span>

```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

<span data-ttu-id="6e1b0-108">Авторы скриптов могут запретить их выполнение, если они не выполняются в совместимой версии PowerShell, с помощью параметра PSEdition инструкции `#requires`.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-108">Script authors can prevent a script from executing unless it is run on a compatible edition of PowerShell using the PSEdition parameter on a `#requires` statement.</span></span>

```powershell
Set-Content C:\script.ps1 -Value "#requires -PSEdition Core
Get-Process -Name PowerShell"
Get-Content C:\script.ps1
#requires -PSEdition Core
Get-Process -Name PowerShell

C:\script.ps1
C:\script.ps1 : The script 'script.ps1' cannot be run because it contained a "#requires" statement for PowerShell editions 'Core'. The edition of PowerShell that is required by the script does not match the currently running PowerShell Desktop edition.
At line:1 char:1
+ C:\script.ps1
+ ~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (script.ps1:String) [], RuntimeException
    + FullyQualifiedErrorId : ScriptRequiresUnmatchedPSEdition
```

<span data-ttu-id="6e1b0-109">Пользователи коллекции PowerShell могут найти список сценариев, поддерживаемых в определенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-109">PowerShell Gallery users can find the list of scripts supported on a specific PowerShell Edition.</span></span>
<span data-ttu-id="6e1b0-110">Считается, что скрипты без тегов PSEdition_Desktop и PSEdition_Core работают в выпуске PowerShell, предназначенном для компьютера.</span><span class="sxs-lookup"><span data-stu-id="6e1b0-110">Scripts without PSEdition_Desktop and PSEdition_Core tags are considered to work fine on PowerShell Desktop edition.</span></span>

```powershell
# Find scripts supported on PowerShell Desktop edition
Find-Script -Tag PSEdition_Desktop

# Find scripts supported on PowerShell Core edition
Find-Script -Tag PSEdition_Core
```

## <a name="more-details"></a><span data-ttu-id="6e1b0-111">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="6e1b0-111">More details</span></span>

- [<span data-ttu-id="6e1b0-112">Модули с PSEditions</span><span class="sxs-lookup"><span data-stu-id="6e1b0-112">Modules with PSEditions</span></span>](module-psedition-support.md)
- [<span data-ttu-id="6e1b0-113">Поддержка PSEditions в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e1b0-113">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)
