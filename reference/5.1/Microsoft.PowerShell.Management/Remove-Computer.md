---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227945"
---
# Remove-Computer

## Краткий обзор
Удаляет локальный компьютер из его домена.

## SYNTAX

### Local (по умолчанию)

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Удаленный доступ

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Remove-Computer`Командлет удаляет локальный компьютер и удаленные компьютеры из текущих доменов.

При удалении компьютера из домена `Remove-Computer` также отключает учетную запись домена компьютера. Необходимо предоставить явные учетные данные, чтобы отсоединить компьютер от своего домена, даже если они являются учетными данными текущего пользователя. Необходимо перезагрузить компьютер, чтобы изменения были эффективны. При удалении компьютера из домена необходимо переместить его в рабочую группу. Используйте параметр **WorkgroupName** для указания рабочей группы.

Чтобы переместить компьютер из рабочей группы в домен, из одной рабочей группы в другую или из одного домена в другой, используйте `Add-Computer` командлет.

Чтобы получить результаты выполнения команды, используйте параметры **Verbose** и **PassThru** . Чтобы скрыть запрос к пользователю, используйте параметр **Force** .

`Remove-Computer` удаляет локальный компьютер и удаленные компьютеры из доменов. Это включает в себя параметры учетных данных, в которых указаны альтернативные учетные данные для подключения к удаленным компьютерам и отсоединения от домена, параметр **Restart** для перезагрузки затронутых компьютеров, параметр **WorkgroupName** для указания имени рабочей группы, в которую добавляются компьютеры.

## Примеры

### Пример 1. Удаление локального компьютера из своего домена

В этом примере удаляется локальный компьютер из домена, к которому он присоединен.

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

Параметр **унжоиндомаинкредентиал** предоставляет учетные данные администратора домена. В общих параметрах **PassThru** и **verbose** отображаются сведения об успешном или неуспешном выполнении команды. Параметр **перезапуска** перезапускает компьютер для завершения операции удаления.

Если имя рабочей группы не указано, компьютер перемещается в рабочую группу с именем после удаления из домена.

### Пример 2. Перемещение нескольких компьютеров в устаревшую рабочую группу

Этот пример удаляет все компьютеры, перечисленные в `OldServers.txt` файле, из их доменов и перемещает их в **устаревшую** рабочую группу.

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

Параметр **локалкредентиал** предоставляет учетные данные пользователя, имеющего разрешение на подключение к удаленным компьютерам. Параметр **унжоиндомаинкредентиал** предоставляет учетные данные пользователя, имеющего разрешение на удаление компьютеров из их доменов. Параметр **Force** подавляет запросы на подтверждение для каждого компьютера. Параметр **перезапуска** перезапускает все компьютеры после удаления из своего домена.

### Пример 3. Удаление компьютеров из рабочей группы без подтверждения

В этом примере удаляется удаленный компьютер, Server01 и локальный компьютер из своих доменов, а затем они добавляются в **локальную** рабочую группу.

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

Параметр **Force** подавляет запрос на подтверждение для каждого компьютера. Параметр **перезапуска** перезапускает компьютеры, чтобы изменения были эффективны.

## PARAMETERS

### -ComputerName

Указывает компьютеры, удаляемые из своих доменов. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленных компьютеров. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, `Remove-Computer` даже если компьютер не настроен для выполнения удаленных команд.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

Скрывает запрос к пользователю. По умолчанию `Remove-Computer` запрашивает подтверждение перед удалением каждого компьютера.

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

### -Локалкредентиал

Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютерам, указанному параметром **ComputerName** . По умолчанию используется текущий пользователь.

Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя командлет запрашивает пароль. Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютера из текущего домена, используйте параметр **UnjoinDomainCredential** .

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает результаты выполнения команды. В противном случае командлет не формирует никаких выходных данных.

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

### -Restart

Указывает, что этот командлет перезапускает удаляемые компьютеры. Чтобы изменения вступили в силу, часто требуется перезагрузка.

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

### -Унжоиндомаинкредентиал

Указывает учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущих доменов.
Требуются явные учетные данные, как указано в этом параметре, для удаления удаленных компьютеров из домена, даже если это учетные данные текущего пользователя.

Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` . При вводе имени пользователя этот командлет запрашивает пароль.

Чтобы указать учетную запись пользователя, имеющую разрешение на подключение к удаленным компьютерам, используйте параметр **LocalCredential** .

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

Указывает имя рабочей группы, в которую добавляются компьютеры после удаления из их доменов. Значение по умолчанию — **Workgroup** . При удалении компьютера из домена необходимо добавить его в рабочую группу.

Этот параметр появился в PowerShell 3,0.

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

### System.String

Имена компьютеров можно передать в сискмдлет.

## Выходные данные

### Microsoft. PowerShell. Commands. Компутерчанжеинфо

При использовании параметра **PassThru** `Remove-Computer` возвращает объект **компутерчанжеинфо** .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет не удаляет компьютеры из рабочих групп.

## Связанные ссылки

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
