---
description: Список командлетов, предназначенных для использования с поставщиками PowerShell.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 1f023c5a66265f561ef6644afdc45cd0149f35b7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604597"
---
# <a name="about-core-commands"></a><span data-ttu-id="3ae69-103">Основные команды</span><span class="sxs-lookup"><span data-stu-id="3ae69-103">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="3ae69-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3ae69-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3ae69-105">Список командлетов, предназначенных для использования с поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ae69-105">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="3ae69-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3ae69-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="3ae69-107">PowerShell включает набор командлетов, специально предназначенных для управления элементами в хранилищах данных, предоставляемых поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ae69-107">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="3ae69-108">Эти командлеты можно использовать для управления всеми типами данных, которые поставщики делают доступными.</span><span class="sxs-lookup"><span data-stu-id="3ae69-108">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="3ae69-109">Для получения дополнительных сведений о поставщиках введите «Get-Help about_providers».</span><span class="sxs-lookup"><span data-stu-id="3ae69-109">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="3ae69-110">Например, с помощью командлета Get-ChildItem можно вывести список файлов в каталоге файловой системы, ключи в разделе реестра или элементы, предоставляемые поставщиком, который вы создаете или скачиваете.</span><span class="sxs-lookup"><span data-stu-id="3ae69-110">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="3ae69-111">Ниже приведен список командлетов PowerShell, предназначенных для использования с поставщиками.</span><span class="sxs-lookup"><span data-stu-id="3ae69-111">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="3ae69-112">Командлеты ChildItem</span><span class="sxs-lookup"><span data-stu-id="3ae69-112">ChildItem cmdlets</span></span>

- <span data-ttu-id="3ae69-113">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3ae69-113">Get-ChildItem</span></span>

<span data-ttu-id="3ae69-114">Командлеты содержимого</span><span class="sxs-lookup"><span data-stu-id="3ae69-114">Content cmdlets</span></span>

- <span data-ttu-id="3ae69-115">Add-Content</span><span class="sxs-lookup"><span data-stu-id="3ae69-115">Add-Content</span></span>
- <span data-ttu-id="3ae69-116">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="3ae69-116">Clear-Content</span></span>
- <span data-ttu-id="3ae69-117">Get-Content</span><span class="sxs-lookup"><span data-stu-id="3ae69-117">Get-Content</span></span>
- <span data-ttu-id="3ae69-118">Set-Content</span><span class="sxs-lookup"><span data-stu-id="3ae69-118">Set-Content</span></span>

<span data-ttu-id="3ae69-119">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="3ae69-119">Item cmdlets</span></span>

- <span data-ttu-id="3ae69-120">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-120">Clear-Item</span></span>
- <span data-ttu-id="3ae69-121">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-121">Copy-Item</span></span>
- <span data-ttu-id="3ae69-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-122">Get-Item</span></span>
- <span data-ttu-id="3ae69-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-123">Invoke-Item</span></span>
- <span data-ttu-id="3ae69-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-124">Move-Item</span></span>
- <span data-ttu-id="3ae69-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-125">New-Item</span></span>
- <span data-ttu-id="3ae69-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-126">Remove-Item</span></span>
- <span data-ttu-id="3ae69-127">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-127">Rename-Item</span></span>
- <span data-ttu-id="3ae69-128">Set-Item</span><span class="sxs-lookup"><span data-stu-id="3ae69-128">Set-Item</span></span>

<span data-ttu-id="3ae69-129">Командлеты ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-129">ItemProperty cmdlets</span></span>

- <span data-ttu-id="3ae69-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-130">Clear-ItemProperty</span></span>
- <span data-ttu-id="3ae69-131">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-131">Copy-ItemProperty</span></span>
- <span data-ttu-id="3ae69-132">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-132">Get-ItemProperty</span></span>
- <span data-ttu-id="3ae69-133">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-133">Move-ItemProperty</span></span>
- <span data-ttu-id="3ae69-134">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-134">New-ItemProperty</span></span>
- <span data-ttu-id="3ae69-135">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-135">Remove-ItemProperty</span></span>
- <span data-ttu-id="3ae69-136">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-136">Rename-ItemProperty</span></span>
- <span data-ttu-id="3ae69-137">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3ae69-137">Set-ItemProperty</span></span>

<span data-ttu-id="3ae69-138">Командлеты Location</span><span class="sxs-lookup"><span data-stu-id="3ae69-138">Location cmdlets</span></span>

- <span data-ttu-id="3ae69-139">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3ae69-139">Get-Location</span></span>
- <span data-ttu-id="3ae69-140">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="3ae69-140">Pop-Location</span></span>
- <span data-ttu-id="3ae69-141">Push-Location</span><span class="sxs-lookup"><span data-stu-id="3ae69-141">Push-Location</span></span>
- <span data-ttu-id="3ae69-142">Set-Location</span><span class="sxs-lookup"><span data-stu-id="3ae69-142">Set-Location</span></span>

<span data-ttu-id="3ae69-143">Командлеты пути</span><span class="sxs-lookup"><span data-stu-id="3ae69-143">Path cmdlets</span></span>

- <span data-ttu-id="3ae69-144">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3ae69-144">Join-Path</span></span>
- <span data-ttu-id="3ae69-145">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="3ae69-145">Convert-Path</span></span>
- <span data-ttu-id="3ae69-146">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3ae69-146">Split-Path</span></span>
- <span data-ttu-id="3ae69-147">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="3ae69-147">Resolve-Path</span></span>
- <span data-ttu-id="3ae69-148">Test-Path</span><span class="sxs-lookup"><span data-stu-id="3ae69-148">Test-Path</span></span>

<span data-ttu-id="3ae69-149">Командлеты PSDrive</span><span class="sxs-lookup"><span data-stu-id="3ae69-149">PSDrive cmdlets</span></span>

- <span data-ttu-id="3ae69-150">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="3ae69-150">Get-PSDrive</span></span>
- <span data-ttu-id="3ae69-151">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="3ae69-151">New-PSDrive</span></span>
- <span data-ttu-id="3ae69-152">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="3ae69-152">Remove-PSDrive</span></span>

<span data-ttu-id="3ae69-153">Командлеты PSProvider</span><span class="sxs-lookup"><span data-stu-id="3ae69-153">PSProvider cmdlets</span></span>

- <span data-ttu-id="3ae69-154">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3ae69-154">Get-PSProvider</span></span>

<span data-ttu-id="3ae69-155">Для получения дополнительных сведений о командлете введите `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="3ae69-155">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ae69-156">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="3ae69-156">SEE ALSO</span></span>

[<span data-ttu-id="3ae69-157">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3ae69-157">about_Providers</span></span>](about_Providers.md)

