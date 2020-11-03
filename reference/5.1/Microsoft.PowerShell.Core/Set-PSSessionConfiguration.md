---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 33773769cd19373764cf4adbe86bb990589948ff
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229753"
---
# <span data-ttu-id="de0b1-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="de0b1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="de0b1-104">SYNOPSIS</span></span>
<span data-ttu-id="de0b1-105">Изменяет свойства конфигурации зарегистрированного сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="de0b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de0b1-106">SYNTAX</span></span>

### <span data-ttu-id="de0b1-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="de0b1-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="de0b1-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="de0b1-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="de0b1-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de0b1-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="de0b1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de0b1-110">DESCRIPTION</span></span>

<span data-ttu-id="de0b1-111">`Set-PSSessionConfiguration`Командлет изменяет свойства конфигураций сеанса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="de0b1-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="de0b1-112">Используйте **Name** параметр, чтобы указать конфигурацию сеанса, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="de0b1-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="de0b1-113">С помощью других параметров укажите новые значения свойств конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="de0b1-114">Чтобы удалить значение свойства из конфигурации и использовать значение по умолчанию, введите пустую строку ("") или значение `$Null` для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="de0b1-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="de0b1-115">Начиная с PowerShell 3,0 можно использовать файл конфигурации сеанса для определения конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="de0b1-116">Это простой метод для настройки и изменения свойств сеансов, которые используют одну конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="de0b1-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="de0b1-117">Чтобы указать файл конфигурации сеанса, используйте параметр **path** в `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="de0b1-118">Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="de0b1-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="de0b1-119">Сведения о том, как создать и изменить файл конфигурации сеанса, см. в разделе `New-PSSessionConfigurationFile` командлет.</span><span class="sxs-lookup"><span data-stu-id="de0b1-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="de0b1-120">Конфигурации сеансов определяют среду удаленных сеансов ( **PSSession** ), которые подключаются к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="de0b1-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="de0b1-121">В каждом сеансе **PSSession** используется конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="de0b1-122">Конфигурация сеанса определяет функции **PSSession** , такие как модули, доступные в сеансе, командлеты, которые разрешено запускать, языковой режим, квоты и время ожидания.</span><span class="sxs-lookup"><span data-stu-id="de0b1-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="de0b1-123">Дескриптор безопасности конфигурации сеанса определяет, кто может использовать конфигурацию сеанса для подключения к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="de0b1-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="de0b1-124">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="de0b1-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="de0b1-125">Чтобы просмотреть свойства конфигурации сеанса, используйте `Get-PSSessionConfiguration` командлет или поставщик WSMan.</span><span class="sxs-lookup"><span data-stu-id="de0b1-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="de0b1-126">Для получения дополнительных сведений о поставщике WSMan введите `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="de0b1-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="de0b1-127">EXAMPLES</span></span>

### <span data-ttu-id="de0b1-128">Пример 1. изменение состояния подразделения потока</span><span class="sxs-lookup"><span data-stu-id="de0b1-128">Example 1: Change the thread apartment state</span></span>

```
PS C:\> Set-PSSessionConfiguration -Name "MaintenanceShell" -ThreadApartmentState STA
```

<span data-ttu-id="de0b1-129">Эта команда изменяет состояние модели "apartment" потока в конфигурации MaintenanceShell на STA.</span><span class="sxs-lookup"><span data-stu-id="de0b1-129">This command changes the thread apartment state in the MaintenanceShell configuration to STA.</span></span>
<span data-ttu-id="de0b1-130">Изменение вступает в силу при перезапуске службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-130">The change is effective when you restart the **WinRM** service.</span></span>

### <span data-ttu-id="de0b1-131">Пример 2. Создание и изменение конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="de0b1-131">Example 2: Create and change a session configuration</span></span>

