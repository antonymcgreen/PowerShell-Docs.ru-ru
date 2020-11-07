---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 6dd0b6a997551aba0df2da666eb21dddeb2e1fcf
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344088"
---
# Enable-PSRemoting

## Краткий обзор
Настраивает прием удаленных команд на компьютере.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-PSRemoting`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии WS-Management. Удаленное взаимодействие PowerShell на основе WS-Management в настоящее время поддерживается только на платформе Windows.

Удаленное взаимодействие PowerShell включено по умолчанию на платформах Windows Server. С помощью можно `Enable-PSRemoting` включить удаленное взаимодействие PowerShell в других поддерживаемых версиях Windows и повторно включить удаленное взаимодействие, если оно будет отключено.

Эту команду необходимо выполнить только один раз на каждом компьютере, который будет принимать команды. Ее не нужно выполнять на компьютерах, которые только отправляют команды. Так как конфигурация запускает прослушиватели для приема удаленных подключений, целесообразно запускать ее только там, где это необходимо.

Включение удаленного взаимодействия PowerShell для клиентских версий Windows, когда компьютер находится в общедоступной сети, обычно запрещен, но это ограничение можно пропустить с помощью параметра **SkipNetworkProfileCheck** . Подробнее см. в описании параметра **SkipNetworkProfileCheck**.

Несколько установок PowerShell могут существовать параллельно на одном компьютере. `Enable-PSRemoting`При запуске будет настроена конечная точка удаленного взаимодействия для конкретной версии установки, в которой выполняется командлет. Поэтому при запуске `Enable-PSRemoting` powershell 6,2 будет настроена конечная точка удаленного взаимодействия, которая запускает powershell 6,2. При запуске `Enable-PSRemoting` PowerShell 7-Preview конечная точка удаленного взаимодействия будет настроена под управлением PowerShell 7-Preview.

`Enable-PSRemoting` При необходимости создает две конфигурации удаленной конечной точки. Если конфигурации конечных точек уже существуют, они просто гарантируют их включение. Созданные конфигурации идентичны, но имеют разные имена. У одной из них будет простое имя, соответствующее версии PowerShell, в которой размещен сеанс. Другое имя конфигурации содержит более подробные сведения о версии PowerShell, в которой размещен сеанс. Например, при выполнении `Enable-PSRemoting` в PowerShell 6,2 вы получите две настроенные конечные точки с именем **PowerShell. 6** , **PowerShell. 6.2.2**.
Это позволяет создать подключение к последней версии узла PowerShell 6 с помощью простого имени **PowerShell. 6**. Или можно подключиться к определенной версии узла PowerShell с помощью более длинного имени **PowerShell. 6.2.2**.

Чтобы использовать только что включенные конечные точки удаленного взаимодействия, необходимо указать их по имени с помощью параметра **configurationName** при создании удаленного соединения с `Invoke-Command` помощью `New-PSSession` `Enter-PSSession` командлетов,,. Дополнительные сведения см. в примере 4.

`Enable-PSRemoting`Командлет выполняет следующие операции:

- Выполняет командлет [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , который выполняет следующие задачи:
  - Запускает службу WinRM.
  - Задает автоматический тип запуска службы WinRM.
  - Создает прослушиватель для приема запросов по любому IP-адресу.
  - Включает исключение брандмауэра для WS-Management связи.
  - Создает простые и длинные конфигурации конечной точки сеанса, если это необходимо.
  - Включает все конфигурации сеансов.
  - Изменяет дескриптор безопасности всех конфигураций сеансов, чтобы разрешить удаленный доступ.
- Перезапускает службу WinRM, чтобы внести предыдущие изменения в силу.

Чтобы запустить этот командлет на платформе Windows, запустите PowerShell с помощью команды Запуск от имени администратора. Этот командлет недоступен в версиях PowerShell для Linux и MacOS.

> [!CAUTION]
> Этот командлет не влияет на конфигурации удаленных конечных точек, созданные Windows PowerShell.
> Он влияет только на конечные точки, созданные с помощью PowerShell версии 6 и выше. Чтобы включить и отключить удаленные конечные точки PowerShell, размещенные в Windows PowerShell, запустите `Enable-PSRemoting` командлет из сеанса Windows PowerShell.

## Примеры

### Пример 1. Настройка приема удаленных команд на компьютере

Эта команда настраивает прием удаленных команд на компьютере.

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### Пример 2. Настройка приема удаленных команд без запроса подтверждения на компьютере

Эта команда настраивает прием удаленных команд на компьютере.
Параметр **Force** подавляет запросы пользователя.

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
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

### Пример 4. Создание удаленного сеанса для вновь включенной конфигурации конечной точки

В этом примере показано, как включить удаленное взаимодействие PowerShell на компьютере, найти настроенные имена конечных точек и создать удаленный сеанс для одной из конечных точек.

Первая команда включает удаленное взаимодействие PowerShell на компьютере.

Вторая команда выводит список конфигураций конечных точек.

Третья команда создает удаленный сеанс PowerShell на том же компьютере, указывая конечную точку **PowerShell. 6** по имени. Удаленный сеанс будет размещен в последней версии PowerShell 6 (6.2.2).

Последняя команда обращается к `$PSVersionTable` переменной в удаленном сеансе, чтобы отобразить версию PowerShell, в которой размещается сеанс.

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

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

Этот командлет доступен только на платформах Windows.

В серверных версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, разрешающих удаленный доступ, и создает правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.

В клиентских версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, которые обеспечивают неограниченный удаленный доступ. Чтобы создать правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ из той же локальной подсети, используйте параметр **SkipNetworkProfileCheck**.

В клиентской или серверной версиях операционной системы Windows для создания правила брандмауэра для общедоступных сетей, которое удаляет ограничение локальной подсети и разрешает удаленный доступ, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity для выполнения следующей команды: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

`Enable-PSRemoting` включает все конфигурации сеансов, устанавливая для свойства **Enabled** всех конфигураций сеансов значение `$True` .

`Enable-PSRemoting` Удаляет параметры **Deny_All** и **Network_Deny_All** . Это обеспечивает удаленный доступ к конфигурациям сеансов, зарезервированным для локального использования.

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
