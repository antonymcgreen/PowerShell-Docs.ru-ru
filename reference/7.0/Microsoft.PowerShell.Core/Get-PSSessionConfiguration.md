---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: d0c5f0a967ecd6eb07d7268cc9e25be93cc5f34c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230005"
---
# <span data-ttu-id="32bd8-103">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-103">Get-PSSessionConfiguration</span></span>

## <span data-ttu-id="32bd8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="32bd8-104">SYNOPSIS</span></span>
<span data-ttu-id="32bd8-105">Получает зарегистрированные конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-105">Gets the registered session configurations on the computer.</span></span>

## <span data-ttu-id="32bd8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32bd8-106">SYNTAX</span></span>

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="32bd8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32bd8-107">DESCRIPTION</span></span>

<span data-ttu-id="32bd8-108">`Get-PSSessionConfiguration`Командлет возвращает конфигурации сеанса, которые были зарегистрированы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-108">The `Get-PSSessionConfiguration` cmdlet gets the session configurations that have been registered on the local computer.</span></span> <span data-ttu-id="32bd8-109">Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="32bd8-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="32bd8-110">Начиная с версии PowerShell 3,0 можно определить свойства конфигурации сеанса с помощью файла конфигурации сеанса (. pssc).</span><span class="sxs-lookup"><span data-stu-id="32bd8-110">Beginning in PowerShell 3.0, you can define the properties of a session configuration by using a session configuration (.pssc) file.</span></span> <span data-ttu-id="32bd8-111">Эта функция позволяет создавать настраиваемые и ограниченные сеансы, не создавая компьютерную программу.</span><span class="sxs-lookup"><span data-stu-id="32bd8-111">This feature lets you create customized and restricted sessions without writing a computer program.</span></span> <span data-ttu-id="32bd8-112">Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="32bd8-112">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="32bd8-113">Кроме того, начиная с PowerShell 3,0 в объект конфигурации сеанса добавлены новые свойства примечаний, которые `Get-PSSessionConfiguration` возвращают.</span><span class="sxs-lookup"><span data-stu-id="32bd8-113">Also, beginning in PowerShell 3.0, new note properties have been added to the session configuration object that `Get-PSSessionConfiguration` returns.</span></span> <span data-ttu-id="32bd8-114">Эти свойства упрощают просмотр и сравнение конфигураций сеанса для пользователей и авторов конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-114">These properties make it easier for users and session configuration authors to examine and compare session configurations.</span></span>

<span data-ttu-id="32bd8-115">Чтобы создать и зарегистрировать конфигурацию сеанса, используйте `Register-PSSessionConfiguration` командлет.</span><span class="sxs-lookup"><span data-stu-id="32bd8-115">To create and register a session configuration, use the `Register-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="32bd8-116">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="32bd8-116">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="32bd8-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="32bd8-117">EXAMPLES</span></span>

### <span data-ttu-id="32bd8-118">Пример 1. получение конфигураций сеансов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="32bd8-118">Example 1 - Get session configurations on the local computer</span></span>

```powershell
Get-PSSessionConfiguration
```

### <span data-ttu-id="32bd8-119">Пример 2. получение двух конфигураций сеансов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="32bd8-119">Example 2 - Get the two default session configurations</span></span>

<span data-ttu-id="32bd8-120">Команда использует параметр **Name** параметра, `Get-PSSessionConfiguration` чтобы получить только конфигурации сеанса с именами, начинающимися с Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32bd8-120">The command uses the **Name** parameter of `Get-PSSessionConfiguration` to get only the session configurations with names that begin with "Microsoft".</span></span>

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### <span data-ttu-id="32bd8-121">Пример 3. получение свойств и значений конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="32bd8-121">Example 3 - Get the properties and values of a session configuration</span></span>

<span data-ttu-id="32bd8-122">В этом примере показаны свойства и значения свойств конфигурации сеанса, созданные с помощью файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-122">This example shows the properties and property values of a session configuration that was created by using a session configuration file.</span></span>

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

<span data-ttu-id="32bd8-123">В примере командлет используется `Get-PSSessionConfiguration` для получения полной конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-123">The example uses the `Get-PSSessionConfiguration` cmdlet to get the full session configuration.</span></span> <span data-ttu-id="32bd8-124">Оператор конвейера отправляет в командлет полную конфигурацию сеанса `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="32bd8-124">A pipeline operator sends the Full session configuration to the `Format-List` cmdlet.</span></span> <span data-ttu-id="32bd8-125">Параметр **Property** со значением `*` (ALL) направляет `Format-List` Отображение всех свойств и значений объекта в списке.</span><span class="sxs-lookup"><span data-stu-id="32bd8-125">The **Property** parameter with a value of `*` (all) directs `Format-List` to display all the properties and values of the object in a list.</span></span>

