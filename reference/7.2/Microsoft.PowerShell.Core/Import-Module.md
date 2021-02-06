---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 1b8164be05f011e13945323a6288426bd2d41183
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "99602706"
---
# Import-Module

## Краткий обзор
Добавляет модули в текущий сеанс.

## SYNTAX

### Имя (по умолчанию)

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### PSSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### CimSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### усевиндовсповершелл

```
Import-Module [-Name] <string[]> -UseWindowsPowerShell [-Global] [-Prefix <string>]
 [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>] [-Alias <string[]>]
 [-Force] [-PassThru] [-AsCustomObject] [-MinimumVersion <version>] [-MaximumVersion <string>]
 [-RequiredVersion <version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <string>] [<CommonParameters>]
```

### FullyQualifiedName

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

### фулликуалифиеднамеандпссессион

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### фулликуалифиеднамеандусевиндовсповершелл

```
Import-Module [-FullyQualifiedName] <ModuleSpecification[]> -UseWindowsPowerShell [-Global]
 [-Prefix <string>] [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>]
 [-Alias <string[]>] [-Force] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>]
 [-DisableNameChecking] [-NoClobber] [-Scope <string>] [<CommonParameters>]
```

### Сборка

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### ModuleInfo

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck] [-PassThru]
 [-AsCustomObject] [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

## DESCRIPTION

`Import-Module`Командлет добавляет один или несколько модулей в текущий сеанс. Начиная с PowerShell 3,0, установленные модули автоматически импортируются в сеанс при использовании каких либо команд или поставщиков в модуле. Однако вы по-прежнему можете использовать `Import-Module` команду для импорта модуля.
Вы можете отключить автоматическое импортирование модулей с помощью `$PSModuleAutoloadingPreference` переменной предпочтений. Дополнительные сведения о `$PSModuleAutoloadingPreference` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

Модуль — это пакет, содержащий элементы, которые можно использовать в PowerShell. Члены включают командлеты, поставщики, скрипты, функции, переменные и другие средства и файлы. После импорта модуля вы можете использовать его элементы в текущем сеансе. Дополнительные сведения о модулях см. в разделе [about_Modules](About/about_Modules.md).

По умолчанию `Import-Module` импортирует все элементы, экспортируемые модулем, но можно использовать параметры **псевдонима**, **функции**, **командлета** и **переменной** , чтобы ограничить импортируемые элементы. Параметр **NoClobber** предотвращает `Import-Module` Импорт элементов, имеющих те же имена, что и члены в текущем сеансе.

`Import-Module` импортирует модуль только в текущий сеанс. Чтобы импортировать модуль в каждый новый сеанс, добавьте `Import-Module` команду в профиль PowerShell. Дополнительные сведения о профилях см. в разделе [about_Profiles](About/about_Profiles.md).

Вы можете управлять удаленными компьютерами Windows, на которых удаленное взаимодействие PowerShell включено, создав **сеанс PSSession** на удаленном компьютере. Затем используйте параметр **PSSession** параметра, `Import-Module` чтобы импортировать модули, установленные на удаленном компьютере. При использовании импортированных команд в текущем сеансе команды выполняются неявным образом на удаленном компьютере.

Начиная с Windows PowerShell 3,0, можно использовать `Import-Module` для импорта модулей модель CIM (CIM). Модули CIM определяют командлеты в файлах XML определения командлетов (CDXML). Эта функция позволяет использовать командлеты, реализованные в неуправляемых сборках кода, таких как написанные на C++.

Для удаленных компьютеров, на которых не включено удаленное взаимодействие PowerShell, включая компьютеры, на которых не установлена операционная система Windows, можно  использовать параметр CIMSession `Import-Module` в для импорта модулей CIM с удаленного компьютера. Импортированные команды выполняются неявно на удаленном компьютере. **CIMSession** — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере.

## Примеры

### Пример 1. Импорт членов модуля в текущий сеанс

В этом примере выполняется импорт элементов модуля **PSDiagnostics** в текущий сеанс.

```powershell
Import-Module -Name PSDiagnostics
```

### Пример 2. импорт всех модулей, указанных в пути к модулю

В этом примере выполняется импорт всех доступных модулей по пути, указанному в `$env:PSModulePath` переменной среды, в текущий сеанс.

```powershell
Get-Module -ListAvailable | Import-Module
```

### Пример 3. Импорт элементов нескольких модулей в текущий сеанс

В этом примере выполняется импорт элементов модулей **PSDiagnostics** и **DISM** в текущий сеанс.

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

`Get-Module`Командлет получает модули **PSDiagnostics** и **DISM** и сохраняет объекты в `$m` переменной. Параметр **ListAvailable** является обязательным при получении модулей, которые еще не импортированы в сеанс.

Параметр **ModuleInfo** класса `Import-Module` используется для импорта модулей в текущий сеанс.

### Пример 4. импорт всех модулей, указанных путем

В этом примере используется явный путь для указания импортируемого модуля.

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

Использование параметра **verbose** приводит `Import-Module` к отчету о ходе выполнения при загрузке модуля.
Без параметра **verbose**, **PassThru** или **AsCustomObject** не `Import-Module` создает никаких выходных данных при импорте модуля.

### Пример 5. Ограничение элементов модуля, импортированных в сеанс

В этом примере показано, как ограничить список членов модуля, импортируемых в сеанс, и результат выполнения этой команды в сеансе. Параметр **функции** ограничивает элементы, импортируемые из модуля. Можно также использовать параметры **псевдонима**, **переменной** и **командлета** для ограничения других членов, импортируемых модулем.

`Get-Module`Командлет возвращает объект, представляющий модуль **PSDiagnostics** . Свойство **експортедкмдлетс** перечисляет все командлеты, экспортируемые модулем, даже если они не были импортированы.

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

С помощью параметра **module** `Get-Command` командлета отображаются команды, импортированные из модуля **PSDiagnostics** . Результаты подтверждают, что `Disable-PSTrace` `Enable-PSTrace` импортированы только командлеты и.

### Пример 6. Импорт элементов модуля и Добавление префикса

Этот пример импортирует модуль **PSDiagnostics** в текущий сеанс, добавляет префикс к именам членов, а затем отображает имена элементов с префиксом. Параметр **prefix** параметра `Import-Module` добавляет префикс **x** ко всем элементам, импортированным из модуля. Префикс применяется только к элементам в текущем сеансе. Он не изменяет сам модуль. Параметр **PassThru** возвращает объект Module, представляющий импортированный модуль.

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

`Get-Command` Возвращает элементы, которые были импортированы из модуля. Выходные данные показывают, что к элементам модуля был правильно добавлен префикс.

### Пример 7. получение и использование пользовательского объекта

В этом примере показано, как получить и использовать пользовательский объект, возвращаемый методом `Import-Module` .

Настраиваемые объекты содержат синтетические элементы, представляющие каждый из элементов импортированного модуля. Например, командлеты и функции в модуле преобразуются в методы скрипта пользовательского объекта.

Пользовательские объекты полезны в сценариях. Они также полезны, если имена нескольких импортированных объектов совпадают. Использование метода скрипта объекта равнозначно указанию полного имени импортированного элемента, включая имя модуля.

Параметр **AsCustomObject** можно использовать только при импорте модуля скрипта. Используйте `Get-Module` , чтобы определить, какой из доступных модулей является модулем скрипта.

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

`Show-Calendar`Модуль скрипта импортируется с помощью параметра **AsCustomObject** для запроса пользовательского объекта, а параметр **PassThru** — для возврата объекта. Полученный пользовательский объект сохраняется в `$a` переменной.

`$a`Переменная передается в `Get-Member` командлет для отображения свойств и методов сохраненного объекта. В выходных данных показан `Show-Calendar` метод скрипта.

Чтобы вызвать `Show-Calendar` метод скрипта, имя метода должно быть заключено в кавычки, так как имя включает дефис.

### Пример 8. повторное импорт модуля в тот же сеанс

В этом примере показано, как использовать параметр **Force** при повторном `Import-Module` импорте модуля в тот же сеанс. Параметр **Force** удаляет загруженный модуль и затем импортирует его снова.

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

Первая команда импортирует модуль **PSDiagnostics** . Вторая команда импортирует модуль, на этот раз с помощью параметра **Prefix**.

Без параметра **Force** сеанс будет содержать две копии каждого командлета **PSDiagnostics** , один из которых имеет стандартное имя и имя с префиксом.

### Пример 9. выполнение команд, скрытых с помощью импортированных команд

В этом примере показано, как выполнить команды, которые были скрыты импортированными командами. Модуль **тестмодуле** включает функцию с именем `Get-Date` , которая возвращает год и день года.

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

Первый `Get-Date` командлет возвращает объект **DateTime** с текущей датой. После импорта модуля **тестмодуле** `Get-Date` возвращает год и день года.

Используя параметр **ALL** параметра, вы `Get-Command` увидите все `Get-Date` команды в сеансе. Результаты показывают, что `Get-Date` в сеансе есть две команды: функция из модуля **тестмодуле** и командлет из модуля **Microsoft. PowerShell. Utility** .

Поскольку функции имеют приоритет над командлетами, `Get-Date` вместо командлета выполняется функция из модуля **тестмодуле** `Get-Date` . Чтобы запустить исходную версию `Get-Date` , необходимо уточнить имя команды с помощью имени модуля.

Дополнительные сведения о приоритетах команд в PowerShell см. в разделе [about_Command_Precedence](about/about_Command_Precedence.md).

### Пример 10. Импорт минимальной версии модуля

В этом примере импортируется модуль **PowerShellGet** . Параметр **MinimumVersion** `Import-Module` в используется для импорта только 2.0.0 версии или выше модуля.

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

Можно также использовать параметр **RequiredVersion** для импорта определенной версии модуля или использовать параметры **модуля** и **версии** `#Requires` ключевого слова, чтобы требовать определенную версию модуля в скрипте.

### Пример 11. Импорт с использованием полного имени

В этом примере выполняется импорт определенной версии модуля с помощью FullyQualifiedName.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### Пример 12. Импорт с использованием полного пути

В этом примере выполняется импорт определенной версии модуля с использованием полного пути.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### Пример 13. импорт модуля с удаленного компьютера

В этом примере показано, как использовать `Import-Module` командлет для импорта модуля с удаленного компьютера.
Эта команда использует функцию неявного удаленного взаимодействия PowerShell.

При импорте модулей из другого сеанса можно применять командлеты в текущем сеансе.
Однако команды, использующие командлеты, выполняются в удаленном сеансе.

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

`New-PSSession` создает удаленный сеанс (**PSSession**) на компьютере Server01. **Сеанс PSSession** сохраняется в `$s` переменной.

Запуск `Get-Module` с параметром **PSSession** показывает, что модуль **NetSecurity** установлен и доступен на удаленном компьютере. Эта команда эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module` команды в удаленном сеансе. Например: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`

`Import-Module`При выполнении с параметром **PSSession** импортирует модуль **NetSecurity** с удаленного компьютера в текущий сеанс. `Get-Command`Командлет используется для получения команд, начинающихся с **Get** и включая **брандмауэр** из модуля **NetSecurity** . Выходные данные подтверждают, что модуль и его командлеты были импортированы в текущий сеанс.

Затем `Get-NetFirewallRule` командлет получает служба удаленного управления Windows правила брандмауэра на компьютере Server01. Это эквивалентно использованию `Invoke-Command` командлета для запуска `Get-NetFirewallRule` в удаленном сеансе.

### Пример 14. Управление хранилищем на удаленном компьютере без операционной системы Windows

В этом примере администратор компьютера установил поставщик WMI для обнаружения модуля, который позволяет использовать команды CIM, предназначенные для поставщика.

`New-CimSession`Командлет создает сеанс на удаленном компьютере с именем RSDGF03. Сеанс подключается к службе WMI на удаленном компьютере. Сеанс CIM сохраняется в `$cs` переменной.
`Import-Module` использует **CimSession** в `$cs` для импорта модуля CIM **хранилища** с компьютера RSDGF03.

`Get-Command`Командлет отображает `Get-Disk` команду в модуле **Storage** . При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML для каждой команды в скрипты PowerShell, которые отображаются как функции в локальном сеансе.

Хотя он `Get-Disk` вводится в локальный сеанс, командлет выполняется неявно на удаленном компьютере, с которого он был импортирован. Команда возвращает объекты с удаленного компьютера в локальный сеанс.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## PARAMETERS

### -Alias

Задает псевдонимы, которые этот командлет импортирует из модуля в текущий сеанс. Введите разделенный запятыми список псевдонимов. Можно использовать подстановочные знаки.

Некоторые модули автоматически экспортируют выбранные псевдонимы в сеанс при импорте модуля.
Этот параметр позволяет выбрать один из экспортированных псевдонимов.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ArgumentList

Указывает массив аргументов или значений параметров, которые передаются в модуль скрипта во время выполнения `Import-Module` команды. Этот параметр допустим только при импорте модуля скрипта.

Можно также ссылаться на параметр **ArgumentList** по его псевдониму **args**. Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsCustomObject

Указывает, что этот командлет возвращает пользовательский объект с элементами, представляющими импортированные элементы модуля. Этот параметр допустим только для модулей скриптов.

При использовании параметра **AsCustomObject** `Import-Module` импортирует элементы модуля в сеанс, а затем возвращает объект **PSCustomObject** вместо объекта **PSModuleInfo** . Пользовательский объект можно сохранить в переменную и использовать точку для вызова элементов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assembly

Задает массив объектов Assembly. Этот командлет импортирует командлеты и поставщики, реализованные в указанных объектах сборки. Введите переменную, которая содержит объекты сборки, или команду, которая создает объекты сборки. Также можно передать объект сборки в `Import-Module` .

При использовании этого параметра импортируются только командлеты и поставщики, реализованные в указанных сборках. Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля. Этот параметр используется для отладки и тестирования модуля, а также при указании его использования автором модуля.

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Цимнамеспаце

Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM. Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.

Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Цимресаурцеури

Задает альтернативное расположение для модулей CIM. Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.

Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Указывает сеанс CIM на удаленном компьютере. Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](../CimCmdlets/Get-CimSession.md) .

