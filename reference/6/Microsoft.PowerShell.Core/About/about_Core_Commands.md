---
description: Список командлетов, предназначенных для использования с поставщиками PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: d02067bca8f66c61a66ff121521a49668f32d839
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231522"
---
# <a name="about-core-commands"></a><span data-ttu-id="b9aca-104">Основные команды</span><span class="sxs-lookup"><span data-stu-id="b9aca-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="b9aca-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b9aca-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="b9aca-106">Список командлетов, предназначенных для использования с поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9aca-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="b9aca-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b9aca-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b9aca-108">PowerShell включает набор командлетов, специально предназначенных для управления элементами в хранилищах данных, предоставляемых поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9aca-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="b9aca-109">Эти командлеты можно использовать для управления всеми типами данных, которые поставщики делают доступными.</span><span class="sxs-lookup"><span data-stu-id="b9aca-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="b9aca-110">Для получения дополнительных сведений о поставщиках введите «Get-Help about_providers».</span><span class="sxs-lookup"><span data-stu-id="b9aca-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="b9aca-111">Например, с помощью командлета Get-ChildItem можно вывести список файлов в каталоге файловой системы, ключи в разделе реестра или элементы, предоставляемые поставщиком, который вы создаете или скачиваете.</span><span class="sxs-lookup"><span data-stu-id="b9aca-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="b9aca-112">Ниже приведен список командлетов PowerShell, предназначенных для использования с поставщиками.</span><span class="sxs-lookup"><span data-stu-id="b9aca-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="b9aca-113">Командлеты ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9aca-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="b9aca-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9aca-114">Get-ChildItem</span></span>

<span data-ttu-id="b9aca-115">Командлеты содержимого</span><span class="sxs-lookup"><span data-stu-id="b9aca-115">Content cmdlets</span></span>

- <span data-ttu-id="b9aca-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b9aca-116">Add-Content</span></span>
- <span data-ttu-id="b9aca-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="b9aca-117">Clear-Content</span></span>
- <span data-ttu-id="b9aca-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9aca-118">Get-Content</span></span>
- <span data-ttu-id="b9aca-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b9aca-119">Set-Content</span></span>

<span data-ttu-id="b9aca-120">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="b9aca-120">Item cmdlets</span></span>

- <span data-ttu-id="b9aca-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-121">Clear-Item</span></span>
- <span data-ttu-id="b9aca-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-122">Copy-Item</span></span>
- <span data-ttu-id="b9aca-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-123">Get-Item</span></span>
- <span data-ttu-id="b9aca-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-124">Invoke-Item</span></span>
- <span data-ttu-id="b9aca-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-125">Move-Item</span></span>
- <span data-ttu-id="b9aca-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-126">New-Item</span></span>
- <span data-ttu-id="b9aca-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-127">Remove-Item</span></span>
- <span data-ttu-id="b9aca-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-128">Rename-Item</span></span>
- <span data-ttu-id="b9aca-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="b9aca-129">Set-Item</span></span>

<span data-ttu-id="b9aca-130">Командлеты ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="b9aca-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="b9aca-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="b9aca-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-133">Get-ItemProperty</span></span>
- <span data-ttu-id="b9aca-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-134">Move-ItemProperty</span></span>
- <span data-ttu-id="b9aca-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-135">New-ItemProperty</span></span>
- <span data-ttu-id="b9aca-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="b9aca-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="b9aca-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9aca-138">Set-ItemProperty</span></span>

<span data-ttu-id="b9aca-139">Командлеты Location</span><span class="sxs-lookup"><span data-stu-id="b9aca-139">Location cmdlets</span></span>

- <span data-ttu-id="b9aca-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b9aca-140">Get-Location</span></span>
- <span data-ttu-id="b9aca-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b9aca-141">Pop-Location</span></span>
- <span data-ttu-id="b9aca-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b9aca-142">Push-Location</span></span>
- <span data-ttu-id="b9aca-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b9aca-143">Set-Location</span></span>

<span data-ttu-id="b9aca-144">Командлеты пути</span><span class="sxs-lookup"><span data-stu-id="b9aca-144">Path cmdlets</span></span>

- <span data-ttu-id="b9aca-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="b9aca-145">Join-Path</span></span>
- <span data-ttu-id="b9aca-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="b9aca-146">Convert-Path</span></span>
- <span data-ttu-id="b9aca-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="b9aca-147">Split-Path</span></span>
- <span data-ttu-id="b9aca-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="b9aca-148">Resolve-Path</span></span>
- <span data-ttu-id="b9aca-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b9aca-149">Test-Path</span></span>

<span data-ttu-id="b9aca-150">Командлеты PSDrive</span><span class="sxs-lookup"><span data-stu-id="b9aca-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="b9aca-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b9aca-151">Get-PSDrive</span></span>
- <span data-ttu-id="b9aca-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b9aca-152">New-PSDrive</span></span>
- <span data-ttu-id="b9aca-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b9aca-153">Remove-PSDrive</span></span>

<span data-ttu-id="b9aca-154">Командлеты PSProvider</span><span class="sxs-lookup"><span data-stu-id="b9aca-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="b9aca-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b9aca-155">Get-PSProvider</span></span>

<span data-ttu-id="b9aca-156">Для получения дополнительных сведений о командлете введите `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="b9aca-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9aca-157">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="b9aca-157">SEE ALSO</span></span>

[<span data-ttu-id="b9aca-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b9aca-158">about_Providers</span></span>](about_Providers.md)