<span data-ttu-id="de0b1-132">В этом примере показано, как добавить и удалить скрипт запуска из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-132">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="de0b1-133">Первая команда создает конфигурацию **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-133">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="de0b1-134">Вторая команда добавляет `AdminConfig.ps1` скрипт в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="de0b1-134">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="de0b1-135">Изменение вступает в силу при перезапуске **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-135">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="de0b1-136">Третья команда удаляет `AdminConfig.ps1` скрипт из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-136">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="de0b1-137">Пример 3. Отображение результатов</span><span class="sxs-lookup"><span data-stu-id="de0b1-137">Example 3: Display results</span></span>

<span data-ttu-id="de0b1-138">В этом примере значение свойства **максимумрецеиведобжектсиземб** увеличивается на 20.</span><span class="sxs-lookup"><span data-stu-id="de0b1-138">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="de0b1-139">Эта команда также предлагает перезапустить службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-139">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="de0b1-140">Изменения вступают в силу только после перезапуска службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-140">The change is not effective until the **WinRM** service is restarted.</span></span>

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### <span data-ttu-id="de0b1-141">Пример 4. Отображение результатов различными способами</span><span class="sxs-lookup"><span data-stu-id="de0b1-141">Example 4: Display results in different ways</span></span>

<span data-ttu-id="de0b1-142">В этом примере `Set-PSSessionConfiguration` изменяет сценарий запуска в конфигурации сеанса **MaintenanceShell** на `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-142">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="de0b1-143">В выходных данных отобразится изменение и будет предложено перезапустить службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-143">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="de0b1-144">Ответ: "y" (да).</span><span class="sxs-lookup"><span data-stu-id="de0b1-144">The response is "y" (yes).</span></span>

<span data-ttu-id="de0b1-145">`Get-PSSessionConfiguration` Возвращает конфигурацию сеанса **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-145">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="de0b1-146">Оператор конвейера (|) отправляет результаты команды в `Format-List` , где отображаются все свойства объекта конфигурации в списке.</span><span class="sxs-lookup"><span data-stu-id="de0b1-146">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="de0b1-147">Затем с помощью поставщика WSMan мы видим параметры инициализации для конфигурации **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-147">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="de0b1-148">`Get-ChildItem` (псевдоним `dir` ) Возвращает дочерние элементы в узле **инитиализатионпараметерс** для подключаемого модуля **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-148">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="de0b1-149">Для получения дополнительных сведений о поставщике WSMan введите `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-149">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```
PS> Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PS> Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *

xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :

PS> dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="de0b1-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de0b1-150">PARAMETERS</span></span>

### <span data-ttu-id="de0b1-151">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="de0b1-151">-AccessMode</span></span>

<span data-ttu-id="de0b1-152">Включает и отключает конфигурацию сеанса и определяет возможность ее использования для удаленных или локальных сеансов компьютера.</span><span class="sxs-lookup"><span data-stu-id="de0b1-152">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="de0b1-153">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="de0b1-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de0b1-154">Отключена.</span><span class="sxs-lookup"><span data-stu-id="de0b1-154">Disabled.</span></span> <span data-ttu-id="de0b1-155">отключает конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-155">Disables the session configuration.</span></span> <span data-ttu-id="de0b1-156">Использовать конфигурацию для локального или удаленного доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="de0b1-156">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="de0b1-157">Это значение задает для свойства **Enabled** конфигурации сеанса () значение `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` **false**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-157">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="de0b1-158">Локальный.</span><span class="sxs-lookup"><span data-stu-id="de0b1-158">Local.</span></span> <span data-ttu-id="de0b1-159">Добавляет запись **Network_Deny_All** в дескриптор безопасности конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-159">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="de0b1-160">Пользователи локального компьютера могут использовать конфигурацию сеанса для создания локального сеанса замыкания на себя на том же компьютере, но удаленным пользователям отказано в доступе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-160">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="de0b1-161">Удаленный.</span><span class="sxs-lookup"><span data-stu-id="de0b1-161">Remote.</span></span> <span data-ttu-id="de0b1-162">Удаляет записи **Deny_All** и **Network_Deny_All** из дескрипторов безопасности конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-162">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="de0b1-163">Пользователи локальных и удаленных компьютеров могут применять конфигурацию сеанса для создания сеансов и выполнения команд на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="de0b1-163">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="de0b1-164">Значение по умолчанию — **Remote**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-164">The default value is **Remote**.</span></span>

