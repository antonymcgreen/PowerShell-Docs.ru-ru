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
# Get-PSSessionConfiguration

## Краткий обзор
Получает зарегистрированные конфигурации сеанса на компьютере.

## SYNTAX

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`Get-PSSessionConfiguration`Командлет возвращает конфигурации сеанса, которые были зарегистрированы на локальном компьютере. Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.

Начиная с версии PowerShell 3,0 можно определить свойства конфигурации сеанса с помощью файла конфигурации сеанса (. pssc). Эта функция позволяет создавать настраиваемые и ограниченные сеансы, не создавая компьютерную программу. Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Кроме того, начиная с PowerShell 3,0 в объект конфигурации сеанса добавлены новые свойства примечаний, которые `Get-PSSessionConfiguration` возвращают. Эти свойства упрощают просмотр и сравнение конфигураций сеанса для пользователей и авторов конфигурации сеанса.

Чтобы создать и зарегистрировать конфигурацию сеанса, используйте `Register-PSSessionConfiguration` командлет.
Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

## Примеры

### Пример 1. получение конфигураций сеансов на локальном компьютере

```powershell
Get-PSSessionConfiguration
```

### Пример 2. получение двух конфигураций сеансов по умолчанию

Команда использует параметр **Name** параметра, `Get-PSSessionConfiguration` чтобы получить только конфигурации сеанса с именами, начинающимися с Microsoft.

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### Пример 3. получение свойств и значений конфигурации сеанса

В этом примере показаны свойства и значения свойств конфигурации сеанса, созданные с помощью файла конфигурации сеанса.

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

В примере командлет используется `Get-PSSessionConfiguration` для получения полной конфигурации сеанса. Оператор конвейера отправляет в командлет полную конфигурацию сеанса `Format-List` . Параметр **Property** со значением `*` (ALL) направляет `Format-List` Отображение всех свойств и значений объекта в списке.

Выходные данные включают в себя полезную информацию, включая автора конфигурации сеанса, тип сеанса, языковой режим и политику выполнения сеансов, созданных с помощью этой конфигурации сеанса, квоты сеанса и полный путь к файлу конфигурации сеанса.

Это представление конфигурации сеанса используется для сеансов, которые включают файл конфигурации сеанса.
Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

### Пример 4. другой способ просмотра конфигураций сеансов

В этом примере используется `Get-ChildItem` командлет (Alias `dir` ) на диске WSMan: Provider для просмотра содержимого узла подключаемого модуля. Это еще один способ просмотра конфигураций сеанса на компьютере.

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

Узел **подключаемого модуля** содержит объекты **контаинерелемент** (Microsoft. WSMan. Management. всманконфигконтаинерелемент), которые представляют зарегистрированные конфигурации сеансов PowerShell, а также другие подключаемые модули для WS-Management.

### Пример 6. Просмотр конфигураций сеансов на удаленном компьютере

В этом примере показано, как использовать поставщик WSMan для просмотра конфигураций сеанса на удаленном компьютере. Этот метод не предоставляет столько сведений `Get-PSSessionConfiguration` , сколько команда, но пользователю не обязательно быть членом группы администраторов для выполнения этого командлета.

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

`Connect-WSMan`Командлет подключается к службе WinRM на удаленном компьютере Server01. `Get-ChildItem`Командлет (псевдоним `dir` ) для диска WSMan: получает элементы в пути **Server01\Plugin** . В выходных данных показаны элементы в каталоге подключаемого модуля на компьютере Server01. Элементы включают конфигурации сеанса, которые являются типом подключаемого модуля WSMan, а также другие типы подключаемых модулей компьютера.

### Пример 7. Получение подробных сведений о конфигурациях сеанса с удаленного компьютера

В этом примере показано, как выполнить `Get-PSSessionConfiguration` команду на удаленном компьютере. Для команды требуется включенное делегирование CredSSP в параметрах клиента на локальном компьютере и в параметрах службы на удаленном компьютере.

Для выполнения команд в этом примере необходимо быть членом группы "Администраторы" на локальном и удаленном компьютерах, и необходимо запустить PowerShell с параметром " **Запуск от имени администратора** ".

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

`Enable-WSManCredSSP`Командлет включает делегирование **CredSSP** на Server01, локальный компьютер. `Connect-WSMan`Командлет подключается к компьютеру Server02. Это действие добавляет узел для Server02 на диск WSMan: на локальном компьютере, позволяя просматривать и изменять параметры WS-Management на компьютере Server02. `Set-Item`Командлет изменяет значение элемента **CredSSP** в узле службы Server02 компьютера на **true** . Это настраивает параметры службы на удаленном компьютере. `Invoke-Command`Командлет выполняет `Get-PSSessionConfiguration` команду на компьютере Server02. Команда использует параметр **Credential** , который использует параметр **Authentication** со значением **CredSSP** . В выходных данных показаны конфигурации сеанса на удаленном компьютере Server02.

### Пример 8. Получение URI ресурса конфигурации сеанса

Этот пример полезен для задания значения `$PSSessionConfigurationName` привилегированной переменной, которая принимает URI ресурса.

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

`$PSSessionConfigurationName`Переменная указывает конфигурацию по умолчанию, используемую при создании сеанса. Эта переменная задается на локальном компьютере, но она указывает конфигурацию на удаленном компьютере. Дополнительные сведения о `$PSSessionConfiguration` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

## PARAMETERS

### -Force

Скрывает запрос на перезапуск службы WinRM, если служба еще не запущена.

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

### -Name

Получает только конфигурации сеанса с указанным именем или шаблоном имени. Введите одно или несколько имен конфигураций сеанса. Разрешено использовать подстановочные знаки.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft. PowerShell. Commands. Пссессионконфигуратионкоммандс # PSSessionConfiguration

## ПРИМЕЧАНИЯ

- Чтобы запустить этот командлет, запустите PowerShell с параметром **Запуск от имени администратора** .

- Чтобы просмотреть конфигурации сеанса на компьютере, необходимо быть членом группы администраторов на компьютере.

- Чтобы выполнить `Get-PSSessionConfiguration` команду на удаленном компьютере, необходимо включить проверку подлинности поставщика службы безопасности учетных данных (CredSSP) в параметрах клиента на локальном компьютере (с помощью `Enable-WSManCredSSP` командлета) и в параметрах службы на удаленном компьютере. Кроме того, при установлении удаленного сеанса необходимо использовать значение **CredSSP** параметра **authentication** . В противном случае доступ будет запрещен.

- Свойства примечаний объекта, `Get-PSSessionConfiguration` возвращаемого в объекте, отображаются только в том случае, если они имеют значение. Только конфигурации сеансов, созданные с помощью файла конфигурации сеанса, имеют все определенные свойства.

- Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

- Вы можете использовать команды на диске WSMan:, чтобы изменить свойства конфигурации сеанса.
  Однако нельзя использовать диск WSMan: в PowerShell 2,0 для изменения свойств конфигурации сеанса, которые представлены в PowerShell 3,0, например **аутпутбуфферингмоде** . Команды PowerShell 2,0 не вызывают ошибку, но они неэффективны. Чтобы изменить свойства, появившиеся в PowerShell 3,0, используйте диск WSMan: в PowerShell 3,0.

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
