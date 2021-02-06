---
description: Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке. Данные представлены в единообразном формате, который напоминает диск файловой системы.
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 6073ef13a6d0a02cded69073d7ffaef903a807ea
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601484"
---
# <a name="about-providers"></a><span data-ttu-id="0a529-104">О поставщиках</span><span class="sxs-lookup"><span data-stu-id="0a529-104">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="0a529-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="0a529-105">Short description</span></span>
<span data-ttu-id="0a529-106">Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0a529-106">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="0a529-107">Данные представлены в единообразном формате, который напоминает диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="0a529-107">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="0a529-108">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0a529-108">Long description</span></span>

<span data-ttu-id="0a529-109">Поставщики PowerShell — это программы .NET, обеспечивающие доступ к специализированным хранилищам данных для упрощения просмотра и управления.</span><span class="sxs-lookup"><span data-stu-id="0a529-109">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="0a529-110">Данные отображаются на диске, а доступ к данным осуществляется по пути, как и на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="0a529-110">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="0a529-111">Для управления данными на диске поставщика можно использовать любой из встроенных командлетов, поддерживаемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0a529-111">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="0a529-112">И можно использовать пользовательские командлеты, разработанные специально для данных.</span><span class="sxs-lookup"><span data-stu-id="0a529-112">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="0a529-113">Поставщики также могут добавлять динамические параметры во встроенные командлеты.</span><span class="sxs-lookup"><span data-stu-id="0a529-113">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="0a529-114">Эти параметры доступны только при использовании командлета с данными поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a529-114">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="0a529-115">Встроенные поставщики</span><span class="sxs-lookup"><span data-stu-id="0a529-115">Built-in providers</span></span>

<span data-ttu-id="0a529-116">В PowerShell имеется набор встроенных поставщиков, которые можно использовать для доступа к различным типам хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="0a529-116">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="0a529-117">Поставщик</span><span class="sxs-lookup"><span data-stu-id="0a529-117">Provider</span></span>   |   <span data-ttu-id="0a529-118">Диск (ы)</span><span class="sxs-lookup"><span data-stu-id="0a529-118">Drive(s)</span></span>  |<span data-ttu-id="0a529-119">OutputType</span><span class="sxs-lookup"><span data-stu-id="0a529-119">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="0a529-120">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="0a529-120">Alias</span></span>       |<span data-ttu-id="0a529-121">Alias:</span><span class="sxs-lookup"><span data-stu-id="0a529-121">Alias:</span></span>       |<span data-ttu-id="0a529-122">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="0a529-122">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="0a529-123">Certificate</span><span class="sxs-lookup"><span data-stu-id="0a529-123">Certificate</span></span> |<span data-ttu-id="0a529-124">Cert:</span><span class="sxs-lookup"><span data-stu-id="0a529-124">Cert:</span></span>        |<span data-ttu-id="0a529-125">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="0a529-125">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="0a529-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="0a529-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="0a529-127">Среда</span><span class="sxs-lookup"><span data-stu-id="0a529-127">Environment</span></span> |<span data-ttu-id="0a529-128">Env:</span><span class="sxs-lookup"><span data-stu-id="0a529-128">Env:</span></span>         |<span data-ttu-id="0a529-129">System. Collections. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="0a529-129">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="0a529-130">FileSystem</span><span class="sxs-lookup"><span data-stu-id="0a529-130">FileSystem</span></span>  |<span data-ttu-id="0a529-131">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="0a529-131">C: (\*)</span></span>       |<span data-ttu-id="0a529-132">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="0a529-132">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="0a529-133">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="0a529-133">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="0a529-134">Компонент</span><span class="sxs-lookup"><span data-stu-id="0a529-134">Function</span></span>    |<span data-ttu-id="0a529-135">Функция:</span><span class="sxs-lookup"><span data-stu-id="0a529-135">Function:</span></span>    |<span data-ttu-id="0a529-136">System.Management.Automation.FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="0a529-136">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="0a529-137">Реестр</span><span class="sxs-lookup"><span data-stu-id="0a529-137">Registry</span></span>    |<span data-ttu-id="0a529-138">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="0a529-138">HKLM: HKCU:</span></span>  |<span data-ttu-id="0a529-139">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="0a529-139">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="0a529-140">Переменная</span><span class="sxs-lookup"><span data-stu-id="0a529-140">Variable</span></span>    |<span data-ttu-id="0a529-141">Variable:</span><span class="sxs-lookup"><span data-stu-id="0a529-141">Variable:</span></span>    |<span data-ttu-id="0a529-142">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="0a529-142">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="0a529-143">WSMan</span><span class="sxs-lookup"><span data-stu-id="0a529-143">WSMan</span></span>       |<span data-ttu-id="0a529-144">WSMan:</span><span class="sxs-lookup"><span data-stu-id="0a529-144">WSMan:</span></span>       |<span data-ttu-id="0a529-145">Microsoft.WSMan.Management.WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="0a529-145">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="0a529-146">(\*) Диски файловой системы различаются в каждой системе.</span><span class="sxs-lookup"><span data-stu-id="0a529-146">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="0a529-147">Вы также можете создавать собственные поставщики PowerShell, а также устанавливать поставщиков, разрабатываемых другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="0a529-147">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="0a529-148">Чтобы получить список поставщиков, доступных в вашем сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-148">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="0a529-149">Установка и удаление поставщиков</span><span class="sxs-lookup"><span data-stu-id="0a529-149">Installing and removing providers</span></span>