<span data-ttu-id="de0b1-165">Другие командлеты могут переопределить значение этого параметра позже.</span><span class="sxs-lookup"><span data-stu-id="de0b1-165">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="de0b1-166">Например, `Enable-PSRemoting` командлет включает все конфигурации сеанса на компьютере и разрешает удаленный доступ к ним, а `Disable-PSRemoting` командлет разрешает только локальный доступ ко всем конфигурациям сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="de0b1-166">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="de0b1-167">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-167">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-168">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="de0b1-168">-ApplicationBase</span></span>

<span data-ttu-id="de0b1-169">Указывает путь к файлу сборки ( \* . dll), указанному в значении параметра **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-169">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="de0b1-170">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="de0b1-170">-AssemblyName</span></span>

<span data-ttu-id="de0b1-171">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="de0b1-171">Specifies the assembly name.</span></span> <span data-ttu-id="de0b1-172">Этот командлет создает конфигурацию сеанса на основе класса, определенного в сборке.</span><span class="sxs-lookup"><span data-stu-id="de0b1-172">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="de0b1-173">Введите имя файла или полный путь к DLL-файлу сборки, который определяет конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-173">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="de0b1-174">Если введено только имя файла, можно ввести путь в значении параметра **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-174">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="de0b1-175">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="de0b1-175">-ConfigurationTypeName</span></span>

<span data-ttu-id="de0b1-176">Указывает тип конфигурации сеанса, который определен в сборке в параметре **AssemblyName**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-176">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="de0b1-177">Задаваемый тип должен реализовывать класс **System.Management.Automation.Remoting.PSSessionConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-177">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="de0b1-178">Этот параметр является обязательным, если указано имя сборки.</span><span class="sxs-lookup"><span data-stu-id="de0b1-178">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="de0b1-179">-Force</span><span class="sxs-lookup"><span data-stu-id="de0b1-179">-Force</span></span>

<span data-ttu-id="de0b1-180">Подавляет все запросы пользователя и перезапускает службу **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-180">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="de0b1-181">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="de0b1-181">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="de0b1-182">Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-182">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="de0b1-183">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="de0b1-183">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="de0b1-184">Задает ограничение на объем данных, которые могут быть отправлены на этот компьютер в любой отдельной удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="de0b1-184">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="de0b1-185">Введите размер данных в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="de0b1-185">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="de0b1-186">Значение по умолчанию — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="de0b1-186">The default is 50 MB.</span></span>

<span data-ttu-id="de0b1-187">Если ограничение на размер данных определяется в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-187">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="de0b1-188">Значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="de0b1-188">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de0b1-189">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="de0b1-189">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="de0b1-190">Указывает ограничения на объем данных, которые могут быть отправлены на этот компьютер в любом отдельном объекте.</span><span class="sxs-lookup"><span data-stu-id="de0b1-190">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="de0b1-191">Введите размер данных в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="de0b1-191">Enter the data size in megabytes.</span></span> <span data-ttu-id="de0b1-192">Значение по умолчанию — 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="de0b1-192">The default is 10 MB.</span></span>

<span data-ttu-id="de0b1-193">Если ограничение размера объекта определено в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-193">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="de0b1-194">Значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="de0b1-194">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="de0b1-195">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="de0b1-195">-ModulesToImport</span></span>

<span data-ttu-id="de0b1-196">Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-196">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="de0b1-197">Введите имена модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="de0b1-197">Enter the module and snap-in names.</span></span>

