---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISEMenuItemCollection
ms.assetid: 0c0f5484-3320-408e-8534-5bd1c8e48512
ms.openlocfilehash: 7e5030416df394aaa9e9d3f63978e204a7faabf1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086703"
---
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="c91be-103">Объект ISEMenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="c91be-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="c91be-104">Объект **ISEMenuItemCollection**  — это коллекция объектов **ISEMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="c91be-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="c91be-105">Он является экземпляром класса Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection.</span><span class="sxs-lookup"><span data-stu-id="c91be-105">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection class.</span></span> <span data-ttu-id="c91be-106">Примером является объект **$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus**, используемый для настройки меню **Надстройка** (Add-On) в интегрированной среде скриптов Windows PowerShell® (ISE).</span><span class="sxs-lookup"><span data-stu-id="c91be-106">An example is the **$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus** object that is used to customize the **Add-On** menu in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="c91be-107">Метод</span><span class="sxs-lookup"><span data-stu-id="c91be-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="c91be-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="c91be-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="c91be-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c91be-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c91be-110">Добавляет пункт меню в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="c91be-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="c91be-111">**DisplayName** — отображаемое имя добавляемого меню.</span><span class="sxs-lookup"><span data-stu-id="c91be-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="c91be-112">**Action** — объект **System.Management.Automation.ScriptBlock**, указывающий действие, связанное с этим пунктом меню.</span><span class="sxs-lookup"><span data-stu-id="c91be-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="c91be-113">**Shortcut** — сочетание клавиш для действия.</span><span class="sxs-lookup"><span data-stu-id="c91be-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="c91be-114">**Returns** — объект ISEMenuItem, который только что был добавлен.</span><span class="sxs-lookup"><span data-stu-id="c91be-114">**Returns** The ISEMenuItem object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="c91be-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="c91be-115">Clear\(\)</span></span>

<span data-ttu-id="c91be-116">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c91be-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c91be-117">Удаляет все подменю из пункта меню.</span><span class="sxs-lookup"><span data-stu-id="c91be-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="c91be-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c91be-118">See Also</span></span>

- [<span data-ttu-id="c91be-119">Объект ISEMenuItem</span><span class="sxs-lookup"><span data-stu-id="c91be-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="c91be-120">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c91be-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="c91be-121">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="c91be-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)