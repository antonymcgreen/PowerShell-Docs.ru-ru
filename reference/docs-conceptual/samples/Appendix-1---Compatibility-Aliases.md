---
ms.date: 08/03/2020
keywords: powershell,командлет
title: Приложение 1. Псевдонимы совместимости
description: PowerShell имеет несколько псевдонимов, позволяющих пользователям UNIX и cmd.exe использовать знакомые команды.
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500748"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="f1e74-104">Приложение 1. Псевдонимы совместимости</span><span class="sxs-lookup"><span data-stu-id="f1e74-104">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="f1e74-105">PowerShell имеет несколько псевдонимов, позволяющих пользователям **UNIX** и **cmd.exe** использовать знакомые команды.</span><span class="sxs-lookup"><span data-stu-id="f1e74-105">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="f1e74-106">Команды и связанные с ними командлеты PowerShell и псевдонимы PowerShell показаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="f1e74-106">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="f1e74-107">Команда cmd.exe</span><span class="sxs-lookup"><span data-stu-id="f1e74-107">cmd.exe command</span></span>            | <span data-ttu-id="f1e74-108">Команда UNIX</span><span class="sxs-lookup"><span data-stu-id="f1e74-108">UNIX command</span></span> | <span data-ttu-id="f1e74-109">Командлет PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1e74-109">PowerShell cmdlet</span></span> | <span data-ttu-id="f1e74-110">Псевдоним PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1e74-110">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="f1e74-111">**cd** , **chdir**</span><span class="sxs-lookup"><span data-stu-id="f1e74-111">**cd** , **chdir**</span></span>                     | <span data-ttu-id="f1e74-112">**cd**</span><span class="sxs-lookup"><span data-stu-id="f1e74-112">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="f1e74-113">**cls**</span><span class="sxs-lookup"><span data-stu-id="f1e74-113">**cls**</span></span>                               | <span data-ttu-id="f1e74-114">**пусто**</span><span class="sxs-lookup"><span data-stu-id="f1e74-114">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="f1e74-115">**copy**</span><span class="sxs-lookup"><span data-stu-id="f1e74-115">**copy**</span></span>                              | <span data-ttu-id="f1e74-116">**cp**</span><span class="sxs-lookup"><span data-stu-id="f1e74-116">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="f1e74-117">**del** , **erase** , **rd** , **rmdir**</span><span class="sxs-lookup"><span data-stu-id="f1e74-117">**del** , **erase** , **rd** , **rmdir**</span></span> | <span data-ttu-id="f1e74-118">**rm**</span><span class="sxs-lookup"><span data-stu-id="f1e74-118">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="f1e74-119">**dir**</span><span class="sxs-lookup"><span data-stu-id="f1e74-119">**dir**</span></span>                               | <span data-ttu-id="f1e74-120">**ls**</span><span class="sxs-lookup"><span data-stu-id="f1e74-120">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="f1e74-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="f1e74-121">**echo**</span></span>                              | <span data-ttu-id="f1e74-122">**echo**</span><span class="sxs-lookup"><span data-stu-id="f1e74-122">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="f1e74-123">**md**</span><span class="sxs-lookup"><span data-stu-id="f1e74-123">**md**</span></span>                                | <span data-ttu-id="f1e74-124">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="f1e74-124">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="f1e74-125">**move**</span><span class="sxs-lookup"><span data-stu-id="f1e74-125">**move**</span></span>                              | <span data-ttu-id="f1e74-126">**mv**</span><span class="sxs-lookup"><span data-stu-id="f1e74-126">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="f1e74-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="f1e74-127">**popd**</span></span>                              | <span data-ttu-id="f1e74-128">**popd**</span><span class="sxs-lookup"><span data-stu-id="f1e74-128">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="f1e74-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="f1e74-129">**pushd**</span></span>                             | <span data-ttu-id="f1e74-130">**pushd**</span><span class="sxs-lookup"><span data-stu-id="f1e74-130">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="f1e74-131">**ren**</span><span class="sxs-lookup"><span data-stu-id="f1e74-131">**ren**</span></span>                               | <span data-ttu-id="f1e74-132">**mv**</span><span class="sxs-lookup"><span data-stu-id="f1e74-132">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="f1e74-133">**type**</span><span class="sxs-lookup"><span data-stu-id="f1e74-133">**type**</span></span>                              | <span data-ttu-id="f1e74-134">**cat**</span><span class="sxs-lookup"><span data-stu-id="f1e74-134">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="f1e74-135">Чтобы найти псевдонимы PowerShell, используйте командлет [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="f1e74-135">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="f1e74-136">Чтобы отобразить псевдонимы командлета, используйте параметр **Definition** и укажите имя командлета.</span><span class="sxs-lookup"><span data-stu-id="f1e74-136">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="f1e74-137">Чтобы найти имя командлета псевдонима, используйте параметр **Name** и укажите псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f1e74-137">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