<span data-ttu-id="de0b1-198">По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в сеансы, но если командлеты не исключены, можно использовать `Import-Module` командлеты и Add-PSSnapin, чтобы добавить модули и оснастки в сеанс.</span><span class="sxs-lookup"><span data-stu-id="de0b1-198">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="de0b1-199">Модули, указанные в этом значении параметра, импортируются в дополнение к модулям, указанным в файле конфигурации сеанса ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="de0b1-199">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="de0b1-200">При этом параметры в файле конфигурации сеанса могут скрывать экспортируемые модулями команды или запрещать их использование.</span><span class="sxs-lookup"><span data-stu-id="de0b1-200">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="de0b1-201">Модули, указанные в этом значении параметра, заменяют список модулей, указанных **ModulesToImport** с помощью параметра ModulesToImport `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="de0b1-201">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="de0b1-202">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-202">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-203">-Name</span><span class="sxs-lookup"><span data-stu-id="de0b1-203">-Name</span></span>

<span data-ttu-id="de0b1-204">Указывает имя конфигурации сеанса, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="de0b1-204">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="de0b1-205">Этот параметр не может использоваться для изменения имени конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-205">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="de0b1-206">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="de0b1-206">-NoServiceRestart</span></span>

<span data-ttu-id="de0b1-207">Не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.</span><span class="sxs-lookup"><span data-stu-id="de0b1-207">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="de0b1-208">По умолчанию при выполнении `Set-PSSessionConfiguration` будет предложено перезапустить службу **WinRM** , чтобы обеспечить эффективную настройку нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-208">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="de0b1-209">Пока служба **WinRM** не будет перезапущена, Новая конфигурация сеанса не вступит в силу.</span><span class="sxs-lookup"><span data-stu-id="de0b1-209">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="de0b1-210">Чтобы перезапустить службу **WinRM** без запроса, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-210">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="de0b1-211">Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="de0b1-211">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="de0b1-212">-Path</span><span class="sxs-lookup"><span data-stu-id="de0b1-212">-Path</span></span>

<span data-ttu-id="de0b1-213">Указывает путь к файлу конфигурации сеанса (. pssc), например, созданному `New-PSSessionConfigurationFile` командлетом.</span><span class="sxs-lookup"><span data-stu-id="de0b1-213">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="de0b1-214">Если путь не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="de0b1-214">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="de0b1-215">Сведения о том, как изменить файл конфигурации сеанса, см. в разделе справки по `New-PSSessionConfigurationFile` командлету.</span><span class="sxs-lookup"><span data-stu-id="de0b1-215">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="de0b1-216">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-217">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="de0b1-217">-PSVersion</span></span>

<span data-ttu-id="de0b1-218">Указывает версию PowerShell в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-218">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="de0b1-219">Значение этого параметра имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-219">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="de0b1-220">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-220">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-221">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="de0b1-221">-RunAsCredential</span></span>

<span data-ttu-id="de0b1-222">Указывает учетные данные для команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-222">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="de0b1-223">По умолчанию команды выполняются с разрешениями текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="de0b1-223">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="de0b1-224">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-224">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-225">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="de0b1-225">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="de0b1-226">Задает другую строку SDDL для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-226">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="de0b1-227">Эта строка определяет разрешения, необходимые для использования новой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-227">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="de0b1-228">Чтобы использовать конфигурацию сеанса в сеансе, пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-228">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="de0b1-229">Чтобы использовать для конфигурации дескриптор безопасности по умолчанию, введите пустую строку ("") или значение `$Null` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-229">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="de0b1-230">Значение по умолчанию — корневой SDDL на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="de0b1-230">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="de0b1-231">Если дескриптор безопасности является сложным, рассмотрите возможность использования параметра **ShowSecurityDescriptorUI** вместо этого.</span><span class="sxs-lookup"><span data-stu-id="de0b1-231">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="de0b1-232">Использовать оба параметра в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="de0b1-232">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="de0b1-233">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="de0b1-233">-SessionTypeOption</span></span>

<span data-ttu-id="de0b1-234">Задает параметры для конкретного типа конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-234">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="de0b1-235">Введите объект параметров типа сеанса, например объект **PSWorkflowExecutionOption** , `New-PSWorkflowExecutionOption` возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="de0b1-235">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="de0b1-236">Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-236">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="de0b1-237">Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-237">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="de0b1-238">При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-238">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="de0b1-239">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-239">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-240">-ShowSecurityDescriptorUI</span><span class="sxs-lookup"><span data-stu-id="de0b1-240">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="de0b1-241">Указывает, что этот командлет является страницей свойств, помогающей создать новый SDDL для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-241">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="de0b1-242">Страница свойств появляется после выполнения `Set-PSSessionConfiguration` команды и перезапуска службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="de0b1-242">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="de0b1-243">При установке разрешений для конфигурации Помните, что пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для использования конфигурации сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-243">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="de0b1-244">Использовать этот параметр и параметр **SecurityDescriptorSDDL** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="de0b1-244">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="de0b1-245">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="de0b1-245">-StartupScript</span></span>

<span data-ttu-id="de0b1-246">Указывает скрипт запуска для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-246">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="de0b1-247">Введите полный путь к скрипту PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de0b1-247">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="de0b1-248">Указанный скрипт выполняется в новом сеансе, для которого используется данная конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-248">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="de0b1-249">Чтобы удалить скрипт запуска из конфигурации сеанса, введите пустую строку ("") или значение `$Null` .</span><span class="sxs-lookup"><span data-stu-id="de0b1-249">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="de0b1-250">Для дальнейшей настройки сеанса пользователя можно использовать сценарий запуска.</span><span class="sxs-lookup"><span data-stu-id="de0b1-250">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="de0b1-251">Если скрипт создает ошибку, даже устранимую ошибку, сеанс не создается и `New-PSSession` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="de0b1-251">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="de0b1-252">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="de0b1-252">-ThreadApartmentState</span></span>

<span data-ttu-id="de0b1-253">Задает параметр состояния апартамента для потоков в сеансе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-253">Specifies the apartment state setting for the threads in the session.</span></span>
<span data-ttu-id="de0b1-254">Допустимые значения для этого параметра: STA, MTA и Unknown.</span><span class="sxs-lookup"><span data-stu-id="de0b1-254">The acceptable values for this parameter are: STA, MTA, and Unknown.</span></span>
<span data-ttu-id="de0b1-255">Значение по умолчанию — Unknown.</span><span class="sxs-lookup"><span data-stu-id="de0b1-255">The default value is Unknown.</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:
Accepted values: STA, MTA, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de0b1-256">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="de0b1-256">-ThreadOptions</span></span>

<span data-ttu-id="de0b1-257">Указывает настройку параметров потока в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de0b1-257">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="de0b1-258">Этот параметр определяет, как потоки создаются и используются при выполнении команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-258">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="de0b1-259">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="de0b1-259">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de0b1-260">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="de0b1-260">Default</span></span>
- <span data-ttu-id="de0b1-261">реусесреад</span><span class="sxs-lookup"><span data-stu-id="de0b1-261">ReuseThread</span></span>
- <span data-ttu-id="de0b1-262">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="de0b1-262">UseCurrentThread</span></span>
- <span data-ttu-id="de0b1-263">усеневсреад</span><span class="sxs-lookup"><span data-stu-id="de0b1-263">UseNewThread</span></span>

<span data-ttu-id="de0b1-264">Значение по умолчанию — **UseCurrentThread**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-264">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="de0b1-265">Дополнительные сведения см. в разделе [перечисление пссреадоптионс](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="de0b1-265">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="de0b1-266">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="de0b1-266">-TransportOption</span></span>

<span data-ttu-id="de0b1-267">Задает параметры транспорта для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-267">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="de0b1-268">Введите объект параметров транспорта, например объект **всманконфигуратионоптион** , `New-PSTransportOption` возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="de0b1-268">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="de0b1-269">Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-269">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="de0b1-270">Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-270">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="de0b1-271">При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-271">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="de0b1-272">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-272">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-273">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="de0b1-273">-UseSharedProcess</span></span>

<span data-ttu-id="de0b1-274">Используйте только один процесс для размещения всех сеансов, запущенных одним и тем же пользователем, и используйте ту же конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-274">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="de0b1-275">По умолчанию каждый сеанс размещается в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="de0b1-275">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="de0b1-276">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-276">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="de0b1-277">-Confirm</span><span class="sxs-lookup"><span data-stu-id="de0b1-277">-Confirm</span></span>

<span data-ttu-id="de0b1-278">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="de0b1-278">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="de0b1-279">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="de0b1-279">-WhatIf</span></span>

<span data-ttu-id="de0b1-280">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="de0b1-280">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="de0b1-281">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="de0b1-281">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="de0b1-282">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="de0b1-282">CommonParameters</span></span>

<span data-ttu-id="de0b1-283">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de0b1-283">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de0b1-284">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de0b1-284">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de0b1-285">Входные данные</span><span class="sxs-lookup"><span data-stu-id="de0b1-285">INPUTS</span></span>

### <span data-ttu-id="de0b1-286">Нет</span><span class="sxs-lookup"><span data-stu-id="de0b1-286">None</span></span>

<span data-ttu-id="de0b1-287">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="de0b1-287">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="de0b1-288">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="de0b1-288">OUTPUTS</span></span>

### <span data-ttu-id="de0b1-289">Microsoft.WSMan.Management.WSManConfigLeafElement</span><span class="sxs-lookup"><span data-stu-id="de0b1-289">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="de0b1-290">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="de0b1-290">NOTES</span></span>

<span data-ttu-id="de0b1-291">Чтобы запустить этот командлет, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="de0b1-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="de0b1-292">`Set-PSSessionConfiguration`Командлет не изменяет имя конфигурации, а поставщик **WSMan** не поддерживает этот `Rename-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="de0b1-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="de0b1-293">Чтобы изменить имя конфигурации сеанса, используйте `Unregister-PSSessionConfiguration` командлет для удаления конфигурации, а затем используйте `Register-PSSessionConfiguration` командлет для создания и регистрации новой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="de0b1-294">С помощью `Set-PSSessionConfiguration` командлета можно изменить конфигурации сеанса Microsoft. PowerShell и Microsoft. PowerShell32 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de0b1-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="de0b1-295">Они не защищены.</span><span class="sxs-lookup"><span data-stu-id="de0b1-295">They are not protected.</span></span> <span data-ttu-id="de0b1-296">Чтобы вернуться к исходной версии конфигурации сеанса по умолчанию, используйте командлет, `Unregister-PSSessionConfiguration` чтобы удалить конфигурацию сеанса по умолчанию, а затем используйте `Enable-PSRemoting` командлет для его восстановления.</span><span class="sxs-lookup"><span data-stu-id="de0b1-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="de0b1-297">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="de0b1-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="de0b1-298">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="de0b1-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="de0b1-299">Вы можете использовать команды на диске WSMan:, чтобы изменить свойства конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="de0b1-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="de0b1-300">Однако нельзя использовать диск WSMan: в PowerShell 2,0 для изменения свойств конфигурации сеанса, которые представлены в PowerShell 3,0, например **аутпутбуфферингмоде**.</span><span class="sxs-lookup"><span data-stu-id="de0b1-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="de0b1-301">Команды Windows PowerShell 2.0 не вызывают ошибку, но они являются неэффективными.</span><span class="sxs-lookup"><span data-stu-id="de0b1-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="de0b1-302">Чтобы изменить свойства, появившиеся в PowerShell 3,0, используйте диск WSMan: в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="de0b1-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="de0b1-303">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="de0b1-303">RELATED LINKS</span></span>

[<span data-ttu-id="de0b1-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-305">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de0b1-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="de0b1-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="de0b1-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="de0b1-309">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="de0b1-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="de0b1-310">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="de0b1-310">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="de0b1-311">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-311">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-312">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-312">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-313">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="de0b1-313">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="de0b1-314">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="de0b1-314">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="de0b1-315">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="de0b1-315">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="de0b1-316">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="de0b1-316">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="de0b1-317">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="de0b1-317">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
