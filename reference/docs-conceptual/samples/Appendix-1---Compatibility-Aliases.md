---
ms.date: 09/09/2019
keywords: powershell,командлет
title: Приложение 1. Псевдонимы совместимости
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "70848162"
---
# <a name="appendix-1---compatibility-aliases"></a>Приложение 1. Псевдонимы совместимости

PowerShell имеет несколько псевдонимов, позволяющих пользователям **UNIX** и **cmd.exe** использовать знакомые команды.
Команды и связанные с ними командлеты PowerShell и псевдонимы PowerShell показаны в следующей таблице:

|Команда cmd.exe|Команда UNIX|Командлет PowerShell|Псевдоним PowerShell|
|---------------|----------------|--------------|------------|
|**cls**|**пусто**|`Clear-Host` (функция)|`cls`|
|**copy**|**cp**|`Copy-Item`|`cpi`|
|**dir**|**ls**|`Get-ChildItem`|`gci`|
|**type**|**cat**|`Get-Content`|`gc`|
|**move**|**mv**|`Move-Item`|`mi`|
|**md**|**mkdir**|`New-Item`|`ni`|
|**pushd**|**pushd**|`Push-Location`|`pushd`|
|**popd**|**popd**|`Pop-Location`|`popd`|
|**del**, **erase**, **rd**, **rmdir**|**rm**|`Remove-Item`|`ri`|
|**ren**|**mv**|`Rename-Item`|`rni`|
|**cd**, **chdir**|**cd**|`Set-Location`|`sl`|

Чтобы найти псевдонимы PowerShell, используйте командлет [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias). Чтобы отобразить псевдонимы командлета, используйте параметр **Definition** и укажите имя командлета.
Чтобы найти имя командлета псевдонима, используйте параметр **Name** и укажите псевдоним.

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
