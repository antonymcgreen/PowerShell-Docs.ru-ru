---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 0ec31d32ef73108b53b18b529cc93aa80787fe25
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604596"
---
# <span data-ttu-id="c1313-102">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-102">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="c1313-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1313-103">SYNOPSIS</span></span>
<span data-ttu-id="c1313-104">Создает и регистрирует новую конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-104">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="c1313-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1313-105">SYNTAX</span></span>

### <span data-ttu-id="c1313-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c1313-106">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c1313-107">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="c1313-107">AssemblyNameParameterSet</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c1313-108">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c1313-108">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c1313-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1313-109">DESCRIPTION</span></span>

<span data-ttu-id="c1313-110">`Register-PSSessionConfiguration`Командлет создает и регистрирует новую конфигурацию сеанса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1313-110">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="c1313-111">Это расширенный командлет, с помощью которого можно создавать пользовательские сеансы для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c1313-111">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="c1313-112">Каждый сеанс PowerShell (**PSSession**) использует конфигурацию сеанса, также известную как конечная точка.</span><span class="sxs-lookup"><span data-stu-id="c1313-112">Every PowerShell session (**PSSession**) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="c1313-113">Когда пользователи создают сеанс, который подключается к компьютеру, он может выбрать конфигурацию сеанса или использовать конфигурацию сеанса по умолчанию, зарегистрированную при включении удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1313-113">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="c1313-114">Кроме того, пользователи могут задавать привилегированную переменную $PSSessionConfigurationName, которая определяет конфигурацию по умолчанию для удаленных сеансов, создаваемых в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-114">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="c1313-115">Конфигурация сеанса определяет среду для удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-115">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="c1313-116">Она определяет, какие команды и элементы языка будут доступны в сеансе, и может включать параметры для защиты компьютера, например ограничения на объем данных, принимаемых сеансом в удаленном режиме в одном объекте или команде.</span><span class="sxs-lookup"><span data-stu-id="c1313-116">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="c1313-117">Дескриптор безопасности конфигурации сеанса определяет, какие пользователи имеют разрешение на использование конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-117">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="c1313-118">Элементы конфигурации определяются с помощью сборки, реализующей новый класс конфигурации, или скрипта, выполняемого в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-118">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="c1313-119">Начиная с PowerShell 3,0, можно также использовать файл конфигурации сеанса для определения конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-119">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="c1313-120">Сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="c1313-120">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="c1313-121">Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="c1313-121">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="c1313-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1313-122">EXAMPLES</span></span>

### <span data-ttu-id="c1313-123">Пример 1. Регистрация конфигурации сеанса NewShell</span><span class="sxs-lookup"><span data-stu-id="c1313-123">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="c1313-124">В этом примере мы регистрируем конфигурацию сеанса **NewShell** .</span><span class="sxs-lookup"><span data-stu-id="c1313-124">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="c1313-125">Параметры **AssemblyName** и **ApplicationBase** указывают расположение файла **MyShell.dll** , который указывает командлеты и поставщики в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-125">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="c1313-126">Параметр **ConfigurationTypeName** указывает класс конфигурации, используемый из сборки.</span><span class="sxs-lookup"><span data-stu-id="c1313-126">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="c1313-127">Чтобы использовать эту конфигурацию, введите `New-PSSession -ConfigurationName newshell` .</span><span class="sxs-lookup"><span data-stu-id="c1313-127">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="c1313-128">Пример 2. Регистрация конфигурации сеанса MaintenanceShell</span><span class="sxs-lookup"><span data-stu-id="c1313-128">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="c1313-129">В этом примере регистрируется конфигурация сеанса **MaintenanceShell** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1313-129">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="c1313-130">Параметр **StartupScript** указывает `Maintenance.ps1` скрипт.</span><span class="sxs-lookup"><span data-stu-id="c1313-130">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="c1313-131">Когда пользователь использует `New-PSSession` команду и выбирает конфигурацию **MaintenanceShell** , `Maintenance.ps1` сценарий выполняется в новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-131">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="c1313-132">Скрипт может настроить сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1313-132">The script can configure the session.</span></span> <span data-ttu-id="c1313-133">Сюда входят импорт модулей и Настройка политики выполнения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-133">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="c1313-134">Если скрипт создает ошибки, включая устранимые ошибки, `New-PSSession` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c1313-134">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="c1313-135">Пример 3. Регистрация конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="c1313-135">Example 3: Register a session configuration</span></span>

