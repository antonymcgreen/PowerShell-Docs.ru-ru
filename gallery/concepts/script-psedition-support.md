---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Сценарии с совместимыми выпусками PowerShell
ms.openlocfilehash: 2313131fe17dcd9508db514883ae3dcb837fb07e
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587216"
---
# <a name="script-with-compatible-powershell-editions"></a>Сценарии с совместимыми выпусками PowerShell

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

- **Выпуск Desktop Edition:** построен на основе .NET Framework и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в полноценных выпусках Windows, таких как Server Core и Windows Desktop.

- **Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

Запущенный выпуск PowerShell отображается в свойстве PSEdition параметра $PSVersionTable.

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

Авторы скриптов могут запретить их выполнение, если они не выполняются в совместимой версии PowerShell, с помощью параметра PSEdition инструкции `#requires`.

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

Пользователи коллекции PowerShell могут найти список сценариев, поддерживаемых в определенной версии PowerShell.
Считается, что скрипты без тегов PSEdition_Desktop и PSEdition_Core работают в выпуске PowerShell, предназначенном для компьютера.

```powershell
# Find scripts supported on PowerShell Desktop edition
Find-Script -Tag PSEdition_Desktop

# Find scripts supported on PowerShell Core edition
Find-Script -Tag PSEdition_Core
```

## <a name="more-details"></a>Дополнительные подробности

- [Модули с PSEditions](module-psedition-support.md)
- [Поддержка PSEditions в коллекции PowerShell](../how-to/finding-items/searching-by-psedition.md)