<span data-ttu-id="0a529-150">Поставщики обычно устанавливаются с помощью модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a529-150">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="0a529-151">При импорте модуля в сеанс загружается поставщик.</span><span class="sxs-lookup"><span data-stu-id="0a529-151">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="0a529-152">Невозможно удалить встроенные поставщики.</span><span class="sxs-lookup"><span data-stu-id="0a529-152">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="0a529-153">Можно удалить поставщиков, загруженных другими модулями.</span><span class="sxs-lookup"><span data-stu-id="0a529-153">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="0a529-154">Вы можете выгрузить поставщик из текущего сеанса с помощью `Remove-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="0a529-154">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="0a529-155">Этот командлет не удаляет поставщик, но делает его недоступным в сеансе.</span><span class="sxs-lookup"><span data-stu-id="0a529-155">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="0a529-156">Кроме того, с помощью `Remove-PSDrive` командлета можно удалить все диски из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="0a529-156">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="0a529-157">Эти данные на диске не затрагиваются, но диск больше не доступен в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="0a529-157">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="0a529-158">Просмотр поставщиков</span><span class="sxs-lookup"><span data-stu-id="0a529-158">Viewing providers</span></span>

<span data-ttu-id="0a529-159">Чтобы просмотреть поставщиков PowerShell на компьютере, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-159">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="0a529-160">В выходных данных перечислены встроенные поставщики и поставщики, добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="0a529-160">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="0a529-161">Командлеты поставщика</span><span class="sxs-lookup"><span data-stu-id="0a529-161">The provider cmdlets</span></span>

<span data-ttu-id="0a529-162">Следующие командлеты предназначены для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0a529-162">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0a529-163">Те же командлеты можно использовать так же, как и для управления различными типами данных, предоставляемыми поставщиками.</span><span class="sxs-lookup"><span data-stu-id="0a529-163">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="0a529-164">После того как вы научитесь управлять данными одного поставщика, вы можете использовать те же процедуры с данными от любого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a529-164">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="0a529-165">Например, `New-Item` командлет создает новый элемент.</span><span class="sxs-lookup"><span data-stu-id="0a529-165">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="0a529-166">На `C:` диске, поддерживаемом поставщиком **FileSystem** , можно использовать `New-Item` для создания нового файла или папки.</span><span class="sxs-lookup"><span data-stu-id="0a529-166">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="0a529-167">На дисках, которые поддерживаются поставщиком **реестра** , можно использовать `New-Item` для создания нового раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="0a529-167">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="0a529-168">На `Alias:` диске можно использовать `New-Item` для создания нового псевдонима.</span><span class="sxs-lookup"><span data-stu-id="0a529-168">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="0a529-169">Для получения подробных сведений о любом из следующих командлетов введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-169">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="0a529-170">Командлеты ChildItem</span><span class="sxs-lookup"><span data-stu-id="0a529-170">ChildItem cmdlets</span></span>

