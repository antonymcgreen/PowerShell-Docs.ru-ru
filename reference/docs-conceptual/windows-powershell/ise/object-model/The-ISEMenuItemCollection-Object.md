---
ms.date: 12/31/2019
title: Объект ISEMenuItemCollection
description: Объект ISEMenuItemCollection  — это коллекция объектов ISEMenuItem.
ms.openlocfilehash: cd86768d13b1326a8f35c44f0391ab60669cee4f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655996"
---
# <a name="the-isemenuitemcollection-object"></a>Объект ISEMenuItemCollection

Объект **ISEMenuItemCollection**   — это коллекция объектов **ISEMenuItem**. Он представляет собой экземпляр класса **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection**. Примером является объект `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`, используемый для настройки меню **Add-On** (Надстройка) в интегрированной среде скриптов Windows PowerShell&reg; (ISE).

## <a name="method"></a>Метод

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a>Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Добавляет пункт меню в коллекцию.

**DisplayName**  — отображаемое имя добавляемого меню.

**Action**  — объект **System.Management.Automation.ScriptBlock** , указывающий действие, связанное с этим пунктом меню.

**Shortcut**  — сочетание клавиш для действия.

**Returns**  — объект **ISEMenuItem** , который только что был добавлен.

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a>Clear\(\)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Удаляет все подменю из пункта меню.

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a>См. также:

- [Объект ISEMenuItem](The-ISEMenuItem-Object.md)
- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
