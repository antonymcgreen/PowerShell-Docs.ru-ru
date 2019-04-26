---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 042e9a30068d32dc5860255bdec960371121d866
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085306"
---
# <a name="packagemanagement-cmdlets"></a>Командлеты PackageManagement

Это основная составляющая PackageManagement, отвечающая за поддержку обнаружения, установки и инвентаризации программного обеспечения. Попробуйте использовать для выполнения этих операций следующие командлеты:

- `Find-Package`
- `Find-PackageProvider`
- `Get-Package`
- `Get-PackageProvider`
- `Get-PackageSource`
- `Import-PackageProvider`
- `Install-Package`
- `Install-PackageProvider`
- `Register-PackageSource`
- `Save-Package`
- `Set-PackageSource`
- `Uninstall-Package`
- `Unregister-PackageSource`

Поскольку PackageManagement является модулем PowerShell, можно обновить сам PackageManagement следующим образом:

```powershell
Install-Module PackageManagement –Force
```

В этом случае потребуется повторно войти в сеанс PowerShell, чтобы переключиться на новую версию PackageManagement.

## <a name="find-package-cmdletpowershellmodulepackagemanagementfind-package"></a>[Командлет Find-Package](/powershell/module/PackageManagement/Find-Package)

Этот командлет обеспечивает обнаружения пакетов программного обеспечения в доступных источниках с помощью загруженных поставщиков пакетов.

```powershell
# Find all available Windows PowerShell module packages from galleries registered
# with PowerShellGet provider
Find-Package -ProviderName PowerShellGet -Source as source
Find-Package -Name jquery –Provider NuGet -Source http://www.nuget.org/api/v2/

# Find package with name and version
# Here we are assuming that the user already registered nuget.org using
# Register-PackageSource. You can specify either the provider or the source, or
# neither. For the latter, performance may be less optimal as it searches through all
# the providers and registered sources.
Find-Package -Name jquery –Provider NuGet –RequiredVersion 2.1.4 -Source nuget.org
```

## <a name="find-packageprovider-cmdletpowershellmodulepackagemanagementfind-packageprovider"></a>[Командлет Find-PackageProvider](/powershell/module/PackageManagement/Find-PackageProvider)

Командлет `Find-PackageProvider` находит подходящие поставщики PackageManagement, которые доступны в зарегистрированных источниках пакетов PowerShellGet. Эти поставщики пакетов можно установить с помощью командлета `Install-PackageProvider`. По умолчанию сюда относятся модули, доступные в коллекции PowerShell с тегами PackageManagement и Provider.

Кроме того, `Find-PackageProvider` находит совпадающие поставщики PackageManagement, доступные в хранилище BLOB-объектов Azure PackageManagement, где для их поиска и установки используется поставщик начального загрузчика PackageManagement.

```powershell
#Find all available package providers in PackageManagement azure blob store as well as in PowerShellGallery.com
Find-PackageProvider

#Find all versions of a provider
Find-PackageProvider -Name "Nuget" -AllVersions

#Find a provider from a specified source
Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

## <a name="get-package-cmdletpowershellmodulepackagemanagementget-package"></a>[Командлет Get-Package](/powershell/module/PackageManagement/Get-Package)

Этот командлет возвращает список всех пакетов программного обеспечения, установленных с помощью PackageManagement.

```powershell
# Get all the packages installed by Programs provider
Get-Package –Provider Programs

# Get all the packages installed by NuGet provider at c:\test using the dynamic
# parameter destination
Get-Package –Provider NuGet -Destination c:\test
```

## <a name="get-packageprovider-cmdletpowershellmodulepackagemanagementget-packageprovider"></a>[Командлет Get-PackageProvider](/powershell/module/PackageManagement/Get-PackageProvider)

С помощью этого командлета можно выполнить инвентаризацию поставщиков пакетов, которые уже загружены и готовы к использованию на локальном компьютере.

```powershell
# Get all currently loaded package providers
Get-PackageProvider

# The following cmdlet will show all the package providers available on the machine (including those that are not loaded):
Get-PackageProvider -ListAvailable
```

## <a name="get-packagesource-cmdletpowershellmodulepackagemanagementget-packagesource"></a>[Командлет Get-PackageSource](/powershell/module/PackageManagement/Get-PackageSource)

Этот командлет возвращает список источников пакетов, зарегистрированных для поставщика пакетов.

```powershell
# Get all package sources
Get-PackageSource

# Get all package sources for a specific provider
Get-PackageSource –ProviderName PowerShellGet
```

## <a name="import-packageprovider-cmdletpowershellmodulepackagemanagementimport-packageprovider"></a>[Командлет Import-PackageProvider](/powershell/module/PackageManagement/Import-PackageProvider)

Этот командлет добавляет поставщиков пакетов для управления пакетами в текущий сеанс.

```powershell
# Import a package provider from the local machine
Import-PackageProvider –Name MyProvider

#The -Name parameter can be either the name of the provider or the full path to the provider. Currently, we support .dll, .exe and.psm1 for the full path case. If the name of the provider is used for the -Name parameter, then additional version parameters such as -RequiredVersion, -MinimumVersion and -MaximumVersion may be specified. Otherwise, the latest version of the provider will be imported.

