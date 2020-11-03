---
description: Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке. Данные представлены в единообразном формате, который напоминает диск файловой системы.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: cbafcab2b24e77a43d7b628ce9500f480ed9b5b8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231333"
---
# <a name="about-providers"></a><span data-ttu-id="1f2aa-105">О поставщиках</span><span class="sxs-lookup"><span data-stu-id="1f2aa-105">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="1f2aa-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="1f2aa-106">Short description</span></span>
<span data-ttu-id="1f2aa-107">Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-107">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="1f2aa-108">Данные представлены в единообразном формате, который напоминает диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-108">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="1f2aa-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="1f2aa-109">Long description</span></span>

<span data-ttu-id="1f2aa-110">Поставщики PowerShell — это программы .NET, обеспечивающие доступ к специализированным хранилищам данных для упрощения просмотра и управления.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-110">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="1f2aa-111">Данные отображаются на диске, а доступ к данным осуществляется по пути, как и на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-111">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="1f2aa-112">Для управления данными на диске поставщика можно использовать любой из встроенных командлетов, поддерживаемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-112">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="1f2aa-113">И можно использовать пользовательские командлеты, разработанные специально для данных.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-113">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="1f2aa-114">Поставщики также могут добавлять динамические параметры во встроенные командлеты.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-114">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="1f2aa-115">Эти параметры доступны только при использовании командлета с данными поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-115">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="1f2aa-116">Встроенные поставщики</span><span class="sxs-lookup"><span data-stu-id="1f2aa-116">Built-in providers</span></span>

<span data-ttu-id="1f2aa-117">В PowerShell имеется набор встроенных поставщиков, которые можно использовать для доступа к различным типам хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-117">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="1f2aa-118">Поставщик</span><span class="sxs-lookup"><span data-stu-id="1f2aa-118">Provider</span></span>   |   <span data-ttu-id="1f2aa-119">Диск (ы)</span><span class="sxs-lookup"><span data-stu-id="1f2aa-119">Drive(s)</span></span>  |<span data-ttu-id="1f2aa-120">OutputType</span><span class="sxs-lookup"><span data-stu-id="1f2aa-120">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="1f2aa-121">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="1f2aa-121">Alias</span></span>       |<span data-ttu-id="1f2aa-122">Alias:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-122">Alias:</span></span>       |<span data-ttu-id="1f2aa-123">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="1f2aa-123">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="1f2aa-124">Сертификат</span><span class="sxs-lookup"><span data-stu-id="1f2aa-124">Certificate</span></span> |<span data-ttu-id="1f2aa-125">Cert:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-125">Cert:</span></span>        |<span data-ttu-id="1f2aa-126">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="1f2aa-126">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="1f2aa-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="1f2aa-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="1f2aa-128">Среда</span><span class="sxs-lookup"><span data-stu-id="1f2aa-128">Environment</span></span> |<span data-ttu-id="1f2aa-129">Env:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-129">Env:</span></span>         |<span data-ttu-id="1f2aa-130">System. Collections. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="1f2aa-130">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="1f2aa-131">FileSystem</span><span class="sxs-lookup"><span data-stu-id="1f2aa-131">FileSystem</span></span>  |<span data-ttu-id="1f2aa-132">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="1f2aa-132">C: (\*)</span></span>       |<span data-ttu-id="1f2aa-133">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="1f2aa-133">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="1f2aa-134">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="1f2aa-134">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="1f2aa-135">Компонент</span><span class="sxs-lookup"><span data-stu-id="1f2aa-135">Function</span></span>    |<span data-ttu-id="1f2aa-136">Функция:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-136">Function:</span></span>    |<span data-ttu-id="1f2aa-137">System.Management.Automation.FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="1f2aa-137">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="1f2aa-138">Реестр</span><span class="sxs-lookup"><span data-stu-id="1f2aa-138">Registry</span></span>    |<span data-ttu-id="1f2aa-139">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-139">HKLM: HKCU:</span></span>  |<span data-ttu-id="1f2aa-140">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="1f2aa-140">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="1f2aa-141">Переменная</span><span class="sxs-lookup"><span data-stu-id="1f2aa-141">Variable</span></span>    |<span data-ttu-id="1f2aa-142">Variable:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-142">Variable:</span></span>    |<span data-ttu-id="1f2aa-143">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="1f2aa-143">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="1f2aa-144">WSMan</span><span class="sxs-lookup"><span data-stu-id="1f2aa-144">WSMan</span></span>       |<span data-ttu-id="1f2aa-145">WSMan:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-145">WSMan:</span></span>       |<span data-ttu-id="1f2aa-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="1f2aa-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="1f2aa-147">(\*) Диски файловой системы различаются в каждой системе.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-147">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="1f2aa-148">Вы также можете создавать собственные поставщики PowerShell, а также устанавливать поставщиков, разрабатываемых другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-148">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="1f2aa-149">Чтобы получить список поставщиков, доступных в вашем сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-149">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="1f2aa-150">Установка и удаление поставщиков</span><span class="sxs-lookup"><span data-stu-id="1f2aa-150">Installing and removing providers</span></span>

