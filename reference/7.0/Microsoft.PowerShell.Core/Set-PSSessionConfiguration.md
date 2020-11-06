---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: c1d0d0bc2452e7f05fd47574dedeb4a1b9686fad
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229997"
---
# <span data-ttu-id="70120-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="70120-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="70120-104">SYNOPSIS</span></span>
<span data-ttu-id="70120-105">Изменяет свойства конфигурации зарегистрированного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="70120-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70120-106">SYNTAX</span></span>

### <span data-ttu-id="70120-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="70120-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70120-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="70120-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70120-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="70120-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="70120-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="70120-110">DESCRIPTION</span></span>

<span data-ttu-id="70120-111">`Set-PSSessionConfiguration`Командлет изменяет свойства конфигураций сеанса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="70120-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="70120-112">Используйте **Name** параметр, чтобы указать конфигурацию сеанса, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="70120-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="70120-113">С помощью других параметров укажите новые значения свойств конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="70120-114">Чтобы удалить значение свойства из конфигурации и использовать значение по умолчанию, введите пустую строку ("") или значение `$Null` для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="70120-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="70120-115">Начиная с PowerShell 3,0 можно использовать файл конфигурации сеанса для определения конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="70120-116">Это простой метод для настройки и изменения свойств сеансов, которые используют одну конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="70120-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="70120-117">Чтобы указать файл конфигурации сеанса, используйте параметр **path** в `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="70120-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="70120-118">Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="70120-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="70120-119">Сведения о том, как создать и изменить файл конфигурации сеанса, см. в разделе `New-PSSessionConfigurationFile` командлет.</span><span class="sxs-lookup"><span data-stu-id="70120-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="70120-120">Конфигурации сеансов определяют среду удаленных сеансов ( **PSSession** ), которые подключаются к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="70120-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="70120-121">В каждом сеансе **PSSession** используется конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="70120-122">Конфигурация сеанса определяет функции **PSSession** , такие как модули, доступные в сеансе, командлеты, которые разрешено запускать, языковой режим, квоты и время ожидания.</span><span class="sxs-lookup"><span data-stu-id="70120-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="70120-123">Дескриптор безопасности конфигурации сеанса определяет, кто может использовать конфигурацию сеанса для подключения к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="70120-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="70120-124">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="70120-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="70120-125">Чтобы просмотреть свойства конфигурации сеанса, используйте `Get-PSSessionConfiguration` командлет или поставщик WSMan.</span><span class="sxs-lookup"><span data-stu-id="70120-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="70120-126">Для получения дополнительных сведений о поставщике WSMan введите `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="70120-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="70120-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="70120-127">EXAMPLES</span></span>

### <span data-ttu-id="70120-128">Пример 1. Создание и изменение конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="70120-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="70120-129">В этом примере показано, как добавить и удалить скрипт запуска из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="70120-130">Первая команда создает конфигурацию **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="70120-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="70120-131">Вторая команда добавляет `AdminConfig.ps1` скрипт в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="70120-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="70120-132">Изменение вступает в силу при перезапуске **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="70120-132">The change is effective when you restart **WinRM** .</span></span>
<span data-ttu-id="70120-133">Третья команда удаляет `AdminConfig.ps1` скрипт из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="70120-134">Пример 2. Отображение результатов</span><span class="sxs-lookup"><span data-stu-id="70120-134">Example 2: Display results</span></span>