<span data-ttu-id="c1313-136">В этом примере регистрируется конфигурация сеанса **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="c1313-136">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="c1313-137">`$sessionParams`Переменная является хэш-таблицей, содержащей все значения параметров.</span><span class="sxs-lookup"><span data-stu-id="c1313-137">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="c1313-138">Эта хэш-таблица передается командлету с помощью PowerShell Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="c1313-138">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="c1313-139">`Register-PSSessionConfiguration`Команда использует параметр **секуритидескриторсддл** для указания SDDL в значении `$sddl` переменной, а параметр **максимумрецеиведобжектсиземб** — для увеличения предельного размера объекта.</span><span class="sxs-lookup"><span data-stu-id="c1313-139">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="c1313-140">Параметр **StartupScript** определяет скрипт, который будет использоваться для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-140">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### <span data-ttu-id="c1313-141">Пример 4. возврат элемента контейнера конфигурации</span><span class="sxs-lookup"><span data-stu-id="c1313-141">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="c1313-142">В этом примере показано, как зарегистрировать конфигурацию **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="c1313-142">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="c1313-143">`Register-PSSessionConfiguration` Возвращает объект **всманконфигконтаинерелемент** , хранящийся в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="c1313-143">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="c1313-144">`Format-List` Отображает все свойства возвращенного объекта.</span><span class="sxs-lookup"><span data-stu-id="c1313-144">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="c1313-145">Свойство **PSPath** показывает, что объект хранится в каталоге на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="c1313-145">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="c1313-146">`Get-ChildItem` (псевдоним `dir` ) Отображает элементы в `WSMan:\LocalHost\PlugIn` пути.</span><span class="sxs-lookup"><span data-stu-id="c1313-146">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="c1313-147">К ним относятся новая конфигурация **MaintenanceShell** и две конфигурации по умолчанию, которые входят в состав PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1313-147">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### <span data-ttu-id="c1313-148">Пример 5. Регистрация конфигурации сеанса с помощью скрипта запуска</span><span class="sxs-lookup"><span data-stu-id="c1313-148">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="c1313-149">В этом примере мы создадим и регистрируем конфигурацию сеанса **WithProfile** .</span><span class="sxs-lookup"><span data-stu-id="c1313-149">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="c1313-150">Параметр **StartupScript** указывает PowerShell выполнить указанный скрипт для любого сеанса, использующего конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-150">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="c1313-151">Скрипт содержит единственную команду, в которой используется запись с точками для запуска профиля **CurrentUserAllHosts** пользователя в текущей области сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-151">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="c1313-152">Дополнительные сведения о профилях см. в разделе [about_Profiles](./About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c1313-152">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="c1313-153">Дополнительные сведения о вызовах с использованием точки см. в разделе [about_Scopes](./About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="c1313-153">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="c1313-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1313-154">PARAMETERS</span></span>

### <span data-ttu-id="c1313-155">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="c1313-155">-AccessMode</span></span>

<span data-ttu-id="c1313-156">Включает и отключает конфигурацию сеанса и определяет возможность ее использования для удаленных или локальных сеансов компьютера.</span><span class="sxs-lookup"><span data-stu-id="c1313-156">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="c1313-157">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c1313-157">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c1313-158">Отключена.</span><span class="sxs-lookup"><span data-stu-id="c1313-158">Disabled.</span></span> <span data-ttu-id="c1313-159">отключает конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-159">Disables the session configuration.</span></span> <span data-ttu-id="c1313-160">Использовать конфигурацию для локального или удаленного доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c1313-160">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="c1313-161">Локальный.</span><span class="sxs-lookup"><span data-stu-id="c1313-161">Local.</span></span> <span data-ttu-id="c1313-162">Позволяет пользователям локального компьютера использовать конфигурацию сеанса для создания локального сеанса замыкания на себя на том же компьютере, но запрещает доступ удаленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="c1313-162">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="c1313-163">Удаленный.</span><span class="sxs-lookup"><span data-stu-id="c1313-163">Remote.</span></span> <span data-ttu-id="c1313-164">позволяет локальным и удаленным пользователям использовать конфигурацию сеанса для создания сеансов и выполнить команды на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1313-164">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="c1313-165">Значение по умолчанию — Remote.</span><span class="sxs-lookup"><span data-stu-id="c1313-165">The default value is Remote.</span></span>

<span data-ttu-id="c1313-166">Другие командлеты могут переопределить значение этого параметра позже.</span><span class="sxs-lookup"><span data-stu-id="c1313-166">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="c1313-167">Например, `Enable-PSRemoting` командлет разрешает удаленный доступ ко всем конфигурациям сеансов, `Enable-PSSessionConfiguration` командлет включает конфигурации сеанса, и `Disable-PSRemoting` командлет предотвращает удаленный доступ ко всем конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="c1313-167">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="c1313-168">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-168">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-169">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="c1313-169">-ApplicationBase</span></span>

