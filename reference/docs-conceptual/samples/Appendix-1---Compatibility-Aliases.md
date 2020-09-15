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
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="0a017-103">Приложение 1. Псевдонимы совместимости</span><span class="sxs-lookup"><span data-stu-id="0a017-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="0a017-104">PowerShell имеет несколько псевдонимов, позволяющих пользователям **UNIX** и **cmd.exe** использовать знакомые команды.</span><span class="sxs-lookup"><span data-stu-id="0a017-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="0a017-105">Команды и связанные с ними командлеты PowerShell и псевдонимы PowerShell показаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="0a017-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="0a017-106">Команда cmd.exe</span><span class="sxs-lookup"><span data-stu-id="0a017-106">cmd.exe command</span></span>            | <span data-ttu-id="0a017-107">Команда UNIX</span><span class="sxs-lookup"><span data-stu-id="0a017-107">UNIX command</span></span> | <span data-ttu-id="0a017-108">Командлет PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a017-108">PowerShell cmdlet</span></span> | <span data-ttu-id="0a017-109">Псевдоним PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a017-109">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="0a017-110">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="0a017-110">**cd**, **chdir**</span></span>                     | <span data-ttu-id="0a017-111">**cd**</span><span class="sxs-lookup"><span data-stu-id="0a017-111">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="0a017-112">**cls**</span><span class="sxs-lookup"><span data-stu-id="0a017-112">**cls**</span></span>                               | <span data-ttu-id="0a017-113">**пусто**</span><span class="sxs-lookup"><span data-stu-id="0a017-113">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="0a017-114">**copy**</span><span class="sxs-lookup"><span data-stu-id="0a017-114">**copy**</span></span>                              | <span data-ttu-id="0a017-115">**cp**</span><span class="sxs-lookup"><span data-stu-id="0a017-115">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="0a017-116">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="0a017-116">**del**, **erase**, **rd**, **rmdir**</span></span> | <span data-ttu-id="0a017-117">**rm**</span><span class="sxs-lookup"><span data-stu-id="0a017-117">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="0a017-118">**dir**</span><span class="sxs-lookup"><span data-stu-id="0a017-118">**dir**</span></span>                               | <span data-ttu-id="0a017-119">**ls**</span><span class="sxs-lookup"><span data-stu-id="0a017-119">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="0a017-120">**echo**</span><span class="sxs-lookup"><span data-stu-id="0a017-120">**echo**</span></span>                              | <span data-ttu-id="0a017-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="0a017-121">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="0a017-122">**md**</span><span class="sxs-lookup"><span data-stu-id="0a017-122">**md**</span></span>                                | <span data-ttu-id="0a017-123">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="0a017-123">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="0a017-124">**move**</span><span class="sxs-lookup"><span data-stu-id="0a017-124">**move**</span></span>                              | <span data-ttu-id="0a017-125">**mv**</span><span class="sxs-lookup"><span data-stu-id="0a017-125">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="0a017-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="0a017-126">**popd**</span></span>                              | <span data-ttu-id="0a017-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="0a017-127">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="0a017-128">**pushd**</span><span class="sxs-lookup"><span data-stu-id="0a017-128">**pushd**</span></span>                             | <span data-ttu-id="0a017-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="0a017-129">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="0a017-130">**ren**</span><span class="sxs-lookup"><span data-stu-id="0a017-130">**ren**</span></span>                               | <span data-ttu-id="0a017-131">**mv**</span><span class="sxs-lookup"><span data-stu-id="0a017-131">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="0a017-132">**type**</span><span class="sxs-lookup"><span data-stu-id="0a017-132">**type**</span></span>                              | <span data-ttu-id="0a017-133">**cat**</span><span class="sxs-lookup"><span data-stu-id="0a017-133">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="0a017-134">Чтобы найти псевдонимы PowerShell, используйте командлет [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias).</span><span class="sxs-lookup"><span data-stu-id="0a017-134">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="0a017-135">Чтобы отобразить псевдонимы командлета, используйте параметр **Definition** и укажите имя командлета.</span><span class="sxs-lookup"><span data-stu-id="0a017-135">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="0a017-136">Чтобы найти имя командлета псевдонима, используйте параметр **Name** и укажите псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0a017-136">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
