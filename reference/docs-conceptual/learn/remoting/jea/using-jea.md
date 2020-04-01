---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Использование JEA
ms.openlocfilehash: 1c424eb4a476dd0db3cc69c0e6f14c89a3c523ba
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500516"
---
# <a name="using-jea"></a>Использование JEA

В этой статье описываются различные способы использования конечной точки JEA и подключения к ней.

## <a name="using-jea-interactively"></a>Интерактивное использование JEA

Если вы тестируете конфигурацию JEA или предлагаете пользователям лишь простые задачи, JEA можно использовать аналогично обычному сеансу удаленного взаимодействия PowerShell. Для сложных задач рекомендуется использовать метод [неявного удаленного взаимодействия](#using-jea-with-implicit-remoting). Неявное удаленное взаимодействие позволяет пользователям работать с объектами данных локально.

Для интерактивного использования JEA требуется следующее:

- имя компьютера, к которому вы подключаетесь (это может быть локальный компьютер);
- имя конечной точки JEA, зарегистрированной на этом компьютере;
- учетные данные для компьютера, предоставляющие доступ к конечной точке JEA.

Располагая этой информацией, можно запустить сеанс JEA с помощью командлета [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) или [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

Если текущая учетная запись имеет доступ к конечной точке JEA, параметр **Credential** можно опустить.

Когда командная строка PowerShell изменяется на `[localhost]: PS>`, это означает, что теперь вы взаимодействуете с удаленным сеансом JEA. Чтобы ознакомиться со списком доступных команд, запустите `Get-Command`. Узнайте у администратора, налагаются ли какие-либо ограничения на доступные параметры и допустимые значения параметров.

Помните, что сеансы JEA работают в режиме NoLanguage. Некоторые из способов использования PowerShell могут быть доступны. Например, невозможно использовать переменные для хранения данных или проверки свойств для объектов, возвращаемых из командлетов. В следующем примере показано два подхода, позволяющих выполнить одни и те же команды в режиме NoLanguage.

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

Для более сложных вызовов команд, которые затрудняют применение такой методики, рекомендуется использовать [неявное удаленное взаимодействие](#using-jea-with-implicit-remoting) или [создание пользовательских функций](role-capabilities.md#creating-custom-functions), включающих в себя нужную вам функциональность.

## <a name="using-jea-with-implicit-remoting"></a>Использование JEA с помощью неявного удаленного взаимодействия

PowerShell поддерживает неявную модель удаленного взаимодействия, где можно импортировать командлеты прокси-сервера с удаленного компьютера и работать с ними, как если бы они были локальными командами. Неявное удаленное взаимодействие описано в этой записи блога **Hey, Scripting Guy!** [здесь](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/).
Неявное удаленное взаимодействие полезно при работе с JEA, так как оно позволяет работать с командлетами JEA в полноязыковом режиме. Можно использовать заполнение нажатием клавиши TAB, переменные, работать с объектами и даже использовать локальные сценарии для автоматизации взаимодействия задач с конечной точкой JEA. При каждом выполнении команды прокси-сервера данные отправляются в конечную точку JEA на удаленном компьютере и выполняются там.

Неявное удаленное взаимодействие работает путем импорта командлетов из существующего сеанса PowerShell. При необходимости можно присваивать существительным каждого командлета прокси-сервера префикс в виде строки по своему выбору. Префикс позволяет отличать команды, предназначенные для удаленной системы. Создается временный модуль сценария, содержащий все команды прокси-сервера, который можно импортировать в течение локального сеанса PowerShell.

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> В некоторых системах импорт всего сеанса JEA может быть невозможен из-за ограничений в командлетах JEA по умолчанию. Чтобы обойти эту проблему, импортируйте из сеанса JEA только необходимые команды, явно указав их имена в параметре `-CommandName`. Данная проблема с импортом целых сеансов JEA на таких системах будет исправлена в будущем обновлении.

Если вам не удается импортировать сеанс JEA из-за ограничений JEA для параметров по умолчанию, можно выполнить указанные ниже шаги, чтобы отфильтровать стандартные команды из импортированного набора. Вы по-прежнему можете использовать такие команды, как `Select-Object`. Просто во время сеанса JEA вы будете использовать локальную версию, установленную на компьютере, вместо импортированной из удаленного сеанса JEA.

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

Можно также сохранить командлеты, выполненные через прокси-сервер, из неявного удаленного взаимодействия с помощью [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).
Дополнительные сведения о неявном удаленном взаимодействии см. в справочной документации по [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) и [Import-Module](/powershell/module/microsoft.powershell.core/import-module).

## <a name="using-jea-programmatically"></a>Программное использование JEA

JEA можно также использовать в системах автоматизации и приложениях пользователей, таких как приложения и веб-сайты собственной службы поддержки. Подход при этом такой же, как и при создании приложений, которые обращаются к неограниченным конечным точкам PowerShell. Убедитесь, что программа способна работать с ограничениями, накладываемыми JEA.

Для простых одноразовых задач можно использовать [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command), чтобы запускать команды с помощью JEA.

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

Чтобы узнать, какие команды доступны для использования при подключении к сеансу JEA, запустите `Get-Command` и просмотрите результаты для поиска допустимых параметров.

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

При разработке приложения на C# можно создать пространство выполнения PowerShell, которое подключается к сеансу JEA путем указания имени конфигурации в объекте [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo).

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
    string.Format(CultureInfo.InvariantCulture, "https://schemas.microsoft.com/powershell/{0}", configName),
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

## <a name="using-jea-with-powershell-direct"></a>Использование JEA с помощью PowerShell Direct

Hyper-V в Windows 10 и Windows Server 2016 предоставляет функцию [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), позволяющую администраторам Hyper-V управлять виртуальными машинами с помощью PowerShell независимо от конфигурации сети и параметров удаленного управления на виртуальной машине.

PowerShell Direct с JEA можно использовать для предоставления администратору Hyper-V ограниченного доступа к виртуальной машине.
Это может быть полезно, если потеряна связь с виртуальной машиной и администратору центра обработки данных необходимо исправить параметры сети.

Дополнительная настройка для использования JEA с PowerShell Direct не требуется. Однако на виртуальной машине должна использоваться ОС Windows 10, Windows Server 2016 или более поздней версии. Администратор Hyper-V может подключиться к конечной точке JEA с помощью параметров `-VMName` или `-VMId` в командлетах PSRemoting:

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

Рекомендуется создать выделенную учетную запись с минимальными правами, необходимыми для управления системой, для использования администратором Hyper-V. Помните, что по умолчанию даже непривилегированный пользователь может войти на компьютер с Windows, в том числе с использованием PowerShell без ограничений. Это позволит ему просмотреть содержимое файловой системы и подробнее узнать о среде операционной системы. Чтобы дать администратору Hyper-V ограниченный доступ к виртуальной машине только с помощью PowerShell Direct с JEA, удалите права на локальный вход в систему из учетной записи JEA администратора Hyper-V.
