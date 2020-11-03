---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: ed69b50019b3393eeeda42a250d65d4dfb809a51
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228557"
---
# <span data-ttu-id="b8d17-103">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b8d17-103">Install-PackageProvider</span></span>

## <span data-ttu-id="b8d17-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b8d17-104">SYNOPSIS</span></span>
<span data-ttu-id="b8d17-105">Устанавливает один или несколько поставщиков пакетов Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="b8d17-105">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="b8d17-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8d17-106">SYNTAX</span></span>

### <span data-ttu-id="b8d17-107">Паккажебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8d17-107">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b8d17-108">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="b8d17-108">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="b8d17-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8d17-109">DESCRIPTION</span></span>

<span data-ttu-id="b8d17-110">Командлет **Install-PackageProvider** устанавливает соответствующие поставщики Управление пакетами, доступные в источниках пакетов, зарегистрированных с помощью **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-110">The **Install-PackageProvider** cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet** .</span></span>
<span data-ttu-id="b8d17-111">По умолчанию сюда входят модули, доступные в коллекция PowerShell с тегом **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-111">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** tag.</span></span>
<span data-ttu-id="b8d17-112">Поставщик Управление пакетами **PowerShellGet** используется для поиска поставщиков в этих репозиториях.</span><span class="sxs-lookup"><span data-stu-id="b8d17-112">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="b8d17-113">Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные с помощью приложения начальной загрузки Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="b8d17-113">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="b8d17-114">Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные в хранилище больших двоичных объектов Azure Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="b8d17-114">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="b8d17-115">Используйте поставщик загрузчика, чтобы найти и установить их.</span><span class="sxs-lookup"><span data-stu-id="b8d17-115">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="b8d17-116">Для первого выполнения PackageManagement требуется подключение к Интернету для загрузки поставщика пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8d17-116">In order to execute the first time, PackageManagement requires an internet connection to download the Nuget package provider.</span></span>
<span data-ttu-id="b8d17-117">Однако если компьютер не подключен к Интернету и необходимо использовать поставщик NuGet или PowerShellGet, его можно загрузить на другой компьютер и скопировать на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="b8d17-117">However, if your computer does not have an internet connection and you need to use the Nuget or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span>
<span data-ttu-id="b8d17-118">Для этого сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="b8d17-118">Use the following steps to do this:</span></span>

1.
<span data-ttu-id="b8d17-119">Выполните команду `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` , чтобы установить поставщик с компьютера с подключением к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b8d17-119">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>