<span data-ttu-id="70120-135">В этом примере значение свойства **максимумрецеиведобжектсиземб** увеличивается на 20.</span><span class="sxs-lookup"><span data-stu-id="70120-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="70120-136">Эта команда также предлагает перезапустить службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="70120-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="70120-137">Изменения вступают в силу только после перезапуска службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="70120-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="70120-138">Пример 3. Отображение результатов различными способами</span><span class="sxs-lookup"><span data-stu-id="70120-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="70120-139">В этом примере `Set-PSSessionConfiguration` изменяет сценарий запуска в конфигурации сеанса **MaintenanceShell** на `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="70120-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="70120-140">В выходных данных отобразится изменение и будет предложено перезапустить службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="70120-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="70120-141">Ответ: "y" (да).</span><span class="sxs-lookup"><span data-stu-id="70120-141">The response is "y" (yes).</span></span>

<span data-ttu-id="70120-142">`Get-PSSessionConfiguration` Возвращает конфигурацию сеанса **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="70120-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="70120-143">Оператор конвейера (|) отправляет результаты команды в `Format-List` , где отображаются все свойства объекта конфигурации в списке.</span><span class="sxs-lookup"><span data-stu-id="70120-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="70120-144">Затем с помощью поставщика WSMan мы видим параметры инициализации для конфигурации **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="70120-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="70120-145">`Get-ChildItem` (псевдоним `dir` ) Возвращает дочерние элементы в узле **инитиализатионпараметерс** для подключаемого модуля **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="70120-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="70120-146">Для получения дополнительных сведений о поставщике WSMan введите `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="70120-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
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
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="70120-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70120-147">PARAMETERS</span></span>

### <span data-ttu-id="70120-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="70120-148">-AccessMode</span></span>

<span data-ttu-id="70120-149">Включает и отключает конфигурацию сеанса и определяет возможность ее использования для удаленных или локальных сеансов компьютера.</span><span class="sxs-lookup"><span data-stu-id="70120-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="70120-150">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="70120-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="70120-151">Отключена.</span><span class="sxs-lookup"><span data-stu-id="70120-151">Disabled.</span></span> <span data-ttu-id="70120-152">отключает конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-152">Disables the session configuration.</span></span> <span data-ttu-id="70120-153">Использовать конфигурацию для локального или удаленного доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="70120-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="70120-154">Это значение задает для свойства **Enabled** конфигурации сеанса () значение `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` **false** .</span><span class="sxs-lookup"><span data-stu-id="70120-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False** .</span></span>
- <span data-ttu-id="70120-155">Локальный.</span><span class="sxs-lookup"><span data-stu-id="70120-155">Local.</span></span> <span data-ttu-id="70120-156">Добавляет запись **Network_Deny_All** в дескриптор безопасности конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="70120-157">Пользователи локального компьютера могут использовать конфигурацию сеанса для создания локального сеанса замыкания на себя на том же компьютере, но удаленным пользователям отказано в доступе.</span><span class="sxs-lookup"><span data-stu-id="70120-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="70120-158">Удаленный.</span><span class="sxs-lookup"><span data-stu-id="70120-158">Remote.</span></span> <span data-ttu-id="70120-159">Удаляет записи **Deny_All** и **Network_Deny_All** из дескрипторов безопасности конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="70120-160">Пользователи локальных и удаленных компьютеров могут применять конфигурацию сеанса для создания сеансов и выполнения команд на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="70120-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="70120-161">Значение по умолчанию — **Remote** .</span><span class="sxs-lookup"><span data-stu-id="70120-161">The default value is **Remote** .</span></span>

<span data-ttu-id="70120-162">Другие командлеты могут переопределить значение этого параметра позже.</span><span class="sxs-lookup"><span data-stu-id="70120-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="70120-163">Например, `Enable-PSRemoting` командлет включает все конфигурации сеанса на компьютере и разрешает удаленный доступ к ним, а `Disable-PSRemoting` командлет разрешает только локальный доступ ко всем конфигурациям сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="70120-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="70120-164">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="70120-165">-ApplicationBase</span></span>

<span data-ttu-id="70120-166">Указывает путь к файлу сборки ( \* . dll), указанному в значении параметра **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="70120-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="70120-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="70120-167">-AssemblyName</span></span>

<span data-ttu-id="70120-168">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="70120-168">Specifies the assembly name.</span></span> <span data-ttu-id="70120-169">Этот командлет создает конфигурацию сеанса на основе класса, определенного в сборке.</span><span class="sxs-lookup"><span data-stu-id="70120-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="70120-170">Введите имя файла или полный путь к DLL-файлу сборки, который определяет конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="70120-171">Если введено только имя файла, можно ввести путь в значении параметра **ApplicationBase** .</span><span class="sxs-lookup"><span data-stu-id="70120-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="70120-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="70120-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="70120-173">Указывает тип конфигурации сеанса, который определен в сборке в параметре **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="70120-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="70120-174">Задаваемый тип должен реализовывать класс **System.Management.Automation.Remoting.PSSessionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="70120-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="70120-175">Этот параметр является обязательным, если указано имя сборки.</span><span class="sxs-lookup"><span data-stu-id="70120-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="70120-176">-Force</span><span class="sxs-lookup"><span data-stu-id="70120-176">-Force</span></span>