<span data-ttu-id="c1313-170">Указывает путь к файлу сборки ( \* . dll), указанному в значении параметра **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="c1313-170">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="c1313-171">Используйте этот параметр, если значение параметра **AssemblyName** не содержит путь.</span><span class="sxs-lookup"><span data-stu-id="c1313-171">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="c1313-172">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c1313-172">The default is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-173">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="c1313-173">-AssemblyName</span></span>

<span data-ttu-id="c1313-174">Указывает имя файла сборки (\*.dll), в котором определен тип конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c1313-174">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="c1313-175">Путь к DLL-файлу можно указать в этом параметре или в значении параметра **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="c1313-175">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="c1313-176">Этот параметр является обязательным при указании параметра **ConfigurationTypeName** .</span><span class="sxs-lookup"><span data-stu-id="c1313-176">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-177">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="c1313-177">-ConfigurationTypeName</span></span>

<span data-ttu-id="c1313-178">задает полное имя типа Microsoft .NET Framework, используемого для этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c1313-178">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="c1313-179">Задаваемый тип должен реализовывать класс **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c1313-179">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="c1313-180">Чтобы указать файл сборки ( \* . dll), который реализует тип конфигурации, укажите параметры **AssemblyName** и **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="c1313-180">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="c1313-181">Создание типа позволяет управлять дополнительными аспектами конфигурации сеанса, такими как предоставление или скрытие определенных параметров командлетов, а также задание размера данных и ограничений размера объектов, которые пользователи не могут переопределить.</span><span class="sxs-lookup"><span data-stu-id="c1313-181">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="c1313-182">Если этот параметр не указан, для настройки конфигурации сеанса используется класс **DefaultRemotePowerShellConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c1313-182">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-183">-Force</span><span class="sxs-lookup"><span data-stu-id="c1313-183">-Force</span></span>

<span data-ttu-id="c1313-184">Подавляет все запросы пользователя и перезапускает службу **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="c1313-184">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="c1313-185">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="c1313-185">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="c1313-186">Чтобы предотвратить перезагрузку и отключить запрос на перезагрузку, укажите параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="c1313-186">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="c1313-187">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="c1313-187">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="c1313-188">Указывает предельный объем данных, которые могут быть отправлены на этот компьютер в любой отдельной удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="c1313-188">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="c1313-189">Введите размер данных в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="c1313-189">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="c1313-190">Значение по умолчанию — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="c1313-190">The default is 50 MB.</span></span>

<span data-ttu-id="c1313-191">Если ограничение на размер данных определено в типе конфигурации, заданном параметром **ConfigurationTypeName**, используется ограничение из типа конфигурации, а значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c1313-191">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-192">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="c1313-192">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="c1313-193">Указывает предельный объем данных, которые могут быть отправлены на этот компьютер в любом отдельном объекте.</span><span class="sxs-lookup"><span data-stu-id="c1313-193">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="c1313-194">Введите размер данных в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="c1313-194">Enter the data size in megabytes.</span></span> <span data-ttu-id="c1313-195">Значение по умолчанию — 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="c1313-195">The default is 10 MB.</span></span>

<span data-ttu-id="c1313-196">Если ограничение на размер объекта определено в типе конфигурации, заданном параметром **ConfigurationTypeName**, используется ограничение из типа конфигурации, а значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c1313-196">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-197">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="c1313-197">-ModulesToImport</span></span>

<span data-ttu-id="c1313-198">Указывает модули, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-198">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="c1313-199">По умолчанию в сеансы импортируются только **Microsoft. PowerShell. Core** .</span><span class="sxs-lookup"><span data-stu-id="c1313-199">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="c1313-200">Если командлеты не исключены, можно использовать `Import-Module` для добавления модулей в сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1313-200">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="c1313-201">Модули, указанные в этом значении параметра, импортируются в дополнение к модулям, заданным параметром **SessionType** , и значения, перечисленные в ключе **ModulesToImport** в файле конфигурации сеанса ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="c1313-201">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="c1313-202">При этом параметры в файле конфигурации сеанса могут скрывать экспортируемые модулями команды или запрещать их использование.</span><span class="sxs-lookup"><span data-stu-id="c1313-202">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="c1313-203">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-203">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-204">-Name</span><span class="sxs-lookup"><span data-stu-id="c1313-204">-Name</span></span>

