---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: f9cc2f83ec0fca1c957c670e13ac7b455c322adb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345352"
---
# Unregister-PSSessionConfiguration

## Краткий обзор
Удаляет зарегистрированные конфигурации сеанса с компьютера.

## SYNTAX

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Unregister-PSSessionConfiguration`Командлет удаляет зарегистрированные конфигурации сеанса с компьютера. Этот командлет предназначен для системных администраторов, позволяющих управлять настроенными конфигурациями сеансов для пользователей.

Чтобы внести изменение в силу, `Unregister-PSSessionConfiguration` перезапустите службу **WinRM** . Чтобы предотвратить перезагрузку, укажите параметр **NoServiceRestart** .

Если вы случайно удалили конфигурации сеанса **Microsoft. PowerShell** или **Microsoft. PowerShell32** по умолчанию, используйте `Enable-PSRemoting` командлет для их восстановления. Дополнительные сведения см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

## Примеры

### Пример 1. Удаление конфигурации сеанса

В этом примере удаляется конфигурация сеанса **MaintenanceShell** с компьютера.

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### Пример 2. Удаление конфигурации сеанса и перезапуск службы WinRM

В этом примере мы удалим конфигурацию **MaintenanceShell** и перезапустите службу WinRM. Параметр **Force** подавляет все пользовательские сообщения для перезапуска службы **WinRM** без запроса.

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### Пример 3. Удаление всех конфигураций сеансов

В этом примере показаны два способа удаления всех конфигураций сеансов на компьютере. Обе команды имеют одинаковый результат и могут использоваться взаимозаменяемыми.

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### Пример 4. Отмена регистрации без перезагрузки

В этом примере показан результат использования параметра **NoServiceRestart** для предотвращения перезапуска службы, которая приведет к нарушению сеансов на компьютере.

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

`Unregister-PSSessionConfiguration`Удаляет конфигурацию сеанса **MaintenanceShell** .
Однако, поскольку команда использует параметр **NoServiceRestart** , служба **WinRM** не перезапускается и изменение еще не полностью эффективно.

Затем `Get-PSSessionConfiguration` попытается получить сеанс **MaintenanceShell** . Поскольку сеанс был удален из таблицы ресурсов WS-Management, `Get-PSSessionConfiguration` он не может вернуть его.

`New-PSSession`Командлет создает сеанс, используя конфигурацию **MaintenanceShell** . Команда выполняется успешно. Затем перезапустите службу **WinRM** .

Наконец, `New-PSSession` командлет пытается создать сеанс, использующий конфигурацию **MaintenanceShell** . На этот раз сеанс завершается сбоем, так как конфигурация **MaintenanceShell** была удалена при перезапуске службы WinRM.

## PARAMETERS

### -Force

Указывает, что командлет не запрашивает подтверждение и перезапускает службу **WinRM** без запроса. Перезапуск службы обеспечивает вступление изменений конфигурации в силу.

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

### -Name

Указывает имена конфигураций сеансов, которые нужно удалить. Введите имя одной конфигурации сеанса или шаблон для отбора имен конфигураций. Можно использовать подстановочные знаки. Этот параметр обязателен.

Можно также передать конфигурации сеанса в `Unregister-PSSessionConfiguration` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoServiceRestart

Указывает, что этот командлет не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.

По умолчанию при выполнении `Unregister-PSSessionConfiguration` команды вам будет предложено перезапустить службу **WinRM** , чтобы изменения были эффективны. Пока служба **WinRM** не будет перезапущена, пользователи по-прежнему смогут использовать конфигурацию незарегистрированного сеанса, даже если `Get-PSSessionConfiguration` она не найдена.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft. PowerShell. Commands. Пссессионконфигуратионкоммандс # PSSessionConfiguration

Объект конфигурации сеанса можно передать `Get-PSSessionConfiguration` в командлет по конвейеру.

## Выходные данные

### Нет

Этот командлет не создает никаких объектов.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .

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

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