`Import-Module` использует соединение с сеансом CIM для импорта модулей с удаленного компьютера в текущий сеанс. При использовании команд из импортированного модуля в текущем сеансе команды выполняются на удаленном компьютере.

Этот параметр можно использовать для импорта модулей с компьютеров и устройств, которые не работают под управлением операционной системы Windows, и компьютеров Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Командлет

Указывает массив командлетов, которые этот командлет импортирует из модуля в текущий сеанс.
Можно использовать подстановочные знаки.

Некоторые модули автоматически экспортируют выбранные командлеты в сеанс при импорте модуля.
Этот параметр позволяет выбрать один из экспортированных командлетов.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -DisableNameChecking

Указывает, что этот командлет подавляет сообщение, выдающее предупреждение при импорте командлета или функции, имя которой включает неутвержденную команду или запрещенный символ.

По умолчанию, когда импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, PowerShell выводит следующее предупреждающее сообщение:

> ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми. Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.

Это сообщение является всего лишь предупреждением. Импорт осуществляется для всего модуля, включая недопустимые команды. Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Этот параметр приводит к тому, что модуль загружается или перегружается поверх текущего.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Указывает полное имя модуля в виде хэш-таблицы. Значение может быть сочетанием строк и хэш-таблиц. Хэш-таблица содержит следующие ключи.

