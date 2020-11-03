---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 978f42174d211d1ceaf7a19d4a348e1bbcaa270b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226718"
---
# Disable-PSSessionConfiguration

## Краткий обзор
Отключает конфигурации сеансов на локальном компьютере.

## SYNTAX

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Disable-PSSessionConfiguration`Командлет отключает конфигурации сеансов на локальном компьютере, что запрещает всем пользователям использовать конфигурации сеанса для создания управляемых пользователем сеансов ( **PSSession** ) на локальном компьютере. Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.

Начиная с PowerShell 3,0, `Disable-PSSessionConfiguration` командлет устанавливает для параметра **Enabled** в конфигурации сеанса () значение `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` false.

В PowerShell 2,0 `Disable-PSSessionConfiguration` командлет добавляет запись **Deny_All** в дескриптор безопасности одной или нескольких зарегистрированных конфигураций сеанса.

Без параметров `Disable-PSSessionConfiguration` отключает конфигурацию **Microsoft. PowerShell** — конфигурацию по умолчанию, используемую для сеансов. Если пользователь не указывает другую конфигурацию, командлет эффективно блокирует создание сеансов подключения к компьютеру локальными и удаленными пользователями.

Чтобы отключить все конфигурации сеансов на компьютере, используйте `Disable-PSRemoting` .

## Примеры

### Пример 1. Отключение конфигурации по умолчанию

Этот пример отключает конфигурацию сеанса Microsoft. PowerShell.

```powershell
Disable-PSSessionConfiguration
```

### Пример 2. Отключение всех конфигураций зарегистрированных сеансов

В этом примере отключаются все зарегистрированные конфигурации сеансов на компьютере.

```powershell
Disable-PSSessionConfiguration -Name *
```

### Пример 3. Отключение конфигураций сеансов по имени

В этом примере отключаются все конфигурации сеансов, имена которых начинаются с Microsoft. Параметр **Force** подавляет все запросы пользователя от командлета.

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### Пример 4. Отключение конфигураций сеанса с помощью конвейера

В этом примере отключаются конфигурации сеанса **MaintenanceShell** и **AdminShell** . Оператор конвейера (|) отправляет результаты в `Get-PSSessionConfiguration` `Disable-PSSessionConfiguration` .

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### Пример 5. последствия отключения конфигурации сеанса

В этом примере показаны разрешения до и после выполнения, `Disable-PSSessionConfiguration` а также действия по отключению конфигурации сеанса.

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> Отключение конфигурации не мешает изменить конфигурацию с помощью `Set-PSSessionConfiguration` командлета. Он только предотвращает использование конфигурации.

## PARAMETERS

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

Указывает массив имен конфигураций сеансов для отключения. Введите одно или несколько имен конфигурации. Можно использовать подстановочные знаки. Можно также передать по конвейеру строку, содержащую имя конфигурации или объект конфигурации сеанса, в `Disable-PSSessionConfiguration` .

Если этот параметр не задан, `Disable-PSSessionConfiguration` отключает конфигурацию сеанса Microsoft. PowerShell.

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

Используется для предотвращения перезапуска службы WSMan. Перезапускать службу для отключения конфигурации не требуется.

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

Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .

## Связанные ссылки

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
