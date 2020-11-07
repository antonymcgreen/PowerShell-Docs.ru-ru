---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 788e7b9d261a862658f4cf7453f35228dd3ffab6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345856"
---
# Set-PSSessionConfiguration

## Краткий обзор
Изменяет свойства конфигурации зарегистрированного сеанса.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AssemblyNameParameterSet

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SessionConfigurationFile

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Set-PSSessionConfiguration`Командлет изменяет свойства конфигураций сеанса на локальном компьютере.

Используйте **Name** параметр, чтобы указать конфигурацию сеанса, которую требуется изменить. С помощью других параметров укажите новые значения свойств конфигурации сеанса. Чтобы удалить значение свойства из конфигурации и использовать значение по умолчанию, введите пустую строку ("") или значение `$Null` для соответствующего параметра.

Начиная с PowerShell 3,0 можно использовать файл конфигурации сеанса для определения конфигурации сеанса. Это простой метод для настройки и изменения свойств сеансов, которые используют одну конфигурацию. Чтобы указать файл конфигурации сеанса, используйте параметр **path** в `Set-PSSessionConfiguration` . Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).
Сведения о том, как создать и изменить файл конфигурации сеанса, см. в разделе `New-PSSessionConfigurationFile` командлет.

Конфигурации сеансов определяют среду удаленных сеансов ( **PSSession** ), которые подключаются к локальному компьютеру. В каждом сеансе **PSSession** используется конфигурация сеанса. Конфигурация сеанса определяет функции **PSSession** , такие как модули, доступные в сеансе, командлеты, которые разрешено запускать, языковой режим, квоты и время ожидания. Дескриптор безопасности конфигурации сеанса определяет, кто может использовать конфигурацию сеанса для подключения к локальному компьютеру. Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

Чтобы просмотреть свойства конфигурации сеанса, используйте `Get-PSSessionConfiguration` командлет или поставщик WSMan. Для получения дополнительных сведений о поставщике WSMan введите `Get-Help WSMan` .

## Примеры

### Пример 1. Создание и изменение конфигурации сеанса

В этом примере показано, как добавить и удалить скрипт запуска из конфигурации.

Первая команда создает конфигурацию **AdminShell** . Вторая команда добавляет `AdminConfig.ps1` скрипт в конфигурацию. Изменение вступает в силу при перезапуске **WinRM**.
Третья команда удаляет `AdminConfig.ps1` скрипт из конфигурации.

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### Пример 2. Отображение результатов

В этом примере значение свойства **максимумрецеиведобжектсиземб** увеличивается на 20. Эта команда также предлагает перезапустить службу **WinRM** . Изменения вступают в силу только после перезапуска службы **WinRM** .

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

### Пример 3. Отображение результатов различными способами

В этом примере `Set-PSSessionConfiguration` изменяет сценарий запуска в конфигурации сеанса **MaintenanceShell** на `Maintenance.ps1` . В выходных данных отобразится изменение и будет предложено перезапустить службу **WinRM** . Ответ: "y" (да).

`Get-PSSessionConfiguration` Возвращает конфигурацию сеанса **MaintenanceShell** . Оператор конвейера (|) отправляет результаты команды в `Format-List` , где отображаются все свойства объекта конфигурации в списке. Затем с помощью поставщика WSMan мы видим параметры инициализации для конфигурации **MaintenanceShell** . `Get-ChildItem` (псевдоним `dir` ) Возвращает дочерние элементы в узле **инитиализатионпараметерс** для подключаемого модуля **MaintenanceShell** . Для получения дополнительных сведений о поставщике WSMan введите `Get-Help wsman` .

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

## PARAMETERS

### -AccessMode

Включает и отключает конфигурацию сеанса и определяет возможность ее использования для удаленных или локальных сеансов компьютера. Допустимые значения для этого параметра:

- Отключена. отключает конфигурацию сеанса. Использовать конфигурацию для локального или удаленного доступа к компьютеру. Это значение задает для свойства **Enabled** конфигурации сеанса () значение `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` **false**.
- Локальный. Добавляет запись **Network_Deny_All** в дескриптор безопасности конфигурации сеанса.
  Пользователи локального компьютера могут использовать конфигурацию сеанса для создания локального сеанса замыкания на себя на том же компьютере, но удаленным пользователям отказано в доступе.
- Удаленный. Удаляет записи **Deny_All** и **Network_Deny_All** из дескрипторов безопасности конфигурации сеанса. Пользователи локальных и удаленных компьютеров могут применять конфигурацию сеанса для создания сеансов и выполнения команд на этом компьютере.

Значение по умолчанию — **Remote**.

Другие командлеты могут переопределить значение этого параметра позже. Например, `Enable-PSRemoting` командлет включает все конфигурации сеанса на компьютере и разрешает удаленный доступ к ним, а `Disable-PSRemoting` командлет разрешает только локальный доступ ко всем конфигурациям сеансов на компьютере.

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

Указывает путь к файлу сборки ( \* . dll), указанному в значении параметра **AssemblyName** .

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

Задает имя сборки. Этот командлет создает конфигурацию сеанса на основе класса, определенного в сборке.

Введите имя файла или полный путь к DLL-файлу сборки, который определяет конфигурацию сеанса. Если введено только имя файла, можно ввести путь в значении параметра **ApplicationBase** .

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

Указывает тип конфигурации сеанса, который определен в сборке в параметре **AssemblyName**. Задаваемый тип должен реализовывать класс **System.Management.Automation.Remoting.PSSessionConfiguration**.

Этот параметр является обязательным, если указано имя сборки.

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

Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart**.

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

Задает ограничение на объем данных, которые могут быть отправлены на этот компьютер в любой отдельной удаленной команде. Введите размер данных в мегабайтах (МБ). Значение по умолчанию — 50 МБ.

Если ограничение на размер данных определяется в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации. Значение этого параметра игнорируется.

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

Указывает ограничения на объем данных, которые могут быть отправлены на этот компьютер в любом отдельном объекте.
Введите размер данных в мегабайтах. Значение по умолчанию — 10 МБ.

Если ограничение размера объекта определено в типе конфигурации, указанном в параметре **ConfigurationTypeName** , используется ограничение в типе конфигурации. Значение этого параметра игнорируется.

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

### -ModulesToImport

Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса. Введите имена модулей и оснасток.

По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в сеансы, но если командлеты не исключены, можно использовать `Import-Module` командлеты и Add-PSSnapin, чтобы добавить модули и оснастки в сеанс.

Модули, указанные в этом значении параметра, импортируются в дополнение к модулям, указанным в файле конфигурации сеанса ( `New-PSSessionConfigurationFile` ). При этом параметры в файле конфигурации сеанса могут скрывать экспортируемые модулями команды или запрещать их использование.

Модули, указанные в этом значении параметра, заменяют список модулей, указанных **ModulesToImport** с помощью параметра ModulesToImport `Register-PSSessionConfiguration` командлета.

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

Указывает имя конфигурации сеанса, которую требуется изменить.

Этот параметр не может использоваться для изменения имени конфигурации сеанса.

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

По умолчанию при выполнении `Set-PSSessionConfiguration` будет предложено перезапустить службу **WinRM** , чтобы обеспечить эффективную настройку нового сеанса. Пока служба **WinRM** не будет перезапущена, Новая конфигурация сеанса не вступит в силу.

Чтобы перезапустить службу **WinRM** без запроса, используйте параметр **Force** . Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.

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

Указывает путь к файлу конфигурации сеанса (. pssc), например, созданному `New-PSSessionConfigurationFile` командлетом. Если путь не указан, по умолчанию используется текущий каталог.

Сведения о том, как изменить файл конфигурации сеанса, см. в разделе справки по `New-PSSessionConfigurationFile` командлету.

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

Задает другую строку SDDL для конфигурации.

Эта строка определяет разрешения, необходимые для использования новой конфигурации сеанса. Чтобы использовать конфигурацию сеанса в сеансе, пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для конфигурации.

Чтобы использовать для конфигурации дескриптор безопасности по умолчанию, введите пустую строку ("") или значение `$Null` . Значение по умолчанию — корневой SDDL на диске WSMan:.

Если дескриптор безопасности является сложным, рассмотрите возможность использования параметра **ShowSecurityDescriptorUI** вместо этого. Использовать оба параметра в одной и той же команде нельзя.

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

Указывает, что этот командлет является страницей свойств, помогающей создать новый SDDL для конфигурации сеанса. Страница свойств появляется после выполнения `Set-PSSessionConfiguration` команды и перезапуска службы **WinRM** .

При установке разрешений для конфигурации Помните, что пользователи должны иметь по крайней мере разрешение на выполнение (Invoke) для использования конфигурации сеанса в сеансе.

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

Указывает скрипт запуска для конфигурации. Введите полный путь к скрипту PowerShell. Указанный скрипт выполняется в новом сеансе, для которого используется данная конфигурация сеанса.

Чтобы удалить скрипт запуска из конфигурации сеанса, введите пустую строку ("") или значение `$Null` .

Для дальнейшей настройки сеанса пользователя можно использовать сценарий запуска. Если скрипт создает ошибку, даже устранимую ошибку, сеанс не создается и `New-PSSession` команда завершается ошибкой.

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

Указывает настройку параметров потока в конфигурации. Этот параметр определяет, как потоки создаются и используются при выполнении команды в сеансе. Допустимые значения для этого параметра:

- По умолчанию
- реусесреад
- UseCurrentThread
- усеневсреад

Значение по умолчанию — **UseCurrentThread**.

Дополнительные сведения см. в разделе [перечисление пссреадоптионс](/dotnet/api/system.management.automation.runspaces.psthreadoptions).

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

Задает параметры транспорта для конфигурации сеанса. Введите объект параметров транспорта, например объект **всманконфигуратионоптион** , `New-PSTransportOption` возвращаемый командлетом.

Параметры сеансов, которые используют конфигурацию сеанса, определяется значениями параметров сеанса и параметров конфигурации сеанса. Если не указано иное, параметры, заданные в сеансе, например с помощью `New-PSSessionOption` командлета, имеют приоритет над параметрами, заданными в конфигурации сеанса. При этом значения параметров сеанса не могут превышать максимальные значения, заданные в конфигурации сеанса.

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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

### Microsoft.WSMan.Management.WSManConfigLeafElement

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

Чтобы запустить этот командлет, запустите PowerShell с помощью команды Запуск от имени администратора.

`Set-PSSessionConfiguration`Командлет не изменяет имя конфигурации, а поставщик **WSMan** не поддерживает этот `Rename-Item` командлет. Чтобы изменить имя конфигурации сеанса, используйте `Unregister-PSSessionConfiguration` командлет для удаления конфигурации, а затем используйте `Register-PSSessionConfiguration` командлет для создания и регистрации новой конфигурации сеанса.

С помощью `Set-PSSessionConfiguration` командлета можно изменить конфигурации сеанса Microsoft. PowerShell и Microsoft. PowerShell32 по умолчанию. Они не защищены. Чтобы вернуться к исходной версии конфигурации сеанса по умолчанию, используйте командлет, `Unregister-PSSessionConfiguration` чтобы удалить конфигурацию сеанса по умолчанию, а затем используйте `Enable-PSRemoting` командлет для его восстановления.

Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

Вы можете использовать команды на диске WSMan:, чтобы изменить свойства конфигурации сеанса.
Однако нельзя использовать диск WSMan: в PowerShell 2,0 для изменения свойств конфигурации сеанса, которые представлены в PowerShell 3,0, например **аутпутбуфферингмоде**. Команды Windows PowerShell 2.0 не вызывают ошибку, но они являются неэффективными. Чтобы изменить свойства, появившиеся в PowerShell 3,0, используйте диск WSMan: в PowerShell 3,0.

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