<span data-ttu-id="c1313-205">Указывает имя конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-205">Specifies a name for the session configuration.</span></span> <span data-ttu-id="c1313-206">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c1313-206">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-207">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="c1313-207">-NoServiceRestart</span></span>

<span data-ttu-id="c1313-208">Не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.</span><span class="sxs-lookup"><span data-stu-id="c1313-208">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="c1313-209">По умолчанию при выполнении `Register-PSSessionConfiguration` команды вам будет предложено перезапустить службу **WinRM** , чтобы обеспечить эффективную настройку нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-209">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="c1313-210">Пока служба **WinRM** не будет перезапущена, Новая конфигурация сеанса не вступит в силу.</span><span class="sxs-lookup"><span data-stu-id="c1313-210">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="c1313-211">Чтобы перезапустить службу **WinRM** без запроса, укажите параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="c1313-211">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="c1313-212">Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="c1313-212">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="c1313-213">-Path</span><span class="sxs-lookup"><span data-stu-id="c1313-213">-Path</span></span>

<span data-ttu-id="c1313-214">Указывает путь и имя файла конфигурации сеанса (. pssc), например, созданного `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="c1313-214">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="c1313-215">Если путь не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c1313-215">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="c1313-216">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-217">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="c1313-217">-ProcessorArchitecture</span></span>

<span data-ttu-id="c1313-218">Определяет, запускается ли 32-разрядная или 64-разрядная версия процесса PowerShell в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-218">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="c1313-219">Допустимые значения для этого параметра: x86 (32-bit) и AMD64 (64-bit).</span><span class="sxs-lookup"><span data-stu-id="c1313-219">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="c1313-220">Значение по умолчанию определяется архитектурой процессора компьютера, на котором размещена конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-220">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="c1313-221">Этот параметр можно использовать для создания 32-разрядного сеанса на 64-разрядном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1313-221">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="c1313-222">Создать 64-разрядный процесс на 32-разрядном компьютере нельзя.</span><span class="sxs-lookup"><span data-stu-id="c1313-222">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-223">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="c1313-223">-PSVersion</span></span>

<span data-ttu-id="c1313-224">Указывает версию PowerShell в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-224">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="c1313-225">Значение этого параметра имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-225">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="c1313-226">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-226">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-227">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c1313-227">-RunAsCredential</span></span>

<span data-ttu-id="c1313-228">Указывает учетные данные для команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-228">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="c1313-229">По умолчанию команды выполняются с разрешениями текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1313-229">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="c1313-230">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-230">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c1313-231">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="c1313-231">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="c1313-232">Задает строку в формате языка определения дескрипторов безопасности (SDDL) для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c1313-232">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="c1313-233">Эта строка определяет разрешения, необходимые для использования новой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-233">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="c1313-234">Чтобы использовать конфигурацию сеанса в сеансе, пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c1313-234">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="c1313-235">В случае сложного дескриптора безопасности вместо этого параметра можно использовать параметр **ShowSecurityDescriptorUI**. Использовать оба параметра в одной команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="c1313-235">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="c1313-236">Использовать оба параметра в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="c1313-236">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="c1313-237">Если этот параметр не задан, для этой конфигурации используется корневой SDDL для службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="c1313-237">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="c1313-238">Для просмотра или изменения корневого элемента SDDL используйте поставщик WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c1313-238">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="c1313-239">Например, `Get-Item wsman:\localhost\service\rootSDDL`.</span><span class="sxs-lookup"><span data-stu-id="c1313-239">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="c1313-240">Для получения дополнительных сведений о поставщике WSMan введите `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="c1313-240">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-241">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="c1313-241">-SessionTypeOption</span></span>

<span data-ttu-id="c1313-242">Задает параметры для конкретного типа конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-242">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="c1313-243">Введите объект параметров типа сеанса, например объект **PSWorkflowExecutionOption** , `New-PSWorkflowExecutionOption` возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="c1313-243">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="c1313-244">Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-244">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="c1313-245">Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-245">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="c1313-246">При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-246">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="c1313-247">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-247">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-248">-ShowSecurityDescriptorUI</span><span class="sxs-lookup"><span data-stu-id="c1313-248">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="c1313-249">Указывает, что этот командлет отображает страницу свойств, которая помогает создать SDDL для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-249">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="c1313-250">Страница свойств появляется после ввода `Register-PSSessionConfiguration` команды и перезапуска службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="c1313-250">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="c1313-251">При задании разрешений для конфигурации Помните, что пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для использования конфигурации сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-251">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="c1313-252">Использовать этот параметр и параметр **SecurityDescriptorSDDL** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="c1313-252">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="c1313-253">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="c1313-253">-StartupScript</span></span>

