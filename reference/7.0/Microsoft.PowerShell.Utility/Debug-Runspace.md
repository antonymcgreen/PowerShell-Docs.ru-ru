---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 1f347afe89ed63d64e8a8156b7259509800d5d24
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225709"
---
# Debug-Runspace

## Краткий обзор
Запускает интерактивный сеанс отладки с пространством выполнения.

## SYNTAX

### Рунспацепараметерсет (по умолчанию)

```
Debug-Runspace [-Runspace] <Runspace> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### намепараметерсет

```
Debug-Runspace [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### идпараметерсет

```
Debug-Runspace [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Debug-Runspace [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Debug-Runspace`Командлет запускает интерактивный сеанс отладки с локальным или удаленным активным пространством выполнения. Для поиска процессов, связанных с PowerShell, можно найти пространство выполнения, которое необходимо отладить `Get-Process` , `Enter-PSHostProcess` а затем указать идентификатор процесса, указанный в параметре **ID** , чтобы присоединиться к процессу, а затем `Get-Runspace` вывести список пространств в хост-процессе PowerShell.

После выбора пространства выполнения для отладки, если пространство выполнения в данный момент выполняет команду или сценарий или если скрипт остановлен в точке останова, PowerShell открывает сеанс удаленного отладчика для пространства выполнения. Скрипт пространства выполнения можно отлаживать таким же образом, как и сценарии удаленного сеанса.

Подключиться к хост-процессу PowerShell можно только при наличии прав администратора на компьютере, на котором выполняется процесс, или при запуске скрипта, который требуется отладить. Кроме того, невозможно ввести ведущий процесс, выполняющий текущий сеанс PowerShell. Можно ввести только ведущий процесс, выполняющий другой сеанс PowerShell.

## Примеры

### Пример 1. Отладка удаленного пространства выполнения

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

В этом примере выполняется отладка пространства выполнения, открытого на удаленном компьютере WS10TestServer. В первой строке команды вы запускаете `Get-Process` на удаленном компьютере и выполняете фильтрацию для процессов узла Windows PowerShell. В этом примере вы хотите отладить процесс с ИДЕНТИФИКАТОРом 1152, ведущий процесс Windows PowerShell ISE.

Во второй команде запускается, `Enter-PSSession` чтобы открыть удаленный сеанс на WS10TestServer. В третьей команде вы подключаетесь к ведущему процессу Windows PowerShell ISE, работающему на удаленном сервере, запустив `Enter-PSHostProcess` и УКАЗАВ идентификатор хостового процесса, полученный в первой команде 1152.

В четвертой команде вы перечислите доступные пространства выполнения для идентификатора процесса 1152, выполнив команду `Get-Runspace` .
Вы запомните ИДЕНТИФИКАЦИОНный номер занятого пространства выполнения; Он выполняет сценарий, который требуется отладить.

В последней команде вы начинаете отладку открытого пространства выполнения, в котором выполняется скрипт, TestWFVar1.ps1, путем запуска `Debug-Runspace` и идентификации пространства выполнения по его идентификатору (2) путем добавления параметра **ID** . Так как в скрипте есть точка останова, откроется отладчик.

## PARAMETERS

### -Id

Указывает ИДЕНТИФИКАЦИОНный номер пространства выполнения. Вы можете запустить `Get-Runspace` , чтобы отобразить идентификаторы пространства выполнения.

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Задает пространство выполнения по ИДЕНТИФИКАТОРу экземпляра, GUID, который можно отобразить, выполнив `Get-Runspace` .

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает пространство выполнения по имени. `Get-Runspace`Для отображения имен пространств выполнения можно запустить.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Пространство выполнения

Задает объект пространства выполнения. Самый простой способ предоставить значение для этого параметра — указать переменную, содержащую результаты фильтрованной `Get-Runspace` команды.

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: True
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
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. пространства выполнения

Результаты команды можно передать `Get-Runspace` в **Debug-пространство** с помощью конвейера.

## Выходные данные

## ПРИМЕЧАНИЯ

`Debug-Runspace` работает с пространствами выполнения, которые находятся в открытом состоянии. Если состояние выполнения изменяется с открытого на другое, это пространство выполнения автоматически удаляется из списка выполняемых. Пространство выполнения добавляется в выполняемый список только в том случае, если оно соответствует следующим критериям.

- Значение, если оно поступает из Invoke-Command; то есть у него есть `Invoke-Command` идентификатор GUID.
- Если он поступает из, то есть `Debug-Runspace` имеет `Debug-Runspace` идентификатор GUID.
- Если он поступает из рабочего процесса PowerShell, идентификатор задания рабочего процесса совпадает с идентификатором текущего активного задания рабочего процесса отладчика.

## Связанные ссылки

[about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[Debug-Job](../Microsoft.PowerShell.Core/Debug-Job.md)

[Get-Runspace](Get-Runspace.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Enter-PSHostProcess](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[Enter-PSSession](../Microsoft.PowerShell.Core/Enter-PSSession.md)