<span data-ttu-id="32bd8-126">Выходные данные включают в себя полезную информацию, включая автора конфигурации сеанса, тип сеанса, языковой режим и политику выполнения сеансов, созданных с помощью этой конфигурации сеанса, квоты сеанса и полный путь к файлу конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-126">The output includes useful information, including the author of the session configuration, the session type, language mode, and execution policy of sessions that are created with this session configuration, session quotas, and the full path to the session configuration file.</span></span>

<span data-ttu-id="32bd8-127">Это представление конфигурации сеанса используется для сеансов, которые включают файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-127">This view of a session configuration is used for sessions that include a session configuration file.</span></span>
<span data-ttu-id="32bd8-128">Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="32bd8-128">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

### <span data-ttu-id="32bd8-129">Пример 4. другой способ просмотра конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="32bd8-129">Example 4 - Another way to look at the session configurations</span></span>

<span data-ttu-id="32bd8-130">В этом примере используется `Get-ChildItem` командлет (Alias `dir` ) на диске WSMan: Provider для просмотра содержимого узла подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="32bd8-130">This example uses the `Get-ChildItem` cmdlet (alias `dir`) in the WSMan: provider drive to look at the content of the Plugin node.</span></span> <span data-ttu-id="32bd8-131">Это еще один способ просмотра конфигураций сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-131">This is another way to look at the session configurations on the computer.</span></span>

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="32bd8-132">Узел **подключаемого модуля** содержит объекты **контаинерелемент** (Microsoft. WSMan. Management. всманконфигконтаинерелемент), которые представляют зарегистрированные конфигурации сеансов PowerShell, а также другие подключаемые модули для WS-Management.</span><span class="sxs-lookup"><span data-stu-id="32bd8-132">The **PlugIn** node contains **ContainerElement** objects (Microsoft.WSMan.Management.WSManConfigContainerElement) that represent the registered PowerShell session configurations, along with other plug-ins for WS-Management.</span></span>

### <span data-ttu-id="32bd8-133">Пример 6. Просмотр конфигураций сеансов на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="32bd8-133">Example 6 - View session configurations on a remote computer</span></span>

<span data-ttu-id="32bd8-134">В этом примере показано, как использовать поставщик WSMan для просмотра конфигураций сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-134">This example shows how to use the WSMan provider to view the session configurations on a remote computer.</span></span> <span data-ttu-id="32bd8-135">Этот метод не предоставляет столько сведений `Get-PSSessionConfiguration` , сколько команда, но пользователю не обязательно быть членом группы администраторов для выполнения этого командлета.</span><span class="sxs-lookup"><span data-stu-id="32bd8-135">This method does not provide as much information as a `Get-PSSessionConfiguration` command, but the user does not need to be a member of the Administrators group to run this cmdlet.</span></span>

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="32bd8-136">`Connect-WSMan`Командлет подключается к службе WinRM на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="32bd8-136">The `Connect-WSMan` cmdlet connects to the WinRM service on the Server01 remote computer.</span></span> <span data-ttu-id="32bd8-137">`Get-ChildItem`Командлет (псевдоним `dir` ) для диска WSMan: получает элементы в пути **Server01\Plugin** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-137">The `Get-ChildItem` cmdlet (alias `dir`) of the WSMan: drive gets the items in the **Server01\Plugin** path.</span></span> <span data-ttu-id="32bd8-138">В выходных данных показаны элементы в каталоге подключаемого модуля на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="32bd8-138">The output shows the items in the Plugin directory on the Server01 computer.</span></span> <span data-ttu-id="32bd8-139">Элементы включают конфигурации сеанса, которые являются типом подключаемого модуля WSMan, а также другие типы подключаемых модулей компьютера.</span><span class="sxs-lookup"><span data-stu-id="32bd8-139">The items include the session configurations, which are a type of WSMan plug-in, along with other types of plug-ins on the computer.</span></span>

### <span data-ttu-id="32bd8-140">Пример 7. Получение подробных сведений о конфигурациях сеанса с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="32bd8-140">Example 7 - Get detailed session configurations from a remote computer</span></span>