#If a package provider is not yet loaded to your system, we can discover and install on-demand. You can use explicit discovery and install cmdlets to do so:
 Find-PackageProvider
 Install-PackageProvider –Name MyProvider

#After installed, follow the Import-PackageProvider to load it to your system.

# Import a specific version of a package provider. PackageManagement supports installations of multiple versions of a package provider using PackageProvider cmdlets (not by bootstrapper provider). You can install another version of a package provider given that you already have one up running by:
Find-PackageProvider –Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider –ListAvailable
Import-PackageProvider –Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
Import-PackageProvider –Name MyProvider –RequiredVersion xxxx -force
```

## <a name="install-package-cmdletpowershellmodulepackagemanagementinstall-package"></a>[Командлет Install-Package](/powershell/module/PackageManagement/Install-Package)

Этот командлет обеспечивает установку пакетов программного обеспечения в доступных источниках с помощью загруженных поставщиков пакетов.

```powershell
# Install a package by name.
# NuGet provider requires us to provide the dynamic parameter destination path
# when we use this provider to install. Not all providers will require you to supply
# dynamic parameters for PackageManagement cmdlets.
Install-Package -Name jquery -Source nuget.org -Destination c:\test

# Install a package by piping.
Find-Package -Name jquery –Provider NuGet | Install-Package -Destination c:\test
```

## <a name="install-packageprovider-cmdletpowershellmodulepackagemanagementinstall-packageprovider"></a>[Командлет Install-PackageProvider](/powershell/module/PackageManagement/Install-PackageProvider)

Этот командлет устанавливает один или несколько поставщиков пакетов для управления пакетами.

```powershell
# Install a package provider from the PowerShell Gallery
Install-PackageProvider –Name "Gistprovider" -Verbose

# Install a specified version of a package provider
Find-PackageProvider –Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force

# Find a provider and install it
Find-PackageProvider –Name "Gistprovider" | Install-PackageProvider -Verbose

# Install a provider to the current user’s module folder
Install-PackageProvider –Name Gistprovider –Verbose –Scope CurrentUser
```

## <a name="register-packagesource-cmdletpowershellmodulepackagemanagementregister-packagesource"></a>[Командлет Register-PackageSource](/powershell/module/PackageManagement/Register-PackageSource)

Этот командлет добавляет источник пакетов для указанного поставщика пакетов.
Каждый поставщик PackageManagement может иметь один или несколько источников программного обеспечения или репозиториев. PackageManagement предоставляет командлеты PowerShell для добавления, удаления и запроса источника. Например, можно зарегистрировать источник пакетов для поставщика NuGet:

```powershell
Register-PackageSource -Name "NugetSource" -Location "http://www.nuget.org/api/v2" –ProviderName nuget
```

## <a name="save-package-cmdletpowershellmodulepackagemanagementsave-package"></a>[Командлет Save-Package](/powershell/module/PackageManagement/Save-Package)

Этот командлет сохраняет пакеты на локальном компьютере без установки.

```powershell
# Saves jquery package to c:\test using NuGetProvider
# Notes that the -Path parameter must point to an existing location
Save-Package -Name jquery –Provider NuGet -Path c:\test

# Save a package by piping.
Find-Package -Name jquery -Source http://www.nuget.org/api/v2/ | Save-Package -Path c:\test
Find-Package -Source c:\test
```

## <a name="set-packagesource-cmdletpowershellmodulepackagemanagementset-packagesource"></a>[Командлет Set-PackageSource](/powershell/module/PackageManagement/Set-PackageSource)

Этот командлет изменяет сведения о существующем источнике пакетов.

```powershell
#Set-PackageSource changes the values for a source that has already been registered by running the Register-PackageSource cmdlet. By #running Set-PackageSource, you can change the source name and location.
Set-PackageSource  -Name nuget.org -Location  http://www.nuget.org/api/v2 -NewName nuget2 -NewLocation https://www.nuget.org/api/v2
```

## <a name="uninstall-package-cmdletpowershellmodulepackagemanagementuninstall-package"></a>[Командлет Uninstall-Package](/powershell/module/PackageManagement/Uninstall-Package)

Этот командлет удаляет пакеты, установленные на локальном компьютере.

```powershell
# Uninstall jquery using nuget
Uninstall-Package -Name jquery –Provider NuGet -Destination c:\test

# Uninstall a package with by piping with Get-Package
Get-Package -Name jquery –Provider NuGet -Destination c:\test | Uninstall-Package
```

## <a name="unregister-packagesource-cmdletpowershellmodulepackagemanagementunregister-packagesource"></a>[Командлет Unregister-PackageSource](/powershell/module/PackageManagement/Unregister-PackageSource)

```powershell
# Unregister a package source for the NuGet provider. You can use command Unregister-PackageSource, to disconnect with a repository, and Get-PackageSource, to discover what the repositories are associated with that provider.
Unregister-PackageSource  -Name "NugetSource"
```