- [<span data-ttu-id="0a529-171">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0a529-171">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="0a529-172">Командлеты содержимого</span><span class="sxs-lookup"><span data-stu-id="0a529-172">Content Cmdlets</span></span>

- [<span data-ttu-id="0a529-173">Add-Content</span><span class="sxs-lookup"><span data-stu-id="0a529-173">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="0a529-174">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="0a529-174">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="0a529-175">Get-Content</span><span class="sxs-lookup"><span data-stu-id="0a529-175">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="0a529-176">Set-Content</span><span class="sxs-lookup"><span data-stu-id="0a529-176">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="0a529-177">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="0a529-177">Item Cmdlets</span></span>

- [<span data-ttu-id="0a529-178">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-178">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="0a529-179">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-179">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="0a529-180">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-180">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="0a529-181">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-181">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="0a529-182">Move-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-182">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="0a529-183">New-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-183">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="0a529-184">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-184">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="0a529-185">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-185">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="0a529-186">Set-Item</span><span class="sxs-lookup"><span data-stu-id="0a529-186">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="0a529-187">Командлеты ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-187">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="0a529-188">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-188">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="0a529-189">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-189">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="0a529-190">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-190">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="0a529-191">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-191">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="0a529-192">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-192">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="0a529-193">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-193">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="0a529-194">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-194">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="0a529-195">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a529-195">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="0a529-196">Командлеты Location</span><span class="sxs-lookup"><span data-stu-id="0a529-196">Location cmdlets</span></span>

- [<span data-ttu-id="0a529-197">Get-Location</span><span class="sxs-lookup"><span data-stu-id="0a529-197">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="0a529-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="0a529-198">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="0a529-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="0a529-199">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="0a529-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0a529-200">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="0a529-201">Командлеты пути</span><span class="sxs-lookup"><span data-stu-id="0a529-201">Path cmdlets</span></span>

- [<span data-ttu-id="0a529-202">Join-Path</span><span class="sxs-lookup"><span data-stu-id="0a529-202">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="0a529-203">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="0a529-203">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="0a529-204">Split-Path</span><span class="sxs-lookup"><span data-stu-id="0a529-204">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="0a529-205">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="0a529-205">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="0a529-206">Test-Path</span><span class="sxs-lookup"><span data-stu-id="0a529-206">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="0a529-207">Командлеты PSDrive</span><span class="sxs-lookup"><span data-stu-id="0a529-207">PSDrive cmdlets</span></span>

- [<span data-ttu-id="0a529-208">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0a529-208">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="0a529-209">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0a529-209">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="0a529-210">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0a529-210">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="0a529-211">Командлеты PSProvider</span><span class="sxs-lookup"><span data-stu-id="0a529-211">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="0a529-212">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="0a529-212">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="0a529-213">Просмотр данных поставщика</span><span class="sxs-lookup"><span data-stu-id="0a529-213">Viewing provider data</span></span>

<span data-ttu-id="0a529-214">Основное преимущество поставщика заключается в том, что он предоставляет свои данные привычным и согласованным способом.</span><span class="sxs-lookup"><span data-stu-id="0a529-214">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="0a529-215">Модель представления данных — это диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="0a529-215">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="0a529-216">Поставщик позволяет просматривать, перемещать и изменять элементы в хранилище данных, как будто они являются данными в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="0a529-216">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="0a529-217">Доступ к хранилищу данных осуществляется по имени диска, который он поддерживает.</span><span class="sxs-lookup"><span data-stu-id="0a529-217">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="0a529-218">Диск отображается в списке по умолчанию для `Get-PSProvider` командлета, но сведения о диске поставщика можно получить с помощью `Get-PSDrive` командлета.</span><span class="sxs-lookup"><span data-stu-id="0a529-218">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="0a529-219">Например, чтобы получить все свойства диска Function:, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-219">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="0a529-220">Данные можно просматривать и перемещать по данным на диске поставщика точно так же, как и на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="0a529-220">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="0a529-221">Чтобы просмотреть содержимое диска поставщика, используйте командлеты Get-Item или Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="0a529-221">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="0a529-222">Введите имя диска, за которым следует двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="0a529-222">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="0a529-223">Например, чтобы просмотреть содержимое диска Alias:, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-223">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="0a529-224">Вы можете просматривать данные и управлять ими на любом диске с другого диска, включив имя диска в путь.</span><span class="sxs-lookup"><span data-stu-id="0a529-224">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="0a529-225">Например, чтобы просмотреть раздел реестра HKLM\Software на диске HKLM: с другого диска, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-225">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="0a529-226">Чтобы открыть диск, используйте командлет Set-Location.</span><span class="sxs-lookup"><span data-stu-id="0a529-226">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="0a529-227">Запомните двоеточие при указании пути к диску.</span><span class="sxs-lookup"><span data-stu-id="0a529-227">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="0a529-228">Например, чтобы изменить расположение на корневой каталог диска Cert:, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-228">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="0a529-229">Затем, чтобы просмотреть содержимое диска Cert:, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-229">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="0a529-230">Перемещение по иерархическим данным</span><span class="sxs-lookup"><span data-stu-id="0a529-230">Moving through hierarchical data</span></span>

<span data-ttu-id="0a529-231">Вы можете перемещаться по диску поставщика так же, как и к жесткому диску.</span><span class="sxs-lookup"><span data-stu-id="0a529-231">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="0a529-232">Если данные упорядочены в иерархии элементов внутри элементов, используйте обратную косую черту ( `\` ), чтобы указать дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="0a529-232">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="0a529-233">Используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="0a529-233">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="0a529-234">Например, чтобы изменить расположение на раздел реестра HKLM\Software, введите команду Set-Location, например:</span><span class="sxs-lookup"><span data-stu-id="0a529-234">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="0a529-235">Если любой элемент в полном имени содержит пробелы, имя необходимо заключить в двойные кавычки ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="0a529-235">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="0a529-236">В следующем примере показан полный путь, содержащий пробелы.</span><span class="sxs-lookup"><span data-stu-id="0a529-236">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="0a529-237">Можно также использовать относительные ссылки на расположения.</span><span class="sxs-lookup"><span data-stu-id="0a529-237">You can also use relative references to locations.</span></span> <span data-ttu-id="0a529-238">Точка ( `.` ) представляет текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="0a529-238">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="0a529-239">Например, если вы используете раздел `HKLM:\Software\Microsoft` реестра и хотите перечислить подразделы реестра в `HKLM:\Software\Microsoft\PowerShell` разделе, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a529-239">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="0a529-240">Кроме того, двойные точки ( `..` ) ссылаются на каталог или контейнер непосредственно над текущим расположением.</span><span class="sxs-lookup"><span data-stu-id="0a529-240">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="0a529-241">Для навигации по иерархии поставщика можно использовать двойные точки ( `..` ).</span><span class="sxs-lookup"><span data-stu-id="0a529-241">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="0a529-242">Домашняя страница поставщика</span><span class="sxs-lookup"><span data-stu-id="0a529-242">Provider Home</span></span>

<span data-ttu-id="0a529-243">Поставщики также имеют **домашнюю** папку.</span><span class="sxs-lookup"><span data-stu-id="0a529-243">Providers also have a **Home** location.</span></span>  <span data-ttu-id="0a529-244">Это расположение является общим для всех, `PSDrives` которое поддерживается поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0a529-244">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="0a529-245">Его можно получить, просмотрев свойство **Home** поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a529-245">It can be retrieved by viewing the **Home** property of the provider.</span></span>

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

<span data-ttu-id="0a529-246">Поставщик **FileSystem** является единственным поставщиком, имеющим значение по умолчанию для **Home**.</span><span class="sxs-lookup"><span data-stu-id="0a529-246">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="0a529-247">Это то же значение, что и `$Home` .</span><span class="sxs-lookup"><span data-stu-id="0a529-247">It's the same value as `$Home`.</span></span> <span data-ttu-id="0a529-248">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0a529-248">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="0a529-249">Можно задать **домашний** каталог для поставщика в текущем сеансе, используя его свойство.</span><span class="sxs-lookup"><span data-stu-id="0a529-249">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="0a529-250">`~`Символ может использоваться для представления домашнего каталога поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a529-250">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="0a529-251">Если у поставщика нет установленного **домашней** папки, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0a529-251">If the provider doesn't have a **Home** location set, you see an error.</span></span>

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="0a529-252">Поиск динамических параметров</span><span class="sxs-lookup"><span data-stu-id="0a529-252">Finding dynamic parameters</span></span>

<span data-ttu-id="0a529-253">Динамические параметры — это параметры командлета, которые добавляются в командлет поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0a529-253">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="0a529-254">Эти параметры доступны только в том случае, если командлет используется с поставщиком, который их добавил.</span><span class="sxs-lookup"><span data-stu-id="0a529-254">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="0a529-255">Например, `Cert:` диск добавляет параметр **CodeSigningCert** в `Get-Item` `Get-ChildItem` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="0a529-255">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="0a529-256">Этот параметр можно использовать только при использовании `Get-Item` или `Get-ChildItem` на `Cert:` диске.</span><span class="sxs-lookup"><span data-stu-id="0a529-256">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="0a529-257">Список динамических параметров, поддерживаемых поставщиком, см. в файле справки для поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a529-257">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="0a529-258">Тип:</span><span class="sxs-lookup"><span data-stu-id="0a529-258">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="0a529-259">Пример:</span><span class="sxs-lookup"><span data-stu-id="0a529-259">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="0a529-260">Изучение поставщиков</span><span class="sxs-lookup"><span data-stu-id="0a529-260">Learning about providers</span></span>

<span data-ttu-id="0a529-261">Несмотря на то что все данные поставщика отображаются в дисках и для их перемещения используются те же методы, подобный процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="0a529-261">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="0a529-262">Хранилище данных, предоставляемое поставщиком, может быть так же разнообразным, как Active Directory расположений и почтовых ящиков Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="0a529-262">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="0a529-263">Для получения сведений об отдельных поставщиках PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-263">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="0a529-264">Пример:</span><span class="sxs-lookup"><span data-stu-id="0a529-264">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="0a529-265">Чтобы получить список разделов справки о поставщиках, введите:</span><span class="sxs-lookup"><span data-stu-id="0a529-265">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="0a529-266">См. также</span><span class="sxs-lookup"><span data-stu-id="0a529-266">See also</span></span>

[<span data-ttu-id="0a529-267">about_Locations</span><span class="sxs-lookup"><span data-stu-id="0a529-267">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="0a529-268">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="0a529-268">about_Path_Syntax</span></span>](about_Path_Syntax.md)