- `ModuleName` - **Обязательное требование** Указывает имя модуля.
- `GUID` - **Необязательно** Указывает идентификатор GUID модуля.
- **Также необходимо** указать один из трех указанных ниже ключей. Эти ключи нельзя использовать совместно.
  - `ModuleVersion` — Указывает минимальную допустимую версию модуля.
  - `RequiredVersion` — Указывает точную, требуемую версию модуля.
  - `MaximumVersion` — Указывает максимально допустимую версию модуля.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession, FullyQualifiedNameAndWinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Function

Указывает массив функций, которые этот командлет импортирует из модуля в текущий сеанс.
Можно использовать подстановочные знаки. Некоторые модули автоматически экспортируют выбранные функции в сеанс при импорте модуля. Этот параметр позволяет выбрать один из экспортированных функций.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Global

Указывает, что этот командлет импортирует модули в глобальное состояние сеанса, чтобы они были доступны для всех команд в сеансе.

По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса.

При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего модуля.

> [!TIP]
> Следует избегать вызова `Import-Module` из модуля. Вместо этого следует объявить целевой модуль как вложенный модуль в манифесте родительского модуля. Объявление вложенных модулей повышает возможность обнаружения зависимостей.

Параметр **Global** аналогичен параметру **Scope** со значением **Global**.