<span data-ttu-id="1f2aa-151">Поставщики обычно устанавливаются с помощью модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-151">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="1f2aa-152">При импорте модуля в сеанс загружается поставщик.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-152">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="1f2aa-153">Невозможно удалить встроенные поставщики.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-153">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="1f2aa-154">Можно удалить поставщиков, загруженных другими модулями.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-154">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="1f2aa-155">Вы можете выгрузить поставщик из текущего сеанса с помощью `Remove-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-155">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="1f2aa-156">Этот командлет не удаляет поставщик, но делает его недоступным в сеансе.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-156">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="1f2aa-157">Кроме того, с помощью `Remove-PSDrive` командлета можно удалить все диски из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-157">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="1f2aa-158">Эти данные на диске не затрагиваются, но диск больше не доступен в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-158">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="1f2aa-159">Просмотр поставщиков</span><span class="sxs-lookup"><span data-stu-id="1f2aa-159">Viewing providers</span></span>

<span data-ttu-id="1f2aa-160">Чтобы просмотреть поставщиков PowerShell на компьютере, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-160">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="1f2aa-161">В выходных данных перечислены встроенные поставщики и поставщики, добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-161">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="1f2aa-162">Командлеты поставщика</span><span class="sxs-lookup"><span data-stu-id="1f2aa-162">The provider cmdlets</span></span>

<span data-ttu-id="1f2aa-163">Следующие командлеты предназначены для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-163">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1f2aa-164">Те же командлеты можно использовать так же, как и для управления различными типами данных, предоставляемыми поставщиками.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-164">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="1f2aa-165">После того как вы научитесь управлять данными одного поставщика, вы можете использовать те же процедуры с данными от любого поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-165">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="1f2aa-166">Например, `New-Item` командлет создает новый элемент.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-166">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="1f2aa-167">На `C:` диске, поддерживаемом поставщиком **FileSystem** , можно использовать `New-Item` для создания нового файла или папки.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-167">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="1f2aa-168">На дисках, которые поддерживаются поставщиком **реестра** , можно использовать `New-Item` для создания нового раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-168">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="1f2aa-169">На `Alias:` диске можно использовать `New-Item` для создания нового псевдонима.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-169">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="1f2aa-170">Для получения подробных сведений о любом из следующих командлетов введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-170">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="1f2aa-171">Командлеты ChildItem</span><span class="sxs-lookup"><span data-stu-id="1f2aa-171">ChildItem cmdlets</span></span>

- [<span data-ttu-id="1f2aa-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1f2aa-172">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="1f2aa-173">Командлеты содержимого</span><span class="sxs-lookup"><span data-stu-id="1f2aa-173">Content Cmdlets</span></span>

- [<span data-ttu-id="1f2aa-174">Add-Content</span><span class="sxs-lookup"><span data-stu-id="1f2aa-174">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="1f2aa-175">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="1f2aa-175">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="1f2aa-176">Get-Content</span><span class="sxs-lookup"><span data-stu-id="1f2aa-176">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="1f2aa-177">Set-Content</span><span class="sxs-lookup"><span data-stu-id="1f2aa-177">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="1f2aa-178">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="1f2aa-178">Item Cmdlets</span></span>

- [<span data-ttu-id="1f2aa-179">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-179">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="1f2aa-180">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-180">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="1f2aa-181">Get-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-181">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="1f2aa-182">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-182">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="1f2aa-183">Move-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-183">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="1f2aa-184">New-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-184">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="1f2aa-185">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-185">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="1f2aa-186">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-186">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="1f2aa-187">Set-Item</span><span class="sxs-lookup"><span data-stu-id="1f2aa-187">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="1f2aa-188">Командлеты ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-188">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="1f2aa-189">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-189">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="1f2aa-190">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-190">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="1f2aa-191">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-191">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="1f2aa-192">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-192">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="1f2aa-193">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-193">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="1f2aa-194">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-194">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="1f2aa-195">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-195">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="1f2aa-196">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f2aa-196">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="1f2aa-197">Командлеты Location</span><span class="sxs-lookup"><span data-stu-id="1f2aa-197">Location cmdlets</span></span>

- [<span data-ttu-id="1f2aa-198">Get-Location</span><span class="sxs-lookup"><span data-stu-id="1f2aa-198">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="1f2aa-199">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="1f2aa-199">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="1f2aa-200">Push-Location</span><span class="sxs-lookup"><span data-stu-id="1f2aa-200">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="1f2aa-201">Set-Location</span><span class="sxs-lookup"><span data-stu-id="1f2aa-201">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="1f2aa-202">Командлеты пути</span><span class="sxs-lookup"><span data-stu-id="1f2aa-202">Path cmdlets</span></span>

- [<span data-ttu-id="1f2aa-203">Join-Path</span><span class="sxs-lookup"><span data-stu-id="1f2aa-203">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="1f2aa-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="1f2aa-204">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="1f2aa-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="1f2aa-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="1f2aa-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="1f2aa-206">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="1f2aa-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="1f2aa-207">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="1f2aa-208">Командлеты PSDrive</span><span class="sxs-lookup"><span data-stu-id="1f2aa-208">PSDrive cmdlets</span></span>

- [<span data-ttu-id="1f2aa-209">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1f2aa-209">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="1f2aa-210">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1f2aa-210">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="1f2aa-211">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1f2aa-211">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="1f2aa-212">Командлеты PSProvider</span><span class="sxs-lookup"><span data-stu-id="1f2aa-212">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="1f2aa-213">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="1f2aa-213">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="1f2aa-214">Просмотр данных поставщика</span><span class="sxs-lookup"><span data-stu-id="1f2aa-214">Viewing provider data</span></span>

<span data-ttu-id="1f2aa-215">Основное преимущество поставщика заключается в том, что он предоставляет свои данные привычным и согласованным способом.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-215">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="1f2aa-216">Модель представления данных — это диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-216">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="1f2aa-217">Поставщик позволяет просматривать, перемещать и изменять элементы в хранилище данных, как будто они являются данными в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-217">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="1f2aa-218">Доступ к хранилищу данных осуществляется по имени диска, который он поддерживает.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-218">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="1f2aa-219">Диск отображается в списке по умолчанию для `Get-PSProvider` командлета, но сведения о диске поставщика можно получить с помощью `Get-PSDrive` командлета.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-219">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="1f2aa-220">Например, чтобы получить все свойства диска Function:, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-220">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="1f2aa-221">Данные можно просматривать и перемещать по данным на диске поставщика точно так же, как и на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-221">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="1f2aa-222">Чтобы просмотреть содержимое диска поставщика, используйте командлеты Get-Item или Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-222">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="1f2aa-223">Введите имя диска, за которым следует двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="1f2aa-223">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="1f2aa-224">Например, чтобы просмотреть содержимое диска Alias:, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-224">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="1f2aa-225">Вы можете просматривать данные и управлять ими на любом диске с другого диска, включив имя диска в путь.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-225">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="1f2aa-226">Например, чтобы просмотреть раздел реестра HKLM\Software на диске HKLM: с другого диска, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-226">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="1f2aa-227">Чтобы открыть диск, используйте командлет Set-Location.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-227">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="1f2aa-228">Запомните двоеточие при указании пути к диску.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-228">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="1f2aa-229">Например, чтобы изменить расположение на корневой каталог диска Cert:, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-229">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="1f2aa-230">Затем, чтобы просмотреть содержимое диска Cert:, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-230">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="1f2aa-231">Перемещение по иерархическим данным</span><span class="sxs-lookup"><span data-stu-id="1f2aa-231">Moving through hierarchical data</span></span>

<span data-ttu-id="1f2aa-232">Вы можете перемещаться по диску поставщика так же, как и к жесткому диску.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-232">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="1f2aa-233">Если данные упорядочены в иерархии элементов внутри элементов, используйте обратную косую черту ( `\` ), чтобы указать дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-233">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="1f2aa-234">Используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-234">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="1f2aa-235">Например, чтобы изменить расположение на раздел реестра HKLM\Software, введите команду Set-Location, например:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-235">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="1f2aa-236">Если любой элемент в полном имени содержит пробелы, имя необходимо заключить в двойные кавычки ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="1f2aa-236">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="1f2aa-237">В следующем примере показан полный путь, содержащий пробелы.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-237">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="1f2aa-238">Можно также использовать относительные ссылки на расположения.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-238">You can also use relative references to locations.</span></span> <span data-ttu-id="1f2aa-239">Точка ( `.` ) представляет текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-239">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="1f2aa-240">Например, если вы используете раздел `HKLM:\Software\Microsoft` реестра и хотите перечислить подразделы реестра в `HKLM:\Software\Microsoft\PowerShell` разделе, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-240">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="1f2aa-241">Кроме того, двойные точки ( `..` ) ссылаются на каталог или контейнер непосредственно над текущим расположением.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-241">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="1f2aa-242">Для навигации по иерархии поставщика можно использовать двойные точки ( `..` ).</span><span class="sxs-lookup"><span data-stu-id="1f2aa-242">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="1f2aa-243">Домашняя страница поставщика</span><span class="sxs-lookup"><span data-stu-id="1f2aa-243">Provider Home</span></span>

<span data-ttu-id="1f2aa-244">Поставщики также имеют **домашнюю** папку.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-244">Providers also have a **Home** location.</span></span>  <span data-ttu-id="1f2aa-245">Это расположение является общим для всех, `PSDrives` которое поддерживается поставщиком.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-245">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="1f2aa-246">Его можно получить, просмотрев свойство **Home** поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-246">It can be retrieved by viewing the **Home** property of the provider.</span></span>

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

<span data-ttu-id="1f2aa-247">Поставщик **FileSystem** является единственным поставщиком, имеющим значение по умолчанию для **Home** .</span><span class="sxs-lookup"><span data-stu-id="1f2aa-247">The **FileSystem** provider is the only provider that has a default value for **Home** .</span></span> <span data-ttu-id="1f2aa-248">Это то же значение, что и `$Home` .</span><span class="sxs-lookup"><span data-stu-id="1f2aa-248">It's the same value as `$Home`.</span></span> <span data-ttu-id="1f2aa-249">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="1f2aa-249">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="1f2aa-250">Можно задать **домашний** каталог для поставщика в текущем сеансе, используя его свойство.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-250">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="1f2aa-251">`~`Символ может использоваться для представления домашнего каталога поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-251">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="1f2aa-252">Если у поставщика нет установленного **домашней** папки, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-252">If the provider doesn't have a **Home** location set, you see an error.</span></span>

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

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="1f2aa-253">Поиск динамических параметров</span><span class="sxs-lookup"><span data-stu-id="1f2aa-253">Finding dynamic parameters</span></span>

<span data-ttu-id="1f2aa-254">Динамические параметры — это параметры командлета, которые добавляются в командлет поставщиком.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-254">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="1f2aa-255">Эти параметры доступны только в том случае, если командлет используется с поставщиком, который их добавил.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-255">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="1f2aa-256">Например, `Cert:` диск добавляет параметр **CodeSigningCert** в `Get-Item` `Get-ChildItem` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-256">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="1f2aa-257">Этот параметр можно использовать только при использовании `Get-Item` или `Get-ChildItem` на `Cert:` диске.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-257">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="1f2aa-258">Список динамических параметров, поддерживаемых поставщиком, см. в файле справки для поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-258">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="1f2aa-259">Тип:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-259">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="1f2aa-260">Пример:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-260">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="1f2aa-261">Изучение поставщиков</span><span class="sxs-lookup"><span data-stu-id="1f2aa-261">Learning about providers</span></span>

<span data-ttu-id="1f2aa-262">Несмотря на то что все данные поставщика отображаются в дисках и для их перемещения используются те же методы, подобный процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-262">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="1f2aa-263">Хранилище данных, предоставляемое поставщиком, может быть так же разнообразным, как Active Directory расположений и почтовых ящиков Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="1f2aa-263">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="1f2aa-264">Для получения сведений об отдельных поставщиках PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-264">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="1f2aa-265">Пример:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-265">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="1f2aa-266">Чтобы получить список разделов справки о поставщиках, введите:</span><span class="sxs-lookup"><span data-stu-id="1f2aa-266">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="1f2aa-267">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1f2aa-267">See also</span></span>

[<span data-ttu-id="1f2aa-268">about_Locations</span><span class="sxs-lookup"><span data-stu-id="1f2aa-268">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="1f2aa-269">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="1f2aa-269">about_Path_Syntax</span></span>](about_Path_Syntax.md)
