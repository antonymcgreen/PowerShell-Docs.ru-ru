---
ms.date: 09/09/2019
keywords: powershell,командлет
title: Приложение 1. Псевдонимы совместимости
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "70848162"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="be762-103">Приложение 1. Псевдонимы совместимости</span><span class="sxs-lookup"><span data-stu-id="be762-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="be762-104">PowerShell имеет несколько псевдонимов, позволяющих пользователям **UNIX** и **cmd.exe** использовать знакомые команды.</span><span class="sxs-lookup"><span data-stu-id="be762-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="be762-105">Команды и связанные с ними командлеты PowerShell и псевдонимы PowerShell показаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="be762-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|<span data-ttu-id="be762-106">Команда cmd.exe</span><span class="sxs-lookup"><span data-stu-id="be762-106">cmd.exe command</span></span>|<span data-ttu-id="be762-107">Команда UNIX</span><span class="sxs-lookup"><span data-stu-id="be762-107">UNIX command</span></span>|<span data-ttu-id="be762-108">Командлет PowerShell</span><span class="sxs-lookup"><span data-stu-id="be762-108">PowerShell cmdlet</span></span>|<span data-ttu-id="be762-109">Псевдоним PowerShell</span><span class="sxs-lookup"><span data-stu-id="be762-109">PowerShell alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="be762-110">**cls**</span><span class="sxs-lookup"><span data-stu-id="be762-110">**cls**</span></span>|<span data-ttu-id="be762-111">**clear**</span><span class="sxs-lookup"><span data-stu-id="be762-111">**clear**</span></span>|<span data-ttu-id="be762-112">`Clear-Host` (функция)</span><span class="sxs-lookup"><span data-stu-id="be762-112">`Clear-Host` (function)</span></span>|`cls`|
|<span data-ttu-id="be762-113">**copy**</span><span class="sxs-lookup"><span data-stu-id="be762-113">**copy**</span></span>|<span data-ttu-id="be762-114">**cp**</span><span class="sxs-lookup"><span data-stu-id="be762-114">**cp**</span></span>|`Copy-Item`|`cpi`|
|<span data-ttu-id="be762-115">**dir**</span><span class="sxs-lookup"><span data-stu-id="be762-115">**dir**</span></span>|<span data-ttu-id="be762-116">**ls**</span><span class="sxs-lookup"><span data-stu-id="be762-116">**ls**</span></span>|`Get-ChildItem`|`gci`|
|<span data-ttu-id="be762-117">**type**</span><span class="sxs-lookup"><span data-stu-id="be762-117">**type**</span></span>|<span data-ttu-id="be762-118">**cat**</span><span class="sxs-lookup"><span data-stu-id="be762-118">**cat**</span></span>|`Get-Content`|`gc`|
|<span data-ttu-id="be762-119">**move**</span><span class="sxs-lookup"><span data-stu-id="be762-119">**move**</span></span>|<span data-ttu-id="be762-120">**mv**</span><span class="sxs-lookup"><span data-stu-id="be762-120">**mv**</span></span>|`Move-Item`|`mi`|
|<span data-ttu-id="be762-121">**md**</span><span class="sxs-lookup"><span data-stu-id="be762-121">**md**</span></span>|<span data-ttu-id="be762-122">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="be762-122">**mkdir**</span></span>|`New-Item`|`ni`|
|<span data-ttu-id="be762-123">**pushd**</span><span class="sxs-lookup"><span data-stu-id="be762-123">**pushd**</span></span>|<span data-ttu-id="be762-124">**pushd**</span><span class="sxs-lookup"><span data-stu-id="be762-124">**pushd**</span></span>|`Push-Location`|`pushd`|
|<span data-ttu-id="be762-125">**popd**</span><span class="sxs-lookup"><span data-stu-id="be762-125">**popd**</span></span>|<span data-ttu-id="be762-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="be762-126">**popd**</span></span>|`Pop-Location`|`popd`|
|<span data-ttu-id="be762-127">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="be762-127">**del**, **erase**, **rd**, **rmdir**</span></span>|<span data-ttu-id="be762-128">**rm**</span><span class="sxs-lookup"><span data-stu-id="be762-128">**rm**</span></span>|`Remove-Item`|`ri`|
|<span data-ttu-id="be762-129">**ren**</span><span class="sxs-lookup"><span data-stu-id="be762-129">**ren**</span></span>|<span data-ttu-id="be762-130">**mv**</span><span class="sxs-lookup"><span data-stu-id="be762-130">**mv**</span></span>|`Rename-Item`|`rni`|
|<span data-ttu-id="be762-131">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="be762-131">**cd**, **chdir**</span></span>|<span data-ttu-id="be762-132">**cd**</span><span class="sxs-lookup"><span data-stu-id="be762-132">**cd**</span></span>|`Set-Location`|`sl`|

<span data-ttu-id="be762-133">Чтобы найти псевдонимы PowerShell, используйте командлет [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="be762-133">To find the PowerShell aliases, use the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet.</span></span> <span data-ttu-id="be762-134">Чтобы отобразить псевдонимы командлета, используйте параметр **Definition** и укажите имя командлета.</span><span class="sxs-lookup"><span data-stu-id="be762-134">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="be762-135">Чтобы найти имя командлета псевдонима, используйте параметр **Name** и укажите псевдоним.</span><span class="sxs-lookup"><span data-stu-id="be762-135">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
