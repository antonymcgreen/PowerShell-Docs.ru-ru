---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226717"
---
# Disable-PSRemoting

## Краткий обзор
Предотвращает получение удаленных подключений конечными точками PowerShell.

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Disable-PSRemoting`Командлет блокирует удаленный доступ ко всем конфигурациям конечных точек сеанса Windows PowerShell на локальном компьютере. Сюда входят все конечные точки, созданные с помощью PowerShell 6 или более поздней версии.

Чтобы повторно включить удаленный доступ ко всем конфигурациям сеансов, используйте `Enable-PSRemoting` командлет. Сюда входят все конечные точки, созданные с помощью PowerShell 6 или более поздней версии. Чтобы включить удаленный доступ к выбранным конфигурациям сеанса, используйте параметр **AccessMode** `Set-PSSessionConfiguration` командлета.
Также можно использовать `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` командлеты и для включения и отключения конфигураций сеансов для всех пользователей. Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

> [!NOTE]
> Даже после запуска `Disable-PSRemoting` на локальном компьютере все равно можно выполнять замыкание соединений. Подключение по обратной связи — это удаленный сеанс PowerShell, который создается и подключается к тому же локальному компьютеру. Удаленные сеансы из внешних источников остаются заблокированными. Для соединений с замыканием на себя необходимо использовать неявные учетные данные в параметре **EnableNetworkAccess** . Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md).

Чтобы запустить этот командлет, запустите Windows PowerShell с параметром **Запуск от имени администратора** .

## Примеры

### Пример 1. Предотвращение удаленного доступа ко всем конфигурациям сеансов

В этом примере предотвращается удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Пример 2. Предотвращение удаленного доступа ко всем конфигурациям сеансов без запроса подтверждения

В этом примере предотвращается удаленный доступ ко всем конфигурациям конечных точек сеанса PowerShell без запроса.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Пример 3. последствия выполнения этого командлета

В этом примере показан результат использования `Disable-PSRemoting` командлета. Чтобы выполнить эту последовательность команд, запустите PowerShell с параметром **Запуск от имени администратора** .

После отключения конфигураций сеансов `New-PSSession` командлет пытается создать удаленный сеанс на локальном компьютере (также называемом "замыканием на себя"). Так как удаленный доступ отключен на локальном компьютере, команда завершается ошибкой.

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### Пример 4. влияние выполнения этого командлета и Enable-PSRemoting

В этом примере показано воздействие на конфигурации сеансов с помощью `Disable-PSRemoting` `Enable-PSRemoting` командлетов и.

`Disable-PSRemoting` используется для отключения удаленного доступа ко всем конфигурациям конечных точек сеанса PowerShell. Параметр **Force** блокирует вывод любых запросов для пользователей. `Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеанса на компьютере.

Выходные данные показывают, что всем удаленным пользователям с токеном сети отказано в доступе к конфигурациям конечных точек. Группе "Администраторы" на локальном компьютере разрешен доступ к конфигурациям конечных точек при условии, что они подключены локально (также называется замыканием на себя) и используют неявные учетные данные.

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

`Enable-PSRemoting`Командлет повторно включает удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере. Параметр **Force** подавляет все запросы пользователя и перезапускает службу WinRM без запроса. Новые выходные данные показывают, что дескрипторы безопасности **AccessDenied** были удалены из всех конфигураций сеансов.

### Пример 5. замыкание соединений с отключенными конфигурациями конечной точки сеанса

В этом примере показано, как отключены конфигурации конечных точек, а также показано, как выполнить успешное замыкание соединения с отключенной конечной точкой. `Disable-PSRemoting` отключает все конфигурации конечных точек сеанса PowerShell.

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

Первое использование `New-PSSession` пытается создать удаленный сеанс на локальном компьютере. Этот тип подключения проходит через сетевой стек и не является замыканием на себя. Следовательно, попытка подключения к отключенной конечной точке завершается сбоем с ошибкой **доступа** .

Второе использование `New-PSSession` также пытается создать удаленный сеанс для локального компьютера.
В этом случае он будет выполнен, так как это подключение с замыканием на себя, которое обходит сетевой стек.

