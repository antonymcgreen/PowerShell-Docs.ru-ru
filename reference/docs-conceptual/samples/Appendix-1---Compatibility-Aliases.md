---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Приложение 1. Псевдонимы совместимости
ms.openlocfilehash: 553b9f01d6b5e3f4e04f1a75c25979b54dc205da
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030326"
---
# <a name="appendix-1---compatibility-aliases"></a>Приложение 1. Псевдонимы совместимости

Windows PowerShell имеет несколько псевдонимов перехода, позволяющих пользователям UNIX и Cmd применять знакомые команды в Windows PowerShell. Наиболее распространенные псевдонимы приведены в таблице ниже, также там указана команда Windows PowerShell для псевдонима и стандартный псевдоним Windows PowerShell, если он существует.

Найти команду Windows PowerShell, на которую указывает псевдоним из Windows PowerShell, можно с помощью командлета Get-Alias. Например, введите **get-alias cls**.

```
CommandType     Name                            Definition
-----------     ----                            ----------
Alias           cls                             Clear-Host
```

|Команда CMD|Команда UNIX|Команда PS|Псевдоним PS|
|---------------|----------------|--------------|------------|
|**dir**|**ls**|**Get-ChildItem**|**gci**|
|**cls**|**clear**|**Clear-Host** (функция)|**cls**|
|**del, erase, rmdir**|**rm**|**Remove-Item**|**ri**|
|**copy**|**cp**|**Copy-Item**|**ci**|
|**move**|**mv**|**Move-Item**|**mi**|
|**rename**|**mv**|**Rename-Item**|**rni**|
|**type**|**cat**|**Get-Content**|**gc**|
|**cd**|**cd**|**Set-Location**|**sl**|
|**md**|**mkdir**|**New-Item**|**ni**|
|**pushd**|**pushd**|**Push-Location**|**pushd**|
|**popd**|**popd**|**Pop-Location**|**popd**|