2.
<span data-ttu-id="b8d17-120">После установки можно найти поставщика, установленного в `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` или `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` .</span><span class="sxs-lookup"><span data-stu-id="b8d17-120">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>`.</span></span>

3.
<span data-ttu-id="b8d17-121">Поместите \<ProviderName\> папку, которая в данном случае является папкой NuGet, в соответствующее расположение на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8d17-121">Place the \<ProviderName\> folder, which in this case is the Nuget folder, in the corresponding location on your target computer.</span></span>
<span data-ttu-id="b8d17-122">Если целевой компьютер является Nano Server, необходимо выполнить команду **Install-PackageProvider** с Nano Server, чтобы скачать правильные двоичные файлы NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8d17-122">If your target computer is a Nano server, you need to run **Install-PackageProvider** from Nano Server to download the correct Nuget binaries.</span></span>

4.
<span data-ttu-id="b8d17-123">Перезапустите PowerShell для автоматической загрузки поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-123">Restart PowerShell to auto-load the package provider.</span></span>
<span data-ttu-id="b8d17-124">Кроме того, можно выполнить команду, `Get-PackageProvider -ListAvailable` чтобы вывести список всех поставщиков пакетов, доступных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8d17-124">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
<span data-ttu-id="b8d17-125">Затем используйте `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` для импорта поставщика в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8d17-125">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current PowerShell session.</span></span>

## <span data-ttu-id="b8d17-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8d17-126">EXAMPLES</span></span>

### <span data-ttu-id="b8d17-127">Пример 1. Установка поставщика пакетов из коллекция PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8d17-127">Example 1: Install a package provider from the PowerShell Gallery</span></span>

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

<span data-ttu-id="b8d17-128">Эта команда устанавливает Gistprovider из коллекция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8d17-128">This command installs the Gistprovider from the PowerShell Gallery.</span></span>

### <span data-ttu-id="b8d17-129">Пример 2. Установка указанной версии поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="b8d17-129">Example 2: Install a specified version of a package provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

<span data-ttu-id="b8d17-130">В этом примере устанавливается указанная версия поставщика пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8d17-130">This example installs a specified version of the Nuget package provider.</span></span>

<span data-ttu-id="b8d17-131">Первая команда находит все версии поставщика пакетов с именем NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8d17-131">The first command finds all versions of the package provider named Nuget.</span></span>
<span data-ttu-id="b8d17-132">Вторая команда устанавливает указанную версию поставщика пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8d17-132">The second command installs a specified version of the Nuget package provider.</span></span>

### <span data-ttu-id="b8d17-133">Пример 3. Поиск поставщика и его установка</span><span class="sxs-lookup"><span data-stu-id="b8d17-133">Example 3: Find a provider and install it</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

<span data-ttu-id="b8d17-134">Эта команда использует **Find-PackageProvider** и конвейер для поиска и установки поставщика реестра.</span><span class="sxs-lookup"><span data-stu-id="b8d17-134">This command uses **Find-PackageProvider** and the pipeline to search for the Gist provider and install it.</span></span>

### <span data-ttu-id="b8d17-135">Пример 4. Установка поставщика в папку модуля текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="b8d17-135">Example 4: Install a provider to the current user's module folder</span></span>

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

<span data-ttu-id="b8d17-136">Эта команда устанавливает поставщик пакетов в $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies, чтобы только текущий пользователь мог его использовать.</span><span class="sxs-lookup"><span data-stu-id="b8d17-136">This command installs a package provider to $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies so that only the current user can use it.</span></span>

## <span data-ttu-id="b8d17-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8d17-137">PARAMETERS</span></span>

### <span data-ttu-id="b8d17-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="b8d17-138">-AllVersions</span></span>

<span data-ttu-id="b8d17-139">Указывает, что этот командлет устанавливает все доступные версии поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-139">Indicates that this cmdlet installs all available versions of the package provider.</span></span>
<span data-ttu-id="b8d17-140">По умолчанию командлет **Install-PackageProvider** Возвращает максимальную доступную версию.</span><span class="sxs-lookup"><span data-stu-id="b8d17-140">By default, **Install-PackageProvider** only returns the highest available version.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="b8d17-141">-Credential</span></span>

<span data-ttu-id="b8d17-142">Указывает учетную запись пользователя, имеющую разрешение на установку поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-142">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-143">-Force</span><span class="sxs-lookup"><span data-stu-id="b8d17-143">-Force</span></span>

<span data-ttu-id="b8d17-144">Указывает, что этот командлет принудительно выполняет все действия с этим командлетом, который можно принудительно применить.</span><span class="sxs-lookup"><span data-stu-id="b8d17-144">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="b8d17-145">Сейчас это означает, что параметр *Force* действует так же, как параметр *форцебутстрап* .</span><span class="sxs-lookup"><span data-stu-id="b8d17-145">Currently, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-146">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="b8d17-146">-ForceBootstrap</span></span>

<span data-ttu-id="b8d17-147">Указывает, что этот командлет автоматически устанавливает поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-147">Indicates that this cmdlet automatically installs the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b8d17-148">-InputObject</span></span>

<span data-ttu-id="b8d17-149">Указывает объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-149">Specifies a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="b8d17-150">Используйте командлет **Find-PackageProvider** , чтобы получить объект **софтвареидентити** для передачи в **Install-PackageProvider** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-150">Use the **Find-PackageProvider** cmdlet to obtain a **SoftwareIdentity** object to pipe into **Install-PackageProvider** .</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b8d17-151">-MaximumVersion</span></span>

<span data-ttu-id="b8d17-152">Указывает максимально допустимую версию поставщика пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="b8d17-152">Specifies the maximum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="b8d17-153">Если этот параметр не добавлен, командлет **Install-PackageProvider** устанавливает самую новую доступную версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="b8d17-153">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-154">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b8d17-154">-MinimumVersion</span></span>

<span data-ttu-id="b8d17-155">Указывает минимально допустимую версию поставщика пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="b8d17-155">Specifies the minimum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="b8d17-156">Если этот параметр не указан, командлет **Install-PackageProvider** устанавливает самую новую доступную версию пакета, которая также удовлетворяет всем требованиям, указанным в параметре *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="b8d17-156">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-157">-Name</span><span class="sxs-lookup"><span data-stu-id="b8d17-157">-Name</span></span>

<span data-ttu-id="b8d17-158">Указывает одно или несколько имен модулей поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-158">Specifies one or more package provider module names.</span></span>
<span data-ttu-id="b8d17-159">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="b8d17-159">Separate multiple package names with commas.</span></span>
<span data-ttu-id="b8d17-160">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b8d17-160">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-161">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="b8d17-161">-Proxy</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b8d17-162">-ProxyCredential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-163">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b8d17-163">-RequiredVersion</span></span>

<span data-ttu-id="b8d17-164">Указывает точную разрешенную версию поставщика пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="b8d17-164">Specifies the exact allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="b8d17-165">Если этот параметр не указан, командлет **Install-PackageProvider** устанавливает самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="b8d17-165">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-166">-Scope</span><span class="sxs-lookup"><span data-stu-id="b8d17-166">-Scope</span></span>

<span data-ttu-id="b8d17-167">Указывает область установки поставщика.</span><span class="sxs-lookup"><span data-stu-id="b8d17-167">Specifies the installation scope of the provider.</span></span>
<span data-ttu-id="b8d17-168">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-168">The acceptable values for this parameter are: **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="b8d17-169">Область **ALLUSERS** устанавливает поставщиков в расположение, доступное всем пользователям компьютера.</span><span class="sxs-lookup"><span data-stu-id="b8d17-169">The **AllUsers** scope installs providers in a location that is accessible to all users of the computer.</span></span>
<span data-ttu-id="b8d17-170">По умолчанию это **$env:P рограмфилес\паккажеманажемент\провидерассемблиес.**</span><span class="sxs-lookup"><span data-stu-id="b8d17-170">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

<span data-ttu-id="b8d17-171">В области **CurrentUser** устанавливаются поставщики в расположении, где они доступны только текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="b8d17-171">The **CurrentUser** scope installs providers in a location where they are only accessible to the current user.</span></span>
<span data-ttu-id="b8d17-172">По умолчанию это **$env: локалаппдата\паккажеманажемент\провидерассемблиес.**</span><span class="sxs-lookup"><span data-stu-id="b8d17-172">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-173">-Source</span><span class="sxs-lookup"><span data-stu-id="b8d17-173">-Source</span></span>

<span data-ttu-id="b8d17-174">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-174">Specifies one or more package sources.</span></span>
<span data-ttu-id="b8d17-175">Используйте командлет Get-PackageSource, чтобы получить список доступных источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8d17-175">Use the Get-PackageSource cmdlet to get a list of available package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b8d17-176">-Confirm</span></span>

<span data-ttu-id="b8d17-177">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b8d17-177">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b8d17-178">-WhatIf</span></span>

<span data-ttu-id="b8d17-179">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b8d17-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b8d17-180">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b8d17-180">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8d17-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b8d17-181">CommonParameters</span></span>

<span data-ttu-id="b8d17-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b8d17-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8d17-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b8d17-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8d17-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b8d17-184">INPUTS</span></span>

### <span data-ttu-id="b8d17-185">Microsoft. PackageManagement. Packaging. Софтвареидентити</span><span class="sxs-lookup"><span data-stu-id="b8d17-185">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="b8d17-186">Объект **софтвареидентити** можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b8d17-186">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span>
<span data-ttu-id="b8d17-187">Используйте Find-PackageProvider, чтобы получить объект **софтвареидентити** , который можно направить в **Install-PackageProvider** .</span><span class="sxs-lookup"><span data-stu-id="b8d17-187">Use Find-PackageProvider to get a **SoftwareIdentity** object that can be piped into **Install-PackageProvider** .</span></span>

## <span data-ttu-id="b8d17-188">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8d17-188">OUTPUTS</span></span>

## <span data-ttu-id="b8d17-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b8d17-189">NOTES</span></span>

## <span data-ttu-id="b8d17-190">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b8d17-190">RELATED LINKS</span></span>

[<span data-ttu-id="b8d17-191">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b8d17-191">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="b8d17-192">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b8d17-192">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="b8d17-193">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b8d17-193">Import-PackageProvider</span></span>](Import-PackageProvider.md)