Соединение с замыканием на себя создается при соблюдении следующих условий.

- Имя компьютера для подключения — localhost.
- Учетные данные не передаются. Текущий вошедший в систему пользователь (неявные учетные данные) используется для подключения.
- Используется параметр ключа **EnableNetworkAccess** .

Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md) Document.

### Пример 6. Предотвращение удаленного доступа к конфигурациям сеансов с пользовательскими дескрипторами безопасности

В этом примере показано, что `Disable-PSRemoting` командлет отключает удаленный доступ ко всем конфигурациям сеансов, включающим конфигурации сеансов с настраиваемыми дескрипторами безопасности.

`Register-PSSessionConfiguration` создает конфигурацию **тестового** сеанса. Параметр **FilePath** указывает файл конфигурации сеанса, который настраивает сеанс. Параметр **ShowSecurityDescriptorUI** отображает диалоговое окно, устанавливающее разрешения для конфигурации сеанса. В диалоговом окне разрешения мы создадим пользовательские разрешения на полный доступ для указанного пользователя.

`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеансов и их свойства. Выходные данные показывают, что конфигурация **тестового** сеанса разрешает интерактивный доступ и специальные разрешения для указанного пользователя.

`Disable-PSRemoting` отключает удаленный доступ ко всем конфигурациям сеансов.

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

Теперь `Get-PSSessionConfiguration` `Format-Table` командлеты и показывают, что дескриптор безопасности **AccessDenied** для всех пользователей сети добавлен во все конфигурации сеанса, включая конфигурацию **тестового** сеанса. Несмотря на то что другие дескрипторы безопасности не изменяются, дескриптор безопасности "network_deny_all" имеет приоритет. Это продемонстрировано попыткой использования `New-PSSession` для подключения к конфигурации **тестового** сеанса.

### Пример 7. Повторное включение удаленного доступа для выбранных конфигураций сеансов

В этом примере показано, как повторно включить удаленный доступ к определенным конфигурациям сеансов. После отключения всех конфигураций сеансов мы повторно включили конкретный сеанс.

`Set-PSSessionConfiguration`Командлет используется для изменения **Microsoft.** Конфигурация сеанса ServerManager. Параметр **AccessMode** со значением **Remote** повторно включает удаленный доступ к конфигурации.

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

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

### Нет

В этот командлет нельзя передать по конвейеру ни один объект.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- Отключение конфигураций сеансов не отменяет все изменения, внесенные `Enable-PSRemoting` `Enable-PSSessionConfiguration` командлетами или. Вам может потребоваться отменить указанные ниже изменения вручную.

  1. Остановка и отключение службы WinRM.
  2. Удаление прослушивателя, принимающего запросы по любому IP-адресу.
  3. Отключение исключений брандмауэра для соединений WS-Management.
  4. Восстановление нулевого значения параметра LocalAccountTokenFilterPolicy, при котором удаленный доступ на компьютере получают только участники группы "Администраторы".

  Конфигурация сеанса — это набор параметров, определяющих среду для сеанса. Каждый сеанс подключения к компьютеру должен использовать одну из конфигураций сеансов, зарегистрированных на компьютере. Запрещая удаленный доступ ко всем конфигурациям сеансов, вы в итоге запрещаете удаленным пользователям создавать сеансы подключения к компьютеру.

  В Windows PowerShell 2,0 `Disable-PSRemoting` добавляет запись Deny_All в дескрипторы безопасности всех конфигураций сеанса. Этот параметр запрещает всем пользователям создавать управляемые пользователем сеансы на локальном компьютере. В Windows PowerShell 3,0 `Disable-PSRemoting` добавляет запись Network_Deny_All в дескрипторы безопасности всех конфигураций сеанса. Этот параметр запрещает пользователям на других компьютерах создавать управляемые пользователем сеансы на локальном компьютере, но позволяет пользователям локального компьютера создавать управляемые пользователем сеансы замыкания на себя.

  В Windows PowerShell 2,0 `Disable-PSRemoting` является аналогом `Disable-PSSessionConfiguration -Name *` . В Windows PowerShell 3,0 и более поздних версиях `Disable-PSRemoting` является аналогом `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
