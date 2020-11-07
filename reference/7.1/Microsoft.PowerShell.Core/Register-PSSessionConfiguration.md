---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 028e28e071bf6e19f2d0aef72b4eec45da6c45b7
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345890"
---
# Register-PSSessionConfiguration

## Краткий обзор
Создает и регистрирует новую конфигурацию сеанса.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AssemblyNameParameterSet

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

### SessionConfigurationFile

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Register-PSSessionConfiguration`Командлет создает и регистрирует новую конфигурацию сеанса на локальном компьютере. Это расширенный командлет, с помощью которого можно создавать пользовательские сеансы для удаленных пользователей.

Каждый сеанс PowerShell ( **PSSession** ) использует конфигурацию сеанса, также известную как конечная точка.
Когда пользователи создают сеанс, который подключается к компьютеру, он может выбрать конфигурацию сеанса или использовать конфигурацию сеанса по умолчанию, зарегистрированную при включении удаленного взаимодействия PowerShell.
Кроме того, пользователи могут задавать привилегированную переменную $PSSessionConfigurationName, которая определяет конфигурацию по умолчанию для удаленных сеансов, создаваемых в текущем сеансе.

Конфигурация сеанса определяет среду для удаленного сеанса. Она определяет, какие команды и элементы языка будут доступны в сеансе, и может включать параметры для защиты компьютера, например ограничения на объем данных, принимаемых сеансом в удаленном режиме в одном объекте или команде. Дескриптор безопасности конфигурации сеанса определяет, какие пользователи имеют разрешение на использование конфигурации сеанса.

Элементы конфигурации определяются с помощью сборки, реализующей новый класс конфигурации, или скрипта, выполняемого в сеансе. Начиная с PowerShell 3,0, можно также использовать файл конфигурации сеанса для определения конфигурации сеанса.

Сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).
Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

## Примеры

### Пример 1. Регистрация конфигурации сеанса NewShell

В этом примере мы регистрируем конфигурацию сеанса **NewShell** . Параметры **AssemblyName** и **ApplicationBase** указывают расположение файла **MyShell.dll** , который указывает командлеты и поставщики в конфигурации сеанса. Параметр **ConfigurationTypeName** указывает класс конфигурации, используемый из сборки.

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

Чтобы использовать эту конфигурацию, введите `New-PSSession -ConfigurationName newshell` .

### Пример 2. Регистрация конфигурации сеанса MaintenanceShell

В этом примере регистрируется конфигурация сеанса **MaintenanceShell** на локальном компьютере. Параметр **StartupScript** указывает `Maintenance.ps1` скрипт.

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

Когда пользователь использует `New-PSSession` команду и выбирает конфигурацию **MaintenanceShell** , `Maintenance.ps1` сценарий выполняется в новом сеансе. Скрипт может настроить сеанс. Сюда входят импорт модулей и Настройка политики выполнения для сеанса. Если скрипт создает ошибки, включая устранимые ошибки, `New-PSSession` команда завершается ошибкой.

### Пример 3. Регистрация конфигурации сеанса

В этом примере регистрируется конфигурация сеанса **AdminShell** .

`$sessionParams`Переменная является хэш-таблицей, содержащей все значения параметров. Эта хэш-таблица передается командлету с помощью PowerShell Сплаттинг. `Register-PSSessionConfiguration`Команда использует параметр **секуритидескриторсддл** для указания SDDL в значении `$sddl` переменной, а параметр **максимумрецеиведобжектсиземб** — для увеличения предельного размера объекта. Параметр **StartupScript** определяет скрипт, который будет использоваться для настройки сеанса.

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

### Пример 4. возврат элемента контейнера конфигурации

В этом примере показано, как зарегистрировать конфигурацию **MaintenanceShell** .
`Register-PSSessionConfiguration` Возвращает объект **всманконфигконтаинерелемент** , хранящийся в `$s` переменной. `Format-List` Отображает все свойства возвращенного объекта. Свойство **PSPath** показывает, что объект хранится в каталоге на диске WSMan:. `Get-ChildItem` (псевдоним `dir` ) Отображает элементы в `WSMan:\LocalHost\PlugIn` пути. К ним относятся новая конфигурация **MaintenanceShell** и две конфигурации по умолчанию, которые входят в состав PowerShell.

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

### Пример 5. Регистрация конфигурации сеанса с помощью скрипта запуска

В этом примере мы создадим и регистрируем конфигурацию сеанса **WithProfile** . Параметр **StartupScript** указывает PowerShell выполнить указанный скрипт для любого сеанса, использующего конфигурацию сеанса.

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

Скрипт содержит единственную команду, в которой используется запись с точками для запуска профиля **CurrentUserAllHosts** пользователя в текущей области сеанса.

Дополнительные сведения о профилях см. в разделе [about_Profiles](./About/about_Profiles.md). Дополнительные сведения о вызовах с использованием точки см. в разделе [about_Scopes](./About/about_Scopes.md).

## PARAMETERS

### -AccessMode

Включает и отключает конфигурацию сеанса и определяет возможность ее использования для удаленных или локальных сеансов компьютера. Допустимые значения для этого параметра:

- Отключена. отключает конфигурацию сеанса. Использовать конфигурацию для локального или удаленного доступа к компьютеру.
- Локальный. Позволяет пользователям локального компьютера использовать конфигурацию сеанса для создания локального сеанса замыкания на себя на том же компьютере, но запрещает доступ удаленным пользователям.
- Удаленный. позволяет локальным и удаленным пользователям использовать конфигурацию сеанса для создания сеансов и выполнить команды на этом компьютере.

Значение по умолчанию — Remote.

Другие командлеты могут переопределить значение этого параметра позже. Например, `Enable-PSRemoting` командлет разрешает удаленный доступ ко всем конфигурациям сеансов, `Enable-PSSessionConfiguration` командлет включает конфигурации сеанса, и `Disable-PSRemoting` командлет предотвращает удаленный доступ ко всем конфигурациям сеансов.

Этот параметр появился в PowerShell 3,0.

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

### -ApplicationBase

Указывает путь к файлу сборки ( \* . dll), указанному в значении параметра **AssemblyName** . Используйте этот параметр, если значение параметра **AssemblyName** не содержит путь. Значением по умолчанию является текущий каталог.

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

### -AssemblyName

Указывает имя файла сборки (\*.dll), в котором определен тип конфигурации. Путь к DLL-файлу можно указать в этом параметре или в значении параметра **ApplicationBase** .

Этот параметр является обязательным при указании параметра **ConfigurationTypeName** .

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

### -ConfigurationTypeName

задает полное имя типа Microsoft .NET Framework, используемого для этой конфигурации. Задаваемый тип должен реализовывать класс **System.Management.Automation.Remoting.PSSessionConfiguration**.

Чтобы указать файл сборки ( \* . dll), который реализует тип конфигурации, укажите параметры **AssemblyName** и **ApplicationBase** .

Создание типа позволяет управлять дополнительными аспектами конфигурации сеанса, такими как предоставление или скрытие определенных параметров командлетов, а также задание размера данных и ограничений размера объектов, которые пользователи не могут переопределить.

Если этот параметр не указан, для настройки конфигурации сеанса используется класс **DefaultRemotePowerShellConfiguration**.

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

### -Force

Подавляет все запросы пользователя и перезапускает службу **WinRM** без запроса. Перезапуск службы обеспечивает вступление изменений конфигурации в силу.

Чтобы предотвратить перезагрузку и отключить запрос на перезагрузку, укажите параметр **NoServiceRestart** .

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

### -MaximumReceivedDataSizePerCommandMB

Указывает предельный объем данных, которые могут быть отправлены на этот компьютер в любой отдельной удаленной команде. Введите размер данных в мегабайтах (МБ). Значение по умолчанию — 50 МБ.

Если ограничение на размер данных определено в типе конфигурации, заданном параметром **ConfigurationTypeName** , используется ограничение из типа конфигурации, а значение этого параметра игнорируется.

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

### -MaximumReceivedObjectSizeMB

Указывает предельный объем данных, которые могут быть отправлены на этот компьютер в любом отдельном объекте.
Введите размер данных в мегабайтах. Значение по умолчанию — 10 МБ.

Если ограничение на размер объекта определено в типе конфигурации, заданном параметром **ConfigurationTypeName** , используется ограничение из типа конфигурации, а значение этого параметра игнорируется.

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

### -ModulesToImport

Указывает модули, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.

По умолчанию в сеансы импортируются только **Microsoft. PowerShell. Core** . Если командлеты не исключены, можно использовать `Import-Module` для добавления модулей в сеанс.

Модули, указанные в этом значении параметра, импортируются в дополнение к модулям, заданным параметром **SessionType** , и значения, перечисленные в ключе **ModulesToImport** в файле конфигурации сеанса ( `New-PSSessionConfigurationFile` ). При этом параметры в файле конфигурации сеанса могут скрывать экспортируемые модулями команды или запрещать их использование.

Этот параметр появился в PowerShell 3,0.

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

### -Name

Указывает имя конфигурации сеанса. Этот параметр обязателен.

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

### -NoServiceRestart

Не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.

По умолчанию при выполнении `Register-PSSessionConfiguration` команды вам будет предложено перезапустить службу **WinRM** , чтобы обеспечить эффективную настройку нового сеанса. Пока служба **WinRM** не будет перезапущена, Новая конфигурация сеанса не вступит в силу.

Чтобы перезапустить службу **WinRM** без запроса, укажите параметр **Force** . Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.

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

### -Path

Указывает путь и имя файла конфигурации сеанса (. pssc), например, созданного `New-PSSessionConfigurationFile` . Если путь не указан, по умолчанию используется текущий каталог.

Этот параметр появился в PowerShell 3,0.

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

### -ProcessorArchitecture

Определяет, запускается ли 32-разрядная или 64-разрядная версия процесса PowerShell в сеансах, использующих эту конфигурацию сеанса. Допустимые значения для этого параметра: x86 (32-bit) и AMD64 (64-bit). Значение по умолчанию определяется архитектурой процессора компьютера, на котором размещена конфигурация сеанса.

Этот параметр можно использовать для создания 32-разрядного сеанса на 64-разрядном компьютере. Создать 64-разрядный процесс на 32-разрядном компьютере нельзя.

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

### -PSVersion

Указывает версию PowerShell в сеансах, использующих эту конфигурацию сеанса.

Значение этого параметра имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.

Этот параметр появился в PowerShell 3,0.

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

### -RunAsCredential

Указывает учетные данные для команд в сеансе. По умолчанию команды выполняются с разрешениями текущего пользователя.

Этот параметр появился в PowerShell 3,0.

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

### -SecurityDescriptorSddl

Задает строку в формате языка определения дескрипторов безопасности (SDDL) для конфигурации.

Эта строка определяет разрешения, необходимые для использования новой конфигурации сеанса. Чтобы использовать конфигурацию сеанса в сеансе, пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для конфигурации.

В случае сложного дескриптора безопасности вместо этого параметра можно использовать параметр **ShowSecurityDescriptorUI**. Использовать оба параметра в одной команде нельзя. Использовать оба параметра в одной и той же команде нельзя.

Если этот параметр не задан, для этой конфигурации используется корневой SDDL для службы **WinRM** .
Для просмотра или изменения корневого элемента SDDL используйте поставщик WS-Management. Например, `Get-Item wsman:\localhost\service\rootSDDL`. Для получения дополнительных сведений о поставщике WSMan введите `Get-Help wsman` .

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

### -SessionTypeOption

Задает параметры для конкретного типа конфигурации сеанса. Введите объект параметров типа сеанса, например объект **PSWorkflowExecutionOption** , `New-PSWorkflowExecutionOption` возвращаемый командлетом.

Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса. Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса. При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.

Этот параметр появился в PowerShell 3,0.

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

### -ShowSecurityDescriptorUI

Указывает, что этот командлет отображает страницу свойств, которая помогает создать SDDL для конфигурации сеанса. Страница свойств появляется после ввода `Register-PSSessionConfiguration` команды и перезапуска службы **WinRM** .

При задании разрешений для конфигурации Помните, что пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для использования конфигурации сеанса в сеансе.

Использовать этот параметр и параметр **SecurityDescriptorSDDL** в одной и той же команде нельзя.

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

### -StartupScript

Указывает полный путь к скрипту PowerShell. Указанный скрипт выполняется в новом сеансе, для которого используется данная конфигурация сеанса.

С помощью скрипта можно дополнительно настроить сеанс. Если скрипт создает ошибку, даже устранимую ошибку, сеанс не создается и `New-PSSession` команда завершается ошибкой.

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

### -ThreadOptions

Указывает, как потоки создаются и используются при выполнении команды в сеансе. Допустимые значения для этого параметра:

- По умолчанию
- реусесреад
- UseCurrentThread
- усеневсреад

Значение по умолчанию — **UseCurrentThread**.

Дополнительные сведения см. в разделе [перечисление пссреадоптионс](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).

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

### -TransportOption

Указывает параметр транспорта.

Этот параметр появился в PowerShell 3,0.

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

### -UseSharedProcess

Используйте только один процесс для размещения всех сеансов, запущенных одним и тем же пользователем, и используйте ту же конфигурацию сеанса. По умолчанию каждый сеанс размещается в отдельном процессе.

Этот параметр появился в PowerShell 3,0.

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

### -Confirm

Запрос подтверждения перед выполнением командлета.

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

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### -ThreadApartmentState

Указывает состояние апартамента для используемого модуля потоков. Допустимы следующие значения:

- Неизвестно
- MTA
- STA

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft.WSMan.Management.WSManConfigContainerElement

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .

Этот командлет создает XML-файл, представляющий веб-службы для конфигурации подключаемого модуля управления (WS-Management), и отправляет XML в WS-Management, который регистрирует подключаемый модуль на локальном компьютере ( `New-Item wsman:\localhost\plugin` ).

Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
