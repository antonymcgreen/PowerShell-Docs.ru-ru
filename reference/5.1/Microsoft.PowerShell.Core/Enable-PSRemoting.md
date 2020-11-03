---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "93229685"
---
# Enable-PSRemoting

## Краткий обзор
Настраивает прием удаленных команд на компьютере.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-PSRemoting`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии WS-Management.

Удаленное взаимодействие PowerShell включено по умолчанию в Windows Server 2012. С помощью можно `Enable-PSRemoting` включить удаленное взаимодействие PowerShell в других поддерживаемых версиях Windows и повторно включить удаленное взаимодействие на Windows Server 2012, если оно будет отключено.

Эту команду необходимо выполнить только один раз на каждом компьютере, который будет принимать команды. Ее не нужно выполнять на компьютерах, которые только отправляют команды. Так как в такой конфигурации запускаются прослушиватели, мы рекомендуем использовать ее только при необходимости.

Начиная с PowerShell 3,0, `Enable-PSRemoting` командлет может включить удаленное взаимодействие PowerShell для клиентских версий Windows, когда компьютер находится в общедоступной сети. Подробнее см. в описании параметра **SkipNetworkProfileCheck** .

`Enable-PSRemoting`Командлет выполняет следующие операции:

- Выполняет командлет [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , который выполняет следующие задачи:
  - Запускает службу WinRM.
  - Задает автоматический тип запуска службы WinRM.
  - Создает прослушиватель для приема запросов по любому IP-адресу.
  - Включает исключение брандмауэра для WS-Management связи.
  - Регистрирует конфигурации сеанса **Microsoft. PowerShell** и **Microsoft. PowerShell. Workflow** , если они еще не зарегистрированы.
  - Регистрирует конфигурацию сеанса **Microsoft. PowerShell32** на 64-разрядных компьютерах, если она еще не зарегистрирована.
  - Включает все конфигурации сеансов.
  - Изменяет дескриптор безопасности всех конфигураций сеансов, чтобы разрешить удаленный доступ.
- Перезапускает службу WinRM, чтобы внести предыдущие изменения в силу.

Чтобы запустить этот командлет на платформе Windows, запустите PowerShell с помощью команды Запуск от имени администратора. Это не относится к версиям PowerShell для Linux и MacOS.

> [!CAUTION]
> В системах, где есть PowerShell 3,0 и PowerShell 2,0, не используйте PowerShell 2,0 для запуска `Enable-PSRemoting` `Disable-PSRemoting` командлетов и. Команды могут казаться выполненными успешно, но удаленный доступ будет настроен неправильно. Удаленные команды и последующие попытки включить или отключить удаленный доступ, скорее всего, будут завершаться сбоем.

## Примеры

### Пример 1. Настройка приема удаленных команд на компьютере

Эта команда настраивает прием удаленных команд на компьютере.

```powershell
Enable-PSRemoting
```

### Пример 2. Настройка приема удаленных команд без запроса подтверждения на компьютере

Эта команда настраивает прием удаленных команд на компьютере.
Параметр **Force** подавляет запросы пользователя.

```powershell
Enable-PSRemoting -Force
```

### Пример 3. Разрешение удаленного доступа для клиентов

В этом примере показано, как разрешить удаленный доступ из общедоступных сетей в клиентских версиях ОС Windows. Имя правила брандмауэра может отличаться для разных версий Windows.
Используйте `Get-NetFirewallRule` для просмотра списка правил. Перед включением правила брандмауэра просмотрите параметры безопасности в правиле, чтобы убедиться, что конфигурация подходит для вашей среды.

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

По умолчанию `Enable-PSRemoting` создает правила сети, разрешающие удаленный доступ из частных и доменных сетей. В команде используется параметр **SkipNetworkProfileCheck** для разрешения удаленного доступа из общедоступных сетей в той же локальной подсети. В команде указывается параметр **Force** , блокирующий вывод запросов подтверждения.

Параметр **SkipNetworkProfileCheck** не влияет на серверные версии операционной системы Windows, которые по умолчанию разрешают удаленный доступ из общедоступных сетей в той же локальной подсети.

`Set-NetFirewallRule`Командлет в модуле **NetSecurity** добавляет правило брандмауэра, которое разрешает удаленный доступ из общедоступных сетей из любого удаленного расположения. включая расположения в других подсетях.

> [!NOTE]
> Имя правила брандмауэра может отличаться в зависимости от версии Windows. Используйте `Get-NetFirewallRule` командлет, чтобы вывести список имен правил в системе.

## PARAMETERS

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

### -SkipNetworkProfileCheck

Указывает, что этот командлет включает удаленное взаимодействие в клиентских версиях ОС Windows, если компьютер находится в общедоступной сети. Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.

Этот параметр не оказывает влияния на серверные версии ОС Windows, в которых для общедоступных сетей по умолчанию задано правило брандмауэра локальной подсети. Если правило брандмауэра локальной подсети отключено на версии сервера, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.

Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .

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

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System.String

Этот командлет возвращает строки, которые описывают результаты его выполнения.

## ПРИМЕЧАНИЯ

В PowerShell 3,0 `Enable-PSRemoting` создает следующие исключения брандмауэра для WS-Management связи.

В серверных версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, разрешающих удаленный доступ, и создает правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.

В клиентских версиях операционной системы Windows `Enable-PSRemoting` в PowerShell 3,0 создаются правила брандмауэра для частных и доменных сетей, которые обеспечивают неограниченный удаленный доступ. Чтобы создать правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ из той же локальной подсети, используйте параметр **SkipNetworkProfileCheck** .

В клиентской или серверной версиях операционной системы Windows для создания правила брандмауэра для общедоступных сетей, которое удаляет ограничение локальной подсети и разрешает удаленный доступ, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity для выполнения следующей команды: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

В PowerShell 2,0 `Enable-PSRemoting` создает следующие исключения брандмауэра для WS-Management связи.

В серверных версиях ОС Windows он создает правила брандмауэра, разрешающие удаленный доступ, для всех сетей.

В клиентских версиях операционной системы Windows `Enable-PSRemoting` в PowerShell 2,0 создается исключение брандмауэра только для расположений домена и частных сетей. Чтобы снизить риски безопасности, не `Enable-PSRemoting` создает правило брандмауэра для общедоступных сетей в клиентских версиях Windows. Если текущее сетевое расположение является общедоступным, `Enable-PSRemoting` возвращает следующее сообщение: не удалось проверить состояние брандмауэра.

Начиная с версии PowerShell 3,0, `Enable-PSRemoting` включает все конфигурации сеанса, устанавливая для свойства **Enabled** всех конфигураций сеансов значение `$True` .

В PowerShell 2,0 `Enable-PSRemoting` удаляет параметр **Deny_All** из дескриптора безопасности конфигураций сеанса. В PowerShell 3,0 `Enable-PSRemoting` удаляет параметры **Deny_All** и **Network_Deny_All** . Это обеспечивает удаленный доступ к конфигурациям сеансов, зарезервированным для локального использования.

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
