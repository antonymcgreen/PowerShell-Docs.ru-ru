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
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="d8278-103">Объект ISEMenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="d8278-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="d8278-104">Объект **ISEMenuItemCollection**   — это коллекция объектов **ISEMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="d8278-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="d8278-105">Он представляет собой экземпляр класса **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection**.</span><span class="sxs-lookup"><span data-stu-id="d8278-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** class.</span></span> <span data-ttu-id="d8278-106">Примером является объект `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`, используемый для настройки меню **Add-On** (Надстройка) в интегрированной среде скриптов Windows PowerShell&reg; (ISE).</span><span class="sxs-lookup"><span data-stu-id="d8278-106">An example is the `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus` object that is used to customize the **Add-On** menu in Windows PowerShell&reg; Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="d8278-107">Метод</span><span class="sxs-lookup"><span data-stu-id="d8278-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="d8278-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="d8278-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="d8278-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d8278-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="d8278-110">Добавляет пункт меню в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="d8278-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="d8278-111">**DisplayName**  — отображаемое имя добавляемого меню.</span><span class="sxs-lookup"><span data-stu-id="d8278-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="d8278-112">**Action**  — объект **System.Management.Automation.ScriptBlock** , указывающий действие, связанное с этим пунктом меню.</span><span class="sxs-lookup"><span data-stu-id="d8278-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="d8278-113">**Shortcut**  — сочетание клавиш для действия.</span><span class="sxs-lookup"><span data-stu-id="d8278-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="d8278-114">**Returns**  — объект **ISEMenuItem** , который только что был добавлен.</span><span class="sxs-lookup"><span data-stu-id="d8278-114">**Returns** The **ISEMenuItem** object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="d8278-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="d8278-115">Clear\(\)</span></span>

<span data-ttu-id="d8278-116">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d8278-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="d8278-117">Удаляет все подменю из пункта меню.</span><span class="sxs-lookup"><span data-stu-id="d8278-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="d8278-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8278-118">See Also</span></span>

- [<span data-ttu-id="d8278-119">Объект ISEMenuItem</span><span class="sxs-lookup"><span data-stu-id="d8278-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="d8278-120">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8278-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="d8278-121">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="d8278-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
