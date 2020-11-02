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
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="c5a4c-104">Объект PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="c5a4c-104">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="c5a4c-105">Объект коллекции **PowerShellTabCollection**  — это коллекция объектов **PowerShellTab** .</span><span class="sxs-lookup"><span data-stu-id="c5a4c-105">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="c5a4c-106">Каждый объект **PowerShellTab** функционирует как отдельная среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-106">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="c5a4c-107">Он является экземпляром класса Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-107">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="c5a4c-108">Примером является объект `$psISE.PowerShellTabs`.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-108">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="c5a4c-109">Методы</span><span class="sxs-lookup"><span data-stu-id="c5a4c-109">Methods</span></span>

### <a name="add"></a><span data-ttu-id="c5a4c-110">Add \(\)</span><span class="sxs-lookup"><span data-stu-id="c5a4c-110">Add\(\)</span></span>

<span data-ttu-id="c5a4c-111">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c5a4c-112">Добавляет новую вкладку PowerShell в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-112">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="c5a4c-113">Метод возвращает вновь добавленную вкладку.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-113">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="c5a4c-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="c5a4c-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="c5a4c-115">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c5a4c-116">Удаляет вкладку, которая указана параметром **psTab** .</span><span class="sxs-lookup"><span data-stu-id="c5a4c-116">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="c5a4c-117">**psTab**  — удаляемая вкладка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-117">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="c5a4c-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="c5a4c-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="c5a4c-119">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c5a4c-120">Выбирает вкладку PowerShell, которая задается параметром **psTab** , чтобы сделать ее активной вкладкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-120">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="c5a4c-121">**psTab**  — выбираемая вкладка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5a4c-121">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c5a4c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c5a4c-122">See Also</span></span>

- [<span data-ttu-id="c5a4c-123">Объект PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="c5a4c-123">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="c5a4c-124">Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5a4c-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="c5a4c-125">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="c5a4c-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
