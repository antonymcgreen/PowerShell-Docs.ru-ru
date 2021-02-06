---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Использование JEA
description: В этой статье описываются различные способы использования конечной точки JEA и подключения к ней.
ms.openlocfilehash: b3d81cc0aa76549c81136e5a1a5af28df9c6fa7a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501547"
---
# <a name="using-jea"></a><span data-ttu-id="67f7a-104">Использование JEA</span><span class="sxs-lookup"><span data-stu-id="67f7a-104">Using JEA</span></span>

<span data-ttu-id="67f7a-105">В этой статье описываются различные способы использования конечной точки JEA и подключения к ней.</span><span class="sxs-lookup"><span data-stu-id="67f7a-105">This article describes the various ways you can connect to and use a JEA endpoint.</span></span>

## <a name="using-jea-interactively"></a><span data-ttu-id="67f7a-106">Интерактивное использование JEA</span><span class="sxs-lookup"><span data-stu-id="67f7a-106">Using JEA interactively</span></span>

<span data-ttu-id="67f7a-107">Если вы тестируете конфигурацию JEA или предлагаете пользователям лишь простые задачи, JEA можно использовать аналогично обычному сеансу удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67f7a-107">If you're testing your JEA configuration or have simple tasks for users, you can use JEA the same way you would a regular PowerShell remoting session.</span></span> <span data-ttu-id="67f7a-108">Для сложных задач рекомендуется использовать метод [неявного удаленного взаимодействия](#using-jea-with-implicit-remoting).</span><span class="sxs-lookup"><span data-stu-id="67f7a-108">For complex remoting tasks, it's recommended to use [implicit remoting](#using-jea-with-implicit-remoting).</span></span> <span data-ttu-id="67f7a-109">Неявное удаленное взаимодействие позволяет пользователям работать с объектами данных локально.</span><span class="sxs-lookup"><span data-stu-id="67f7a-109">Implicit remoting allows users to operate with the data objects locally.</span></span>

<span data-ttu-id="67f7a-110">Для интерактивного использования JEA требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="67f7a-110">To use JEA interactively, you need:</span></span>

- <span data-ttu-id="67f7a-111">имя компьютера, к которому вы подключаетесь (это может быть локальный компьютер);</span><span class="sxs-lookup"><span data-stu-id="67f7a-111">The name of the computer you're connecting to (can be the local machine)</span></span>
- <span data-ttu-id="67f7a-112">имя конечной точки JEA, зарегистрированной на этом компьютере;</span><span class="sxs-lookup"><span data-stu-id="67f7a-112">The name of the JEA endpoint registered on that computer</span></span>
- <span data-ttu-id="67f7a-113">учетные данные для компьютера, предоставляющие доступ к конечной точке JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-113">Credentials that have access to the JEA endpoint on that computer</span></span>