Чтобы ограничить команды, экспортируемые модулем, используйте `Export-ModuleMember` команду в модуле script.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Указывает максимальную версию. Этот командлет импортирует только версию модуля, которая меньше или равна указанному значению. Если версия не соответствует требованиям, функция `Import-Module` возвращает ошибку.

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Указывает минимальную версию. Этот командлет импортирует только версию модуля, которая больше или равна указанному значению. Используйте имя параметра **MinimumVersion** или его псевдоним, **Version**. Если версия не соответствует требованиям, `Import-Module` выдает ошибку.

Чтобы указать точную версию, используйте параметр **RequiredVersion**. Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleInfo

Указывает массив объектов модуля для импорта. Введите переменную, содержащую объекты модуля, или команду, которая получает объекты модуля, например следующую команду: `Get-Module -ListAvailable` . Также можно передать объекты модуля в `Import-Module` .

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Задает имена модулей для импорта. Введите имя модуля или имя файла в модуле, например `.psd1` файл,, `.psm1` `.dll` или `.ps1` . Пути к файлам являются необязательными. Подстановочные знаки не допускаются. Можно также передать имена модулей и имен файлов в `Import-Module` .

Если опустить путь, `Import-Module` ищет модуль в путях, сохраненных в `$env:PSModulePath` переменной среды.

