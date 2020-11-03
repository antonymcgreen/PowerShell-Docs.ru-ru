---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 212a745276a51fce2ec3b00ef59629d4480d8661
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229534"
---
# Enable-PSSessionConfiguration

## Краткий обзор
Включает конфигурации сеанса на локальном компьютере.

## SYNTAX

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-PSSessionConfiguration`Командлет активирует зарегистрированные конфигурации сеансов, которые были отключены, например с помощью `Disable-PSSessionConfiguration` `Disable-PSRemoting` командлетов или или параметра **AccessMode** `Register-PSSessionConfiguration` . Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.

Без параметров `Enable-PSSessionConfiguration` включает конфигурацию **Microsoft. PowerShell** , которая является конфигурацией по умолчанию, используемой для сеансов.

`Enable-PSSessionConfiguration` Удаляет параметр **Deny_All** из дескриптора безопасности затронутых конфигураций сеанса, включает прослушиватель, который принимает запросы по любому IP-адресу, и перезапускает службу WinRM. Начиная с PowerShell 3,0, `Enable-PSSessionConfiguration` также устанавливает значение true для свойства **Enabled** конфигурации сеанса ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ). Однако не `Enable-PSSessionConfiguration` удаляет или не изменяет **Network_Deny_All** `AccessMode=Local` параметр дескриптора безопасности Network_Deny_All (), который позволяет использовать в конфигурации сеанса только пользователи локального компьютера.

## Примеры

### Пример 1. Повторное включение сеанса по умолчанию

В этом примере повторно включается конфигурация сеанса **Microsoft. PowerShell** по умолчанию на компьютере.

```powershell
Enable-PSSessionConfiguration
```

### Пример 2. Повторное включение указанных сеансов

В этом примере повторно включаются конфигурации сеанса **MaintenanceShell** и **AdminShell** на компьютере.

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### Пример 3. Повторное включение всех сеансов

В этом примере повторно включаются все конфигурации сеансов на компьютере. Эти команды эквивалентны.
Таким образом, можно использовать любую из них.

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

`Enable-PSSessionConfiguration` не создает ошибку, если включена конфигурация сеанса, которая уже включена.

### Пример 4. Повторное включение сеанса и указание нового дескриптора безопасности

В этом примере повторно включается конфигурация сеанса **MaintenanceShell** и указывается новый дескриптор безопасности для конфигурации.

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## PARAMETERS

### -Force

Указывает, что командлет не запрашивает подтверждение и перезапускает службу WinRM без запроса. Перезапуск службы обеспечивает вступление изменений конфигурации в силу.

Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart** .

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

Указывает включаемые имена конфигураций сеанса. Введите одно или несколько имен конфигурации.
Можно использовать подстановочные знаки.

Можно также передать по конвейеру строку, содержащую имя конфигурации или объект конфигурации сеанса, в `Enable-PSSessionConfiguration` .

Если этот параметр не задан, `Enable-PSSessionConfiguration` включается Настройка сеанса **Microsoft. PowerShell** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -NoServiceRestart

Указывает, что командлет не перезапускает службу.

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

### -SecurityDescriptorSddl

Указывает дескриптор безопасности, на который этот командлет заменяет дескриптор безопасности в конфигурации сеанса.

Если опустить этот параметр, `Enable-PSSessionConfiguration` удаляется только элемент Deny All из дескриптора безопасности.

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

### -SkipNetworkProfileCheck

Указывает, что этот командлет включает конфигурацию сеанса, если компьютер находится в общедоступной сети. Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети. По умолчанию `Enable-PSSessionConfiguration` не работает в общедоступной сети.

Этот параметр предназначен для клиентских версий операционной системы Windows. Серверные версии операционной системы Windows имеют правило брандмауэра локальной подсети для общедоступных сетей. Но если правило брандмауэра локальной подсети отключено в серверной версии операционной системы Windows, этот параметр повторно включает его.

Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity. Для получения дополнительной информации см. `Enable-PSRemoting`.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String

Вы можете передать по конвейеру объект конфигурации сеанса или строку, которая содержит имя конфигурации сеанса в этот командлет.

## Выходные данные

### Нет

Этот командлет не создает никаких объектов.

## ПРИМЕЧАНИЯ

Чтобы использовать этот командлет, необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)