<span data-ttu-id="32bd8-141">В этом примере показано, как выполнить `Get-PSSessionConfiguration` команду на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-141">This example shows how to run a `Get-PSSessionConfiguration` command on a remote computer.</span></span> <span data-ttu-id="32bd8-142">Для команды требуется включенное делегирование CredSSP в параметрах клиента на локальном компьютере и в параметрах службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-142">The command requires that CredSSP delegation be enabled in the client settings on the local computer and in the service settings on the remote computer.</span></span>

<span data-ttu-id="32bd8-143">Для выполнения команд в этом примере необходимо быть членом группы "Администраторы" на локальном и удаленном компьютерах, и необходимо запустить PowerShell с параметром " **Запуск от имени администратора** ".</span><span class="sxs-lookup"><span data-stu-id="32bd8-143">To run the commands in this example, you must be a member of the Administrators group on the local and remote computers and you must start PowerShell with the **Run as administrator** option.</span></span>

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

<span data-ttu-id="32bd8-144">`Enable-WSManCredSSP`Командлет включает делегирование **CredSSP** на Server01, локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="32bd8-144">The `Enable-WSManCredSSP` cmdlet enables **CredSSP** delegation on Server01, the local computer.</span></span> <span data-ttu-id="32bd8-145">`Connect-WSMan`Командлет подключается к компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="32bd8-145">The `Connect-WSMan` cmdlet connects to Server02 computer.</span></span> <span data-ttu-id="32bd8-146">Это действие добавляет узел для Server02 на диск WSMan: на локальном компьютере, позволяя просматривать и изменять параметры WS-Management на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="32bd8-146">This action adds a node for Server02 to the WSMan: drive on the local computer, allowing you to view and change the WS-Management settings on the Server02 computer.</span></span> <span data-ttu-id="32bd8-147">`Set-Item`Командлет изменяет значение элемента **CredSSP** в узле службы Server02 компьютера на **true** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-147">The `Set-Item` cmdlet changes the value of the **CredSSP** item in the Service node of the Server02 computer to **True** .</span></span> <span data-ttu-id="32bd8-148">Это настраивает параметры службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-148">This configures the service settings on the remote computer.</span></span> <span data-ttu-id="32bd8-149">`Invoke-Command`Командлет выполняет `Get-PSSessionConfiguration` команду на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="32bd8-149">The `Invoke-Command` cmdlet runs the`Get-PSSessionConfiguration` command on the Server02 computer.</span></span> <span data-ttu-id="32bd8-150">Команда использует параметр **Credential** , который использует параметр **Authentication** со значением **CredSSP** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-150">The command uses the **Credential** parameter, and it uses the **Authentication** parameter with a value of **CredSSP** .</span></span> <span data-ttu-id="32bd8-151">В выходных данных показаны конфигурации сеанса на удаленном компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="32bd8-151">The output shows the session configurations on the Server02 remote computer.</span></span>

### <span data-ttu-id="32bd8-152">Пример 8. Получение URI ресурса конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="32bd8-152">Example 8 - Get the resource URI of a session configuration</span></span>

<span data-ttu-id="32bd8-153">Этот пример полезен для задания значения `$PSSessionConfigurationName` привилегированной переменной, которая принимает URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-153">This example is useful for setting the value of the `$PSSessionConfigurationName` preference variable, which takes a resource URI.</span></span>

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

<span data-ttu-id="32bd8-154">`$PSSessionConfigurationName`Переменная указывает конфигурацию по умолчанию, используемую при создании сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-154">The `$PSSessionConfigurationName` variable specifies the default configuration that is used when you create a session.</span></span> <span data-ttu-id="32bd8-155">Эта переменная задается на локальном компьютере, но она указывает конфигурацию на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-155">This variable is set on the local computer, but it specifies a configuration on the remote computer.</span></span> <span data-ttu-id="32bd8-156">Дополнительные сведения о `$PSSessionConfiguration` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="32bd8-156">For more information about the `$PSSessionConfiguration` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="32bd8-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32bd8-157">PARAMETERS</span></span>

### <span data-ttu-id="32bd8-158">-Force</span><span class="sxs-lookup"><span data-stu-id="32bd8-158">-Force</span></span>

<span data-ttu-id="32bd8-159">Скрывает запрос на перезапуск службы WinRM, если служба еще не запущена.</span><span class="sxs-lookup"><span data-stu-id="32bd8-159">Suppresses the prompt to restart the WinRM service, if the service is not already running.</span></span>

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

### <span data-ttu-id="32bd8-160">-Name</span><span class="sxs-lookup"><span data-stu-id="32bd8-160">-Name</span></span>