По возможности указывайте только имя модуля. Если указать имя файла, импортируются только элементы, реализованные в этом файле. Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля.

> [!NOTE]
> Хотя файл скрипта () можно импортировать `.ps1` как модуль, файлы скриптов обычно не структурированы как файл модулей скрипта ( `.psm1` ). Импорт файла скрипта не гарантирует, что он будет использоваться в качестве модуля. Дополнительные сведения см. в разделе [about_Modules](about/about_Modules.md).

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -NoClobber

Предотвращает импорт команд, имеющих те же имена, что и существующие команды в текущем сеансе. По умолчанию `Import-Module` импортирует все команды экспортированного модуля.

Команды с одинаковыми именами могут скрывать или заменять команды в сеансе. Чтобы избежать конфликта имен команд в сеансе, используйте параметр **Prefix** или **NoClobber**. Дополнительные сведения о конфликтах имен и приоритете команд см. в разделе "Конфликты модулей и имен" в статьях [about_Modules](about/about_Modules.md) и [about_Command_Precedence](about/about_Command_Precedence.md).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым выполняется работа. По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### — Префикс

Задает префикс, который добавляется этим командлетом к существительным в именах импортированных элементов модуля.

Используйте этот параметр, чтобы избежать конфликтов имен, которые могут возникать, когда имена элементов совпадают с именами элементов в сеансе. Этот параметр не изменяет модуль и не влияет на файлы, импортируемые модулем для его собственного использования. Они называются вложенными модулями. Этот командлет влияет только на имена элементов в текущем сеансе.

Например, если указать префикс UTC, а затем импортировать `Get-Date` командлет, то этот командлет будет известен в сеансе как `Get-UTCDate` , и он не будет путать с исходным `Get-Date` командлетом.

Значение этого параметра имеет приоритет над свойством **DefaultCommandPrefix** модуля, который определяет префикс по умолчанию.

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

### -PSSession

