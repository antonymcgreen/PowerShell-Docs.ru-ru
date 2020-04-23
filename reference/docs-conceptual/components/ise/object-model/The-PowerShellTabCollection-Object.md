---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект PowerShellTabCollection
ms.openlocfilehash: 0aad885afd3ba3ae3b00f5c11d2c62a9ff303798
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736119"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="6a417-103">Объект PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="6a417-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="6a417-104">Объект коллекции **PowerShellTabCollection** — это коллекция объектов **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="6a417-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="6a417-105">Каждый объект **PowerShellTab** функционирует как отдельная среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="6a417-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="6a417-106">Он является экземпляром класса Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="6a417-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="6a417-107">Примером является объект `$psISE.PowerShellTabs`.</span><span class="sxs-lookup"><span data-stu-id="6a417-107">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="6a417-108">Методы</span><span class="sxs-lookup"><span data-stu-id="6a417-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="6a417-109">Add \(\)</span><span class="sxs-lookup"><span data-stu-id="6a417-109">Add\(\)</span></span>

<span data-ttu-id="6a417-110">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="6a417-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6a417-111">Добавляет новую вкладку PowerShell в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="6a417-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="6a417-112">Метод возвращает вновь добавленную вкладку.</span><span class="sxs-lookup"><span data-stu-id="6a417-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="6a417-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="6a417-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="6a417-114">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="6a417-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6a417-115">Удаляет вкладку, которая указана параметром **psTab**.</span><span class="sxs-lookup"><span data-stu-id="6a417-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="6a417-116">**psTab** — удаляемая вкладка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a417-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="6a417-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="6a417-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="6a417-118">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="6a417-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="6a417-119">Выбирает вкладку PowerShell, которая задается параметром **psTab**, чтобы сделать ее активной вкладкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a417-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="6a417-120">**psTab** — выбираемая вкладка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a417-120">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6a417-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a417-121">See Also</span></span>

- [<span data-ttu-id="6a417-122">Объект PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="6a417-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="6a417-123">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a417-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="6a417-124">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="6a417-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