<span data-ttu-id="c1313-254">Указывает полный путь к скрипту PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1313-254">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="c1313-255">Указанный скрипт выполняется в новом сеансе, для которого используется данная конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-255">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="c1313-256">С помощью скрипта можно дополнительно настроить сеанс.</span><span class="sxs-lookup"><span data-stu-id="c1313-256">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="c1313-257">Если скрипт создает ошибку, даже устранимую ошибку, сеанс не создается и `New-PSSession` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c1313-257">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-258">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="c1313-258">-ThreadOptions</span></span>

<span data-ttu-id="c1313-259">Указывает, как потоки создаются и используются при выполнении команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1313-259">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="c1313-260">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c1313-260">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c1313-261">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c1313-261">Default</span></span>
- <span data-ttu-id="c1313-262">реусесреад</span><span class="sxs-lookup"><span data-stu-id="c1313-262">ReuseThread</span></span>
- <span data-ttu-id="c1313-263">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="c1313-263">UseCurrentThread</span></span>
- <span data-ttu-id="c1313-264">усеневсреад</span><span class="sxs-lookup"><span data-stu-id="c1313-264">UseNewThread</span></span>

<span data-ttu-id="c1313-265">Значение по умолчанию — **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="c1313-265">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="c1313-266">Дополнительные сведения см. в разделе [перечисление пссреадоптионс](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="c1313-266">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-267">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="c1313-267">-TransportOption</span></span>

<span data-ttu-id="c1313-268">Указывает параметр транспорта.</span><span class="sxs-lookup"><span data-stu-id="c1313-268">Specifies the transport option.</span></span>

<span data-ttu-id="c1313-269">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-269">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-270">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="c1313-270">-UseSharedProcess</span></span>

<span data-ttu-id="c1313-271">Используйте только один процесс для размещения всех сеансов, запущенных одним и тем же пользователем, и используйте ту же конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1313-271">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="c1313-272">По умолчанию каждый сеанс размещается в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="c1313-272">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="c1313-273">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c1313-273">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c1313-274">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c1313-274">-Confirm</span></span>

<span data-ttu-id="c1313-275">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c1313-275">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c1313-276">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c1313-276">-WhatIf</span></span>

<span data-ttu-id="c1313-277">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c1313-277">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c1313-278">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c1313-278">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c1313-279">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="c1313-279">-ThreadApartmentState</span></span>

<span data-ttu-id="c1313-280">Указывает состояние апартамента для используемого модуля потоков.</span><span class="sxs-lookup"><span data-stu-id="c1313-280">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="c1313-281">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c1313-281">Acceptable values are:</span></span>

- <span data-ttu-id="c1313-282">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="c1313-282">Unknown</span></span>
- <span data-ttu-id="c1313-283">MTA</span><span class="sxs-lookup"><span data-stu-id="c1313-283">MTA</span></span>
- <span data-ttu-id="c1313-284">STA</span><span class="sxs-lookup"><span data-stu-id="c1313-284">STA</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1313-285">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1313-285">CommonParameters</span></span>

<span data-ttu-id="c1313-286">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1313-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1313-287">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1313-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1313-288">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1313-288">INPUTS</span></span>

### <span data-ttu-id="c1313-289">None</span><span class="sxs-lookup"><span data-stu-id="c1313-289">None</span></span>

<span data-ttu-id="c1313-290">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="c1313-290">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c1313-291">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1313-291">OUTPUTS</span></span>

### <span data-ttu-id="c1313-292">Microsoft.WSMan.Management.WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="c1313-292">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="c1313-293">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1313-293">NOTES</span></span>

<span data-ttu-id="c1313-294">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="c1313-294">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="c1313-295">Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="c1313-295">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="c1313-296">Этот командлет создает XML-файл, представляющий веб-службы для конфигурации подключаемого модуля управления (WS-Management), и отправляет XML в WS-Management, который регистрирует подключаемый модуль на локальном компьютере ( `New-Item wsman:\localhost\plugin` ).</span><span class="sxs-lookup"><span data-stu-id="c1313-296">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="c1313-297">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="c1313-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="c1313-298">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="c1313-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="c1313-299">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1313-299">RELATED LINKS</span></span>

[<span data-ttu-id="c1313-300">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-300">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="c1313-301">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-301">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="c1313-302">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-302">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="c1313-303">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c1313-303">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="c1313-304">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-304">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="c1313-305">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c1313-305">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="c1313-306">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1313-306">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="c1313-307">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="c1313-307">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="c1313-308">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="c1313-308">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="c1313-309">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="c1313-309">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
