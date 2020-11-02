---
ms.date: 06/05/2017
title: Объект PowerShellTabCollection
description: Объект коллекции PowerShellTabCollection — это коллекция объектов PowerShellTab. Каждый объект PowerShellTab функционирует как отдельная среда выполнения.
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658275"
---
# <a name="the-powershelltabcollection-object"></a>Объект PowerShellTabCollection

Объект коллекции **PowerShellTabCollection**  — это коллекция объектов **PowerShellTab** . Каждый объект **PowerShellTab** функционирует как отдельная среда выполнения. Он является экземпляром класса Microsoft.PowerShell.Host.ISE.PowerShellTabs. Примером является объект `$psISE.PowerShellTabs`.

## <a name="methods"></a>Методы

### <a name="add"></a>Add \(\)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Добавляет новую вкладку PowerShell в коллекцию. Метод возвращает вновь добавленную вкладку.

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a>Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Удаляет вкладку, которая указана параметром **psTab** .

**psTab**  — удаляемая вкладка PowerShell.

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a>SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Выбирает вкладку PowerShell, которая задается параметром **psTab** , чтобы сделать ее активной вкладкой PowerShell.

**psTab**  — выбираемая вкладка PowerShell.

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a>См. также

- [Объект PowerShellTab](The-PowerShellTab-Object.md)
- [Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