<span data-ttu-id="32bd8-161">Получает только конфигурации сеанса с указанным именем или шаблоном имени.</span><span class="sxs-lookup"><span data-stu-id="32bd8-161">Gets only the session configurations with the specified name or name pattern.</span></span> <span data-ttu-id="32bd8-162">Введите одно или несколько имен конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-162">Enter one or more session configuration names.</span></span> <span data-ttu-id="32bd8-163">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="32bd8-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="32bd8-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="32bd8-164">CommonParameters</span></span>

<span data-ttu-id="32bd8-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32bd8-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32bd8-166">См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="32bd8-166">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="32bd8-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="32bd8-167">INPUTS</span></span>

### <span data-ttu-id="32bd8-168">Нет</span><span class="sxs-lookup"><span data-stu-id="32bd8-168">None</span></span>

<span data-ttu-id="32bd8-169">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="32bd8-169">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="32bd8-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="32bd8-170">OUTPUTS</span></span>

### <span data-ttu-id="32bd8-171">Microsoft. PowerShell. Commands. Пссессионконфигуратионкоммандс # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-171">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

## <span data-ttu-id="32bd8-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="32bd8-172">NOTES</span></span>

- <span data-ttu-id="32bd8-173">Чтобы запустить этот командлет, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-173">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

- <span data-ttu-id="32bd8-174">Чтобы просмотреть конфигурации сеанса на компьютере, необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-174">To view the session configurations on the computer, you must be a member of the Administrators group on the computer.</span></span>

- <span data-ttu-id="32bd8-175">Чтобы выполнить `Get-PSSessionConfiguration` команду на удаленном компьютере, необходимо включить проверку подлинности поставщика службы безопасности учетных данных (CredSSP) в параметрах клиента на локальном компьютере (с помощью `Enable-WSManCredSSP` командлета) и в параметрах службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="32bd8-175">To run a `Get-PSSessionConfiguration` command on a remote computer, Credential Security Service Provider (CredSSP) authentication must be enabled in the client settings on the local computer (by using the `Enable-WSManCredSSP` cmdlet) and in the service settings on the remote computer.</span></span> <span data-ttu-id="32bd8-176">Кроме того, при установлении удаленного сеанса необходимо использовать значение **CredSSP** параметра **authentication** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-176">Also, you must use the **CredSSP** value of the **Authentication** parameter when establishing the remote session.</span></span> <span data-ttu-id="32bd8-177">В противном случае доступ будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="32bd8-177">Otherwise, access is denied.</span></span>

- <span data-ttu-id="32bd8-178">Свойства примечаний объекта, `Get-PSSessionConfiguration` возвращаемого в объекте, отображаются только в том случае, если они имеют значение.</span><span class="sxs-lookup"><span data-stu-id="32bd8-178">The note properties of the object that `Get-PSSessionConfiguration` returns appear on the object only when they have a value.</span></span> <span data-ttu-id="32bd8-179">Только конфигурации сеансов, созданные с помощью файла конфигурации сеанса, имеют все определенные свойства.</span><span class="sxs-lookup"><span data-stu-id="32bd8-179">Only session configurations that were created by using a session configuration file have all the defined properties.</span></span>

- <span data-ttu-id="32bd8-180">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="32bd8-180">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="32bd8-181">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="32bd8-181">Also, session configurations that use a session configuration file have additional properties.</span></span>

- <span data-ttu-id="32bd8-182">Вы можете использовать команды на диске WSMan:, чтобы изменить свойства конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="32bd8-182">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
  <span data-ttu-id="32bd8-183">Однако нельзя использовать диск WSMan: в PowerShell 2,0 для изменения свойств конфигурации сеанса, которые представлены в PowerShell 3,0, например **аутпутбуфферингмоде** .</span><span class="sxs-lookup"><span data-stu-id="32bd8-183">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="32bd8-184">Команды PowerShell 2,0 не вызывают ошибку, но они неэффективны.</span><span class="sxs-lookup"><span data-stu-id="32bd8-184">PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="32bd8-185">Чтобы изменить свойства, появившиеся в PowerShell 3,0, используйте диск WSMan: в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="32bd8-185">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="32bd8-186">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="32bd8-186">RELATED LINKS</span></span>

[<span data-ttu-id="32bd8-187">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-187">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-188">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-188">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-189">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-189">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-190">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="32bd8-190">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="32bd8-191">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="32bd8-191">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="32bd8-192">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-192">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-193">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-193">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-194">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="32bd8-194">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="32bd8-195">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="32bd8-195">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="32bd8-196">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="32bd8-196">WSMan Provider</span></span>](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[<span data-ttu-id="32bd8-197">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="32bd8-197">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="32bd8-198">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="32bd8-198">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
