---
ms.date: 08/03/2020
keywords: powershell,командлет
title: Приложение 1. Псевдонимы совместимости
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758505"
---
# <a name="appendix-1---compatibility-aliases"></a>Приложение 1. Псевдонимы совместимости

PowerShell имеет несколько псевдонимов, позволяющих пользователям **UNIX** и **cmd.exe** использовать знакомые команды.
Команды и связанные с ними командлеты PowerShell и псевдонимы PowerShell показаны в следующей таблице:

|            Команда cmd.exe            | Команда UNIX | Командлет PowerShell | Псевдоним PowerShell |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd**, **chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **пусто**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del**, **erase**, **rd**, **rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| **echo**                              | **echo**     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| **type**                              | **cat**      | `Get-Content`     | `gc`             |

Чтобы найти псевдонимы PowerShell, используйте командлет [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias). Чтобы отобразить псевдонимы командлета, используйте параметр **Definition** и укажите имя командлета.
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
