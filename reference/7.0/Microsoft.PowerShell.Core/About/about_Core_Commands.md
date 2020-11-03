---
description: Список командлетов, предназначенных для использования с поставщиками PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 5c784518ae30108813d32497f654198e7d10b379
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231030"
---
# <a name="about-core-commands"></a><span data-ttu-id="aef41-104">Основные команды</span><span class="sxs-lookup"><span data-stu-id="aef41-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="aef41-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="aef41-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="aef41-106">Список командлетов, предназначенных для использования с поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aef41-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="aef41-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="aef41-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="aef41-108">PowerShell включает набор командлетов, специально предназначенных для управления элементами в хранилищах данных, предоставляемых поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aef41-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="aef41-109">Эти командлеты можно использовать для управления всеми типами данных, которые поставщики делают доступными.</span><span class="sxs-lookup"><span data-stu-id="aef41-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="aef41-110">Для получения дополнительных сведений о поставщиках введите «Get-Help about_providers».</span><span class="sxs-lookup"><span data-stu-id="aef41-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="aef41-111">Например, с помощью командлета Get-ChildItem можно вывести список файлов в каталоге файловой системы, ключи в разделе реестра или элементы, предоставляемые поставщиком, который вы создаете или скачиваете.</span><span class="sxs-lookup"><span data-stu-id="aef41-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="aef41-112">Ниже приведен список командлетов PowerShell, предназначенных для использования с поставщиками.</span><span class="sxs-lookup"><span data-stu-id="aef41-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="aef41-113">Командлеты ChildItem</span><span class="sxs-lookup"><span data-stu-id="aef41-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="aef41-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="aef41-114">Get-ChildItem</span></span>

<span data-ttu-id="aef41-115">Командлеты содержимого</span><span class="sxs-lookup"><span data-stu-id="aef41-115">Content cmdlets</span></span>

- <span data-ttu-id="aef41-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="aef41-116">Add-Content</span></span>
- <span data-ttu-id="aef41-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="aef41-117">Clear-Content</span></span>
- <span data-ttu-id="aef41-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="aef41-118">Get-Content</span></span>
- <span data-ttu-id="aef41-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="aef41-119">Set-Content</span></span>

<span data-ttu-id="aef41-120">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="aef41-120">Item cmdlets</span></span>

- <span data-ttu-id="aef41-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-121">Clear-Item</span></span>
- <span data-ttu-id="aef41-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-122">Copy-Item</span></span>
- <span data-ttu-id="aef41-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-123">Get-Item</span></span>
- <span data-ttu-id="aef41-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-124">Invoke-Item</span></span>
- <span data-ttu-id="aef41-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-125">Move-Item</span></span>
- <span data-ttu-id="aef41-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-126">New-Item</span></span>
- <span data-ttu-id="aef41-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-127">Remove-Item</span></span>
- <span data-ttu-id="aef41-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-128">Rename-Item</span></span>
- <span data-ttu-id="aef41-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="aef41-129">Set-Item</span></span>

<span data-ttu-id="aef41-130">Командлеты ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="aef41-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="aef41-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="aef41-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-133">Get-ItemProperty</span></span>
- <span data-ttu-id="aef41-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-134">Move-ItemProperty</span></span>
- <span data-ttu-id="aef41-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-135">New-ItemProperty</span></span>
- <span data-ttu-id="aef41-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="aef41-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="aef41-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="aef41-138">Set-ItemProperty</span></span>

<span data-ttu-id="aef41-139">Командлеты Location</span><span class="sxs-lookup"><span data-stu-id="aef41-139">Location cmdlets</span></span>

- <span data-ttu-id="aef41-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="aef41-140">Get-Location</span></span>
- <span data-ttu-id="aef41-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="aef41-141">Pop-Location</span></span>
- <span data-ttu-id="aef41-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="aef41-142">Push-Location</span></span>
- <span data-ttu-id="aef41-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="aef41-143">Set-Location</span></span>

<span data-ttu-id="aef41-144">Командлеты пути</span><span class="sxs-lookup"><span data-stu-id="aef41-144">Path cmdlets</span></span>

- <span data-ttu-id="aef41-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="aef41-145">Join-Path</span></span>
- <span data-ttu-id="aef41-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="aef41-146">Convert-Path</span></span>
- <span data-ttu-id="aef41-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="aef41-147">Split-Path</span></span>
- <span data-ttu-id="aef41-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="aef41-148">Resolve-Path</span></span>
- <span data-ttu-id="aef41-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="aef41-149">Test-Path</span></span>

<span data-ttu-id="aef41-150">Командлеты PSDrive</span><span class="sxs-lookup"><span data-stu-id="aef41-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="aef41-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="aef41-151">Get-PSDrive</span></span>
- <span data-ttu-id="aef41-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="aef41-152">New-PSDrive</span></span>
- <span data-ttu-id="aef41-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="aef41-153">Remove-PSDrive</span></span>

<span data-ttu-id="aef41-154">Командлеты PSProvider</span><span class="sxs-lookup"><span data-stu-id="aef41-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="aef41-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="aef41-155">Get-PSProvider</span></span>

<span data-ttu-id="aef41-156">Для получения дополнительных сведений о командлете введите `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="aef41-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="aef41-157">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="aef41-157">SEE ALSO</span></span>

[<span data-ttu-id="aef41-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="aef41-158">about_Providers</span></span>](about_Providers.md)