<span data-ttu-id="70120-177">Подавляет все запросы пользователя и перезапускает службу **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="70120-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="70120-178">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="70120-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="70120-179">Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="70120-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="70120-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="70120-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="70120-181">Задает ограничение на объем данных, которые могут быть отправлены на этот компьютер в любой отдельной удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="70120-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="70120-182">Введите размер данных в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="70120-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="70120-183">Значение по умолчанию — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="70120-183">The default is 50 MB.</span></span>

<span data-ttu-id="70120-184">Если ограничение на размер данных определяется в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="70120-185">Значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="70120-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="70120-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="70120-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="70120-187">Указывает ограничения на объем данных, которые могут быть отправлены на этот компьютер в любом отдельном объекте.</span><span class="sxs-lookup"><span data-stu-id="70120-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="70120-188">Введите размер данных в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="70120-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="70120-189">Значение по умолчанию — 10 МБ.</span><span class="sxs-lookup"><span data-stu-id="70120-189">The default is 10 MB.</span></span>

<span data-ttu-id="70120-190">Если ограничение размера объекта определено в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="70120-191">Значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="70120-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="70120-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="70120-192">-ModulesToImport</span></span>

<span data-ttu-id="70120-193">Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="70120-194">Введите имена модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="70120-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="70120-195">По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в сеансы, но если командлеты не исключены, можно использовать `Import-Module` командлеты и Add-PSSnapin, чтобы добавить модули и оснастки в сеанс.</span><span class="sxs-lookup"><span data-stu-id="70120-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="70120-196">Модули, указанные в этом значении параметра, импортируются в дополнение к модулям, указанным в файле конфигурации сеанса ( `New-PSSessionConfigurationFile` ).</span><span class="sxs-lookup"><span data-stu-id="70120-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="70120-197">При этом параметры в файле конфигурации сеанса могут скрывать экспортируемые модулями команды или запрещать их использование.</span><span class="sxs-lookup"><span data-stu-id="70120-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="70120-198">Модули, указанные в этом значении параметра, заменяют список модулей, указанных **ModulesToImport** с помощью параметра ModulesToImport `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="70120-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="70120-199">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-200">-Name</span><span class="sxs-lookup"><span data-stu-id="70120-200">-Name</span></span>

<span data-ttu-id="70120-201">Указывает имя конфигурации сеанса, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="70120-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="70120-202">Этот параметр не может использоваться для изменения имени конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="70120-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="70120-203">-NoServiceRestart</span></span>

<span data-ttu-id="70120-204">Не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.</span><span class="sxs-lookup"><span data-stu-id="70120-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="70120-205">По умолчанию при выполнении `Set-PSSessionConfiguration` будет предложено перезапустить службу **WinRM** , чтобы обеспечить эффективную настройку нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="70120-206">Пока служба **WinRM** не будет перезапущена, Новая конфигурация сеанса не вступит в силу.</span><span class="sxs-lookup"><span data-stu-id="70120-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="70120-207">Чтобы перезапустить службу **WinRM** без запроса, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="70120-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="70120-208">Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="70120-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="70120-209">-Path</span><span class="sxs-lookup"><span data-stu-id="70120-209">-Path</span></span>

<span data-ttu-id="70120-210">Указывает путь к файлу конфигурации сеанса (. pssc), например, созданному `New-PSSessionConfigurationFile` командлетом.</span><span class="sxs-lookup"><span data-stu-id="70120-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="70120-211">Если путь не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="70120-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="70120-212">Сведения о том, как изменить файл конфигурации сеанса, см. в разделе справки по `New-PSSessionConfigurationFile` командлету.</span><span class="sxs-lookup"><span data-stu-id="70120-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="70120-213">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="70120-214">-PSVersion</span></span>

<span data-ttu-id="70120-215">Указывает версию PowerShell в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="70120-216">Значение этого параметра имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="70120-217">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="70120-218">-RunAsCredential</span></span>

<span data-ttu-id="70120-219">Указывает учетные данные для команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70120-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="70120-220">По умолчанию команды выполняются с разрешениями текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="70120-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="70120-221">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-222">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="70120-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="70120-223">Задает другую строку SDDL для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="70120-224">Эта строка определяет разрешения, необходимые для использования новой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="70120-225">Чтобы использовать конфигурацию сеанса в сеансе, пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="70120-226">Чтобы использовать для конфигурации дескриптор безопасности по умолчанию, введите пустую строку ("") или значение `$Null` .</span><span class="sxs-lookup"><span data-stu-id="70120-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="70120-227">Значение по умолчанию — корневой SDDL на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="70120-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="70120-228">Если дескриптор безопасности является сложным, рассмотрите возможность использования параметра **ShowSecurityDescriptorUI** вместо этого.</span><span class="sxs-lookup"><span data-stu-id="70120-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="70120-229">Использовать оба параметра в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="70120-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="70120-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="70120-230">-SessionTypeOption</span></span>

<span data-ttu-id="70120-231">Задает параметры для конкретного типа конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="70120-232">Введите объект параметров типа сеанса, например объект **PSWorkflowExecutionOption** , `New-PSWorkflowExecutionOption` возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="70120-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="70120-233">Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="70120-234">Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="70120-235">При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="70120-236">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-237">-ShowSecurityDescriptorUI</span><span class="sxs-lookup"><span data-stu-id="70120-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="70120-238">Указывает, что этот командлет является страницей свойств, помогающей создать новый SDDL для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="70120-239">Страница свойств появляется после выполнения `Set-PSSessionConfiguration` команды и перезапуска службы **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="70120-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="70120-240">При установке разрешений для конфигурации Помните, что пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для использования конфигурации сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70120-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="70120-241">Использовать этот параметр и параметр **SecurityDescriptorSDDL** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="70120-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="70120-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="70120-242">-StartupScript</span></span>

<span data-ttu-id="70120-243">Указывает скрипт запуска для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="70120-244">Введите полный путь к скрипту PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70120-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="70120-245">Указанный скрипт выполняется в новом сеансе, для которого используется данная конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="70120-246">Чтобы удалить скрипт запуска из конфигурации сеанса, введите пустую строку ("") или значение `$Null` .</span><span class="sxs-lookup"><span data-stu-id="70120-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="70120-247">Для дальнейшей настройки сеанса пользователя можно использовать сценарий запуска.</span><span class="sxs-lookup"><span data-stu-id="70120-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="70120-248">Если скрипт создает ошибку, даже устранимую ошибку, сеанс не создается и `New-PSSession` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="70120-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="70120-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="70120-249">-ThreadOptions</span></span>

<span data-ttu-id="70120-250">Указывает настройку параметров потока в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70120-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="70120-251">Этот параметр определяет, как потоки создаются и используются при выполнении команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70120-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="70120-252">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="70120-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="70120-253">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="70120-253">Default</span></span>
- <span data-ttu-id="70120-254">реусесреад</span><span class="sxs-lookup"><span data-stu-id="70120-254">ReuseThread</span></span>
- <span data-ttu-id="70120-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="70120-255">UseCurrentThread</span></span>
- <span data-ttu-id="70120-256">усеневсреад</span><span class="sxs-lookup"><span data-stu-id="70120-256">UseNewThread</span></span>

<span data-ttu-id="70120-257">Значение по умолчанию — **UseCurrentThread** .</span><span class="sxs-lookup"><span data-stu-id="70120-257">The default value is **UseCurrentThread** .</span></span>

<span data-ttu-id="70120-258">Дополнительные сведения см. в разделе [перечисление пссреадоптионс](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="70120-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="70120-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="70120-259">-TransportOption</span></span>

<span data-ttu-id="70120-260">Задает параметры транспорта для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="70120-261">Введите объект параметров транспорта, например объект **всманконфигуратионоптион** , `New-PSTransportOption` возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="70120-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="70120-262">Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="70120-263">Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="70120-264">При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="70120-265">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="70120-266">-UseSharedProcess</span></span>

<span data-ttu-id="70120-267">Используйте только один процесс для размещения всех сеансов, запущенных одним и тем же пользователем, и используйте ту же конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="70120-268">По умолчанию каждый сеанс размещается в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="70120-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="70120-269">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="70120-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="70120-270">-Confirm</span></span>

<span data-ttu-id="70120-271">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="70120-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="70120-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="70120-272">-WhatIf</span></span>

<span data-ttu-id="70120-273">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="70120-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="70120-274">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="70120-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="70120-275">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="70120-275">-ThreadApartmentState</span></span>

<span data-ttu-id="70120-276">Указывает состояние апартамента для используемого модуля потоков.</span><span class="sxs-lookup"><span data-stu-id="70120-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="70120-277">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="70120-277">Acceptable values are:</span></span>

- <span data-ttu-id="70120-278">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="70120-278">Unknown</span></span>
- <span data-ttu-id="70120-279">MTA</span><span class="sxs-lookup"><span data-stu-id="70120-279">MTA</span></span>
- <span data-ttu-id="70120-280">STA</span><span class="sxs-lookup"><span data-stu-id="70120-280">STA</span></span>

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

### <span data-ttu-id="70120-281">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="70120-281">CommonParameters</span></span>

<span data-ttu-id="70120-282">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="70120-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70120-283">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="70120-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="70120-284">Входные данные</span><span class="sxs-lookup"><span data-stu-id="70120-284">INPUTS</span></span>

### <span data-ttu-id="70120-285">Нет</span><span class="sxs-lookup"><span data-stu-id="70120-285">None</span></span>

<span data-ttu-id="70120-286">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="70120-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="70120-287">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="70120-287">OUTPUTS</span></span>

### <span data-ttu-id="70120-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span><span class="sxs-lookup"><span data-stu-id="70120-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="70120-289">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="70120-289">NOTES</span></span>

<span data-ttu-id="70120-290">Чтобы запустить этот командлет, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="70120-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="70120-291">`Set-PSSessionConfiguration`Командлет не изменяет имя конфигурации, а поставщик **WSMan** не поддерживает этот `Rename-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="70120-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="70120-292">Чтобы изменить имя конфигурации сеанса, используйте `Unregister-PSSessionConfiguration` командлет для удаления конфигурации, а затем используйте `Register-PSSessionConfiguration` командлет для создания и регистрации новой конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="70120-293">С помощью `Set-PSSessionConfiguration` командлета можно изменить конфигурации сеанса Microsoft. PowerShell и Microsoft. PowerShell32 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70120-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="70120-294">Они не защищены.</span><span class="sxs-lookup"><span data-stu-id="70120-294">They are not protected.</span></span> <span data-ttu-id="70120-295">Чтобы вернуться к исходной версии конфигурации сеанса по умолчанию, используйте командлет, `Unregister-PSSessionConfiguration` чтобы удалить конфигурацию сеанса по умолчанию, а затем используйте `Enable-PSRemoting` командлет для его восстановления.</span><span class="sxs-lookup"><span data-stu-id="70120-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="70120-296">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="70120-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="70120-297">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="70120-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="70120-298">Вы можете использовать команды на диске WSMan:, чтобы изменить свойства конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70120-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="70120-299">Однако нельзя использовать диск WSMan: в PowerShell 2,0 для изменения свойств конфигурации сеанса, которые представлены в PowerShell 3,0, например **аутпутбуфферингмоде** .</span><span class="sxs-lookup"><span data-stu-id="70120-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="70120-300">Команды Windows PowerShell 2.0 не вызывают ошибку, но они являются неэффективными.</span><span class="sxs-lookup"><span data-stu-id="70120-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="70120-301">Чтобы изменить свойства, появившиеся в PowerShell 3,0, используйте диск WSMan: в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70120-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="70120-302">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="70120-302">RELATED LINKS</span></span>

[<span data-ttu-id="70120-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="70120-304">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="70120-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="70120-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="70120-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="70120-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="70120-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="70120-308">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="70120-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="70120-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="70120-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="70120-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="70120-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="70120-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="70120-312">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="70120-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="70120-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="70120-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="70120-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="70120-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)