Указывает управляемый пользователем сеанс PowerShell (**PSSession**), из которого этот командлет импортирует модули в текущий сеанс. Введите переменную, содержащую **сеанс PSSession** или команду, которая получает **PSSession**, например `Get-PSSession` команду.

При импорте модуля из другого сеанса в текущий сеанс командлеты из модуля в текущем сеансе можно использовать, как и командлеты из локального модуля. Команды, использующие удаленные командлеты, выполняются в удаленном сеансе, но сведения об удаленном взаимодействии управляются в фоновом режиме с помощью PowerShell.

Этот параметр использует функцию неявного удаленного взаимодействия PowerShell. Он эквивалентен использованию `Import-PSSession` командлета для импорта определенных модулей из сеанса.

`Import-Module` невозможно импортировать модули PowerShell Core из другого сеанса. Имена модулей PowerShell Core начинаются с Microsoft. PowerShell.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Указывает версию модуля, который импортирует этот командлет. Если версия не установлена, `Import-Module` создает ошибку.

По умолчанию `Import-Module` импортирует модуль без проверки номера версии.

Чтобы указать минимальную версию, используйте параметр **MinimumVersion**. Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.

Этот параметр впервые появился в Windows PowerShell 3.0.

Сценарии, использующие **RequiredVersion** для импорта модулей, входящих в состав существующих выпусков операционной системы Windows, не выполняются автоматически в будущих выпусках операционной системы Windows. Это обусловлено тем, что номера версий модулей PowerShell в будущих выпусках операционной системы Windows выше, чем номера версий модулей в существующих выпусках операционной системы Windows.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope

Указывает область, в которой этот командлет импортирует модуль.

Допустимые значения для этого параметра:

- **Глобальный**. доступно для всех команд в сеансе. Эквивалентно параметру **Global**.
- **Локальный**. доступно только в текущей области.

По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса. С помощью параметра можно `-Scope Local` импортировать содержимое модуля в область скрипта или ScriptBlock.

При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего. Указание `-Scope Global` или `-Global` указывает, что этот командлет импортирует модули в глобальное состояние сеанса, поэтому они доступны для всех команд в сеансе.

Параметр **Global** аналогичен параметру **Scope** со значением **Global**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Указывает массив переменных, которые этот командлет импортирует из модуля в текущий сеанс.
Введите список переменных. Можно использовать подстановочные знаки.

Некоторые модули автоматически экспортируют выбранные переменные в сеанс при импорте модуля.
Этот параметр позволяет выбрать один из экспортированных переменных.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Скипедитиончекк

Пропускает проверку на `CompatiblePSEditions` поле.

Позволяет загрузить модуль из `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` каталога модуля в PowerShell Core, если этот модуль не указан `Core` в `CompatiblePSEditions` поле манифеста.

При импорте модуля из другого пути этот параметр не выполняет никаких действий, так как проверка не выполняется. В Linux и macOS этот параметр не выполняет никаких действий.

Дополнительные сведения см. в разделе [about_PowerShell_Editions](About/about_PowerShell_Editions.md).

> [!WARNING]
> `Import-Module -SkipEditionCheck` по-прежнему может не импортировать модуль. Даже если он завершится успешно, при попытке использовать несовместимый API вызов команды из модуля может завершиться ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, PSSession, CimSession, FullyQualifiedName, FullyQualifiedNameAndPSSession, Assembly, ModuleInfo
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Усевиндовсповершелл

Загружает модуль с помощью функции совместимости Windows PowerShell. Дополнительные сведения см. в разделе [about_Windows_PowerShell_Compatibility](About/about_Windows_PowerShell_Compatibility.md) .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WinCompat, FullyQualifiedNameAndWinCompat
Aliases: UseWinPS

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, System. Management. Automation. PSModuleInfo, System. Reflection. Assembly

В этот командлет можно передать имя модуля, объект модуля или объект сборки.

## Выходные данные

### None, System. Management. Automation. PSModuleInfo или System. Management. Automation. PSCustomObject