<span data-ttu-id="67f7a-114">Располагая этой информацией, можно запустить сеанс JEA с помощью командлета [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) или [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="67f7a-114">Given that information, you can start a JEA session using the [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) or [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlets.</span></span>

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

<span data-ttu-id="67f7a-115">Если текущая учетная запись имеет доступ к конечной точке JEA, параметр **Credential** можно опустить.</span><span class="sxs-lookup"><span data-stu-id="67f7a-115">If the current user account has access to the JEA endpoint, you can omit the **Credential** parameter.</span></span>

<span data-ttu-id="67f7a-116">Когда командная строка PowerShell изменяется на `[localhost]: PS>`, это означает, что теперь вы взаимодействуете с удаленным сеансом JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-116">When the PowerShell prompt changes to `[localhost]: PS>` you know that you're now interacting with the remote JEA session.</span></span> <span data-ttu-id="67f7a-117">Чтобы ознакомиться со списком доступных команд, запустите `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="67f7a-117">You can run `Get-Command` to check which commands are available.</span></span> <span data-ttu-id="67f7a-118">Узнайте у администратора, налагаются ли какие-либо ограничения на доступные параметры и допустимые значения параметров.</span><span class="sxs-lookup"><span data-stu-id="67f7a-118">Consult with your administrator to learn if there are any restrictions on the available parameters or allowed parameter values.</span></span>

<span data-ttu-id="67f7a-119">Помните, что сеансы JEA работают в режиме NoLanguage.</span><span class="sxs-lookup"><span data-stu-id="67f7a-119">Remember, JEA sessions operate in NoLanguage mode.</span></span> <span data-ttu-id="67f7a-120">Некоторые из способов использования PowerShell могут быть доступны.</span><span class="sxs-lookup"><span data-stu-id="67f7a-120">Some of the ways you typically use PowerShell may not be available.</span></span> <span data-ttu-id="67f7a-121">Например, невозможно использовать переменные для хранения данных или проверки свойств для объектов, возвращаемых из командлетов.</span><span class="sxs-lookup"><span data-stu-id="67f7a-121">For instance, you can't use variables to store data or inspect the properties on objects returned from cmdlets.</span></span> <span data-ttu-id="67f7a-122">В следующем примере показано два подхода, позволяющих выполнить одни и те же команды в режиме NoLanguage.</span><span class="sxs-lookup"><span data-stu-id="67f7a-122">The following example shows two approaches to get the same commands to work in NoLanguage mode.</span></span>

```powershell
# Using variables is prohibited in NoLanguage mode. The following will not work:
# $vm = Get-VM -Name 'SQL01'
# Start-VM -VM $vm

# You can use pipes to pass data through to commands that accept input from the pipeline
Get-VM -Name 'SQL01' | Start-VM

# You can also wrap subcommands in parentheses and enter them inline as arguments
Start-VM -VM (Get-VM -Name 'SQL01')

# You can also use parameter sets that don't require extra data to be passed in
Start-VM -VMName 'SQL01'
```

<span data-ttu-id="67f7a-123">Для более сложных вызовов команд, которые затрудняют применение такой методики, рекомендуется использовать [неявное удаленное взаимодействие](#using-jea-with-implicit-remoting) или [создание пользовательских функций](role-capabilities.md#creating-custom-functions), включающих в себя нужную вам функциональность.</span><span class="sxs-lookup"><span data-stu-id="67f7a-123">For more complex command invocations that make this approach difficult, consider using [implicit remoting](#using-jea-with-implicit-remoting) or [creating custom functions](role-capabilities.md#creating-custom-functions) that wrap the functionality you require.</span></span>

## <a name="using-jea-with-implicit-remoting"></a><span data-ttu-id="67f7a-124">Использование JEA с помощью неявного удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="67f7a-124">Using JEA with implicit remoting</span></span>

<span data-ttu-id="67f7a-125">PowerShell поддерживает неявную модель удаленного взаимодействия, где можно импортировать командлеты прокси-сервера с удаленного компьютера и работать с ними, как если бы они были локальными командами.</span><span class="sxs-lookup"><span data-stu-id="67f7a-125">PowerShell has an implicit remoting model that lets you import proxy cmdlets from a remote machine and interact with them as if they were local commands.</span></span> <span data-ttu-id="67f7a-126">Неявное удаленное взаимодействие описано в этой записи блога **Hey, Scripting Guy!**</span><span class="sxs-lookup"><span data-stu-id="67f7a-126">Implicit remoting is explained in this **Hey, Scripting Guy!**</span></span> <span data-ttu-id="67f7a-127">[здесь](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/).</span><span class="sxs-lookup"><span data-stu-id="67f7a-127">[blog post](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/).</span></span>
<span data-ttu-id="67f7a-128">Неявное удаленное взаимодействие полезно при работе с JEA, так как оно позволяет работать с командлетами JEA в полноязыковом режиме.</span><span class="sxs-lookup"><span data-stu-id="67f7a-128">Implicit remoting is useful when working with JEA because it allows you to work with JEA cmdlets in a full language mode.</span></span> <span data-ttu-id="67f7a-129">Можно использовать заполнение нажатием клавиши TAB, переменные, работать с объектами и даже использовать локальные сценарии для автоматизации взаимодействия задач с конечной точкой JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-129">You can use tab completion, variables, manipulate objects, and even use local scripts to automate tasks against a JEA endpoint.</span></span> <span data-ttu-id="67f7a-130">При каждом выполнении команды прокси-сервера данные отправляются в конечную точку JEA на удаленном компьютере и выполняются там.</span><span class="sxs-lookup"><span data-stu-id="67f7a-130">Anytime you invoke a proxy command, the data is sent to the JEA endpoint on the remote machine and executed there.</span></span>

<span data-ttu-id="67f7a-131">Неявное удаленное взаимодействие работает путем импорта командлетов из существующего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67f7a-131">Implicit remoting works by importing cmdlets from an existing PowerShell session.</span></span> <span data-ttu-id="67f7a-132">При необходимости можно присваивать существительным каждого командлета прокси-сервера префикс в виде строки по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="67f7a-132">You can optionally choose to prefix the nouns of each proxy cmdlet with a string of your choosing.</span></span> <span data-ttu-id="67f7a-133">Префикс позволяет отличать команды, предназначенные для удаленной системы.</span><span class="sxs-lookup"><span data-stu-id="67f7a-133">The prefix allows you to distinguish the commands that are for the remote system.</span></span> <span data-ttu-id="67f7a-134">Создается временный модуль сценария, содержащий все команды прокси-сервера, который можно импортировать в течение локального сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67f7a-134">A temporary script module containing all the proxy commands is created and imported for the duration of your local PowerShell session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> <span data-ttu-id="67f7a-135">В некоторых системах импорт всего сеанса JEA может быть невозможен из-за ограничений в командлетах JEA по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67f7a-135">Some systems may not be able to import an entire JEA session due to constraints in the default JEA cmdlets.</span></span> <span data-ttu-id="67f7a-136">Чтобы обойти эту проблему, импортируйте из сеанса JEA только необходимые команды, явно указав их имена в параметре `-CommandName`.</span><span class="sxs-lookup"><span data-stu-id="67f7a-136">To get around this, only import the commands you need from the JEA session by explicitly providing their names to the `-CommandName` parameter.</span></span> <span data-ttu-id="67f7a-137">Данная проблема с импортом целых сеансов JEA на таких системах будет исправлена в будущем обновлении.</span><span class="sxs-lookup"><span data-stu-id="67f7a-137">A future update will address the issue with importing entire JEA sessions on affected systems.</span></span>

<span data-ttu-id="67f7a-138">Если вам не удается импортировать сеанс JEA из-за ограничений JEA для параметров по умолчанию, можно выполнить указанные ниже шаги, чтобы отфильтровать стандартные команды из импортированного набора.</span><span class="sxs-lookup"><span data-stu-id="67f7a-138">If you're unable to import a JEA session because of JEA constraints on the default parameters, follow the steps below to filter out the default commands from the imported set.</span></span> <span data-ttu-id="67f7a-139">Вы по-прежнему можете использовать такие команды, как `Select-Object`. Просто во время сеанса JEA вы будете использовать локальную версию, установленную на компьютере, вместо импортированной из удаленного сеанса JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-139">You can continue use commands like `Select-Object`, but you'll just use the local version installed on your computer instead of the one imported from the remote JEA session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Get a list of all the commands on the JEA endpoint
$commands = Invoke-Command -Session $jeasession -ScriptBlock { Get-Command }

# Filter out the default cmdlets
$jeaDefaultCmdlets = 'Clear-Host', 'Exit-PSSession', 'Get-Command', 'Get-FormatData', 'Get-Help', 'Measure-Object', 'Out-Default', 'Select-Object'
$filteredCommands = $commands.Name | Where-Object { $jeaDefaultCmdlets -notcontains $_ }

# Import only commands explicitly added in role capabilities and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA' -CommandName $filteredCommands
```

<span data-ttu-id="67f7a-140">Можно также сохранить командлеты, выполненные через прокси-сервер, из неявного удаленного взаимодействия с помощью [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).</span><span class="sxs-lookup"><span data-stu-id="67f7a-140">You can also persist the proxied cmdlets from implicit remoting using [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).</span></span>
<span data-ttu-id="67f7a-141">Дополнительные сведения о неявном удаленном взаимодействии см. в справочной документации по [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) и [Import-Module](/powershell/module/microsoft.powershell.core/import-module).</span><span class="sxs-lookup"><span data-stu-id="67f7a-141">For more information about implicit remoting, see the documentation for [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) and [Import-Module](/powershell/module/microsoft.powershell.core/import-module).</span></span>

## <a name="using-jea-programmatically"></a><span data-ttu-id="67f7a-142">Программное использование JEA</span><span class="sxs-lookup"><span data-stu-id="67f7a-142">Using JEA programmatically</span></span>

<span data-ttu-id="67f7a-143">JEA можно также использовать в системах автоматизации и приложениях пользователей, таких как приложения и веб-сайты собственной службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="67f7a-143">JEA can also be used in automation systems and in user applications, such as in-house helpdesk apps and websites.</span></span> <span data-ttu-id="67f7a-144">Подход при этом такой же, как и при создании приложений, которые обращаются к неограниченным конечным точкам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67f7a-144">The approach is the same as that for building apps that talk to unconstrained PowerShell endpoints.</span></span> <span data-ttu-id="67f7a-145">Убедитесь, что программа способна работать с ограничениями, накладываемыми JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-145">Ensure the program is designed to work with limitation imposed by JEA.</span></span>

<span data-ttu-id="67f7a-146">Для простых одноразовых задач можно использовать [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command), чтобы запускать команды с помощью JEA.</span><span class="sxs-lookup"><span data-stu-id="67f7a-146">For simple, one-off tasks, you can use [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) to run commands in a JEA session.</span></span>

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

<span data-ttu-id="67f7a-147">Чтобы узнать, какие команды доступны для использования при подключении к сеансу JEA, запустите `Get-Command` и просмотрите результаты для поиска допустимых параметров.</span><span class="sxs-lookup"><span data-stu-id="67f7a-147">To check which commands are available for use when you connect to a JEA session, run `Get-Command` and iterate through the results to check for the allowed parameters.</span></span>

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

<span data-ttu-id="67f7a-148">При разработке приложения на C# можно создать пространство выполнения PowerShell, которое подключается к сеансу JEA путем указания имени конфигурации в объекте [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo).</span><span class="sxs-lookup"><span data-stu-id="67f7a-148">If you're building a C# app, you can create a PowerShell runspace that connects to a JEA session by specifying the configuration name in a [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo) object.</span></span>

```csharp
// using System.Management.Automation;
var computerName = "SERVER01";
var configName   = "JEAMaintenance";
// See https://docs.microsoft.com/dotnet/api/system.management.automation.pscredential
var creds        = // create a PSCredential object here

WSManConnectionInfo connectionInfo = new WSManConnectionInfo(
    false,                 // Use SSL
    computerName,          // Computer name
    5985,                  // WSMan Port
    "/wsman",              // WSMan Path
                           // Connection URI with config name
    string.Format(CultureInfo.InvariantCulture, "http://schemas.microsoft.com/powershell/{0}", configName),
    creds);                // Credentials

// Now, use the connection info to create a runspace where you can run the commands
using (Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo))
{
    // Open the runspace
    runspace.Open();

    using (PowerShell ps = PowerShell.Create())
    {
        // Set the PowerShell object to use the JEA runspace
        ps.Runspace = runspace;

        // Now you can add and invoke commands
        ps.AddCommand("Get-Command");
        foreach (var result in ps.Invoke())
        {
            Console.WriteLine(result);
        }
    }

    // Close the runspace
    runspace.Close();
}
```

## <a name="using-jea-with-powershell-direct"></a><span data-ttu-id="67f7a-149">Использование JEA с помощью PowerShell Direct</span><span class="sxs-lookup"><span data-stu-id="67f7a-149">Using JEA with PowerShell Direct</span></span>

<span data-ttu-id="67f7a-150">Hyper-V в Windows 10 и Windows Server 2016 предоставляет функцию [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), позволяющую администраторам Hyper-V управлять виртуальными машинами с помощью PowerShell независимо от конфигурации сети и параметров удаленного управления на виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="67f7a-150">Hyper-V in Windows 10 and Windows Server 2016 offers [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), a feature that allows Hyper-V administrators to manage virtual machines with PowerShell regardless of the network configuration or remote management settings on the virtual machine.</span></span>

<span data-ttu-id="67f7a-151">PowerShell Direct с JEA можно использовать для предоставления администратору Hyper-V ограниченного доступа к виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="67f7a-151">You can use PowerShell Direct with JEA to give a Hyper-V administrator limited access to your VM.</span></span>
<span data-ttu-id="67f7a-152">Это может быть полезно, если потеряна связь с виртуальной машиной и администратору центра обработки данных необходимо исправить параметры сети.</span><span class="sxs-lookup"><span data-stu-id="67f7a-152">This can be useful if you lose network connectivity to your VM and need a datacenter admin to fix the network settings.</span></span>

<span data-ttu-id="67f7a-153">Дополнительная настройка для использования JEA с PowerShell Direct не требуется.</span><span class="sxs-lookup"><span data-stu-id="67f7a-153">No additional configuration is required to use JEA over PowerShell Direct.</span></span> <span data-ttu-id="67f7a-154">Однако на виртуальной машине должна использоваться ОС Windows 10, Windows Server 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="67f7a-154">However, the guest operating system running inside the virtual machine must be Windows 10, Windows Server 2016, or higher.</span></span> <span data-ttu-id="67f7a-155">Администратор Hyper-V может подключиться к конечной точке JEA с помощью параметров `-VMName` или `-VMId` в командлетах PSRemoting:</span><span class="sxs-lookup"><span data-stu-id="67f7a-155">The Hyper-V admin can connect to the JEA endpoint by using the `-VMName` or `-VMId` parameters on PSRemoting cmdlets:</span></span>

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

<span data-ttu-id="67f7a-156">Рекомендуется создать выделенную учетную запись с минимальными правами, необходимыми для управления системой, для использования администратором Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="67f7a-156">It's recommended you create a dedicated user account with the minimum rights needed to manage the system for use by a Hyper-V administrator.</span></span> <span data-ttu-id="67f7a-157">Помните, что по умолчанию даже непривилегированный пользователь может войти на компьютер с Windows, в том числе с использованием PowerShell без ограничений.</span><span class="sxs-lookup"><span data-stu-id="67f7a-157">Remember, even an unprivileged user can sign into a Windows machine by default, including using unconstrained PowerShell.</span></span> <span data-ttu-id="67f7a-158">Это позволит ему просмотреть содержимое файловой системы и подробнее узнать о среде операционной системы.</span><span class="sxs-lookup"><span data-stu-id="67f7a-158">That allows them to browse the file system and learn more about your OS environment.</span></span> <span data-ttu-id="67f7a-159">Чтобы дать администратору Hyper-V ограниченный доступ к виртуальной машине только с помощью PowerShell Direct с JEA, удалите права на локальный вход в систему из учетной записи JEA администратора Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="67f7a-159">To lock down a Hyper-V administrator and limit them to only access a VM using PowerShell Direct with JEA, you must deny local logon rights to the Hyper-V admin's JEA account.</span></span>