По умолчанию не `Import-Module` создает никаких выходных данных. Если указан параметр **PassThru** , командлет создает объект **System. Management. Automation. PSModuleInfo** , представляющий модуль. При указании параметра **AsCustomObject** создается объект **PSCustomObject** .

## ПРИМЕЧАНИЯ

- Перед импортом модуля необходимо установить модуль на локальном компьютере. То есть каталог модуля должен быть скопирован в каталог, доступный локальному компьютеру. Дополнительные сведения см. в разделе [about_Modules](About/about_Modules.md).

  Для импорта модулей, установленных на удаленных компьютерах, можно также использовать параметры **PSSession** и **CIMSession**. Однако команды, использующие командлеты в этих модулях, выполняются в удаленном сеансе на удаленном компьютере.

- Если в сеансе импортируются элементы с одинаковым именем и типом, то в PowerShell по умолчанию используется элемент, импортированный последним. Переменные и псевдонимы заменяются, и исходные значения недоступны. Функции, командлеты и поставщики просто затенены новыми элементами. Доступ к ним можно получить, добавив в имя команды имя своей оснастки, модуля или пути к функции.

- Чтобы обновить данные форматирования для команд, импортированных из модуля, используйте `Update-FormatData` командлет. `Update-FormatData` также обновляет данные форматирования для команд в сеансе, импортированных из модулей. При изменении файла форматирования для модуля можно выполнить `Update-FormatData` команду, чтобы обновить данные форматирования для импортированных команд. Импортировать модуль повторно не требуется.

- Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые с помощью PowerShell, упаковываются в модули. В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки (**PSSnapin**). Исключением является **Microsoft. PowerShell. Core**, который всегда является оснасткой. Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.

  Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в описании [метода CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- В Windows PowerShell 2,0 некоторые значения свойств объекта Module, такие как значения свойств **експортедкмдлетс** и **NestedModules** , не были заполнены до импорта модуля.

- При попытке импортировать модуль, содержащий сборки в смешанном режиме, несовместимые с Windows PowerShell 3.0 +, `Import-Module` возвращает сообщение об ошибке следующего вида.

  > Import-Module: сборка смешанного режима построена на базе версии "v 2.0.50727" среды выполнения и не может быть загружена в среду выполнения 4,0 без дополнительных сведений о конфигурации.

  Эта ошибка возникает, когда модуль, разработанный для Windows PowerShell 2,0, содержит по крайней мере одну сборку смешанного модуля. Сборка смешанного модуля, включающая как управляемый, так и неуправляемый код, например C++ и C#.

  Чтобы импортировать модуль, содержащий сборки в смешанном режиме, запустите Windows PowerShell 2,0 с помощью следующей команды и повторите `Import-Module` команду.

  `PowerShell.exe -Version 2.0`

- Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт. На компьютере также должен быть поставщик WMI модуля обнаружения или альтернативный поставщик CIM с теми же основными функциями.

  Можно использовать сеанс CIM на компьютерах, которые не работают под управлением операционной системы Windows и на компьютерах Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.

  Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell, включая локальный компьютер. При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.

- По умолчанию `Import-Module` импортирует модули в глобальной области, даже если они вызываются из области видимости потомков. Область верхнего уровня и все области видимости потомков имеют доступ к экспортированным элементам модуля.

  В области видимости потомков `-Scope Local` ограничивает импорт в эту область и все ее дочерние области. В родительских областях не отображаются импортированные элементы.

  > [!NOTE]
  > `Get-Module` показывает все модули, загруженные в текущем сеансе. Сюда входят модули, загруженные локально в области видимости потомков. Используйте `Get-Command -Module modulename` , чтобы узнать, какие элементы загружаются в текущей области.

  `Import-Module` не загружает определения классов и перечислений в модуле. Используйте `using module` оператор в начале скрипта. Это позволит импортировать модуль, включая определения класса и перечисления. Дополнительные сведения см. в разделе [about_Using](About/about_Using.md).

## Связанные ссылки

[about_Modules](about/about_Modules.md)

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[New-Module](New-Module.md)

[Remove-Module](Remove-Module.md)

[about_PowerShell_Editions](About/about_PowerShell_Editions.md)
