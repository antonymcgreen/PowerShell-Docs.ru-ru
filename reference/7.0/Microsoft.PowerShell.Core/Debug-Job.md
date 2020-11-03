---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 947fcea58ea32e34bdd0dc0129443ac5bc39c561
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226101"
---
# Debug-Job

## Краткий обзор
Выполняет отработку ошибок выполняемого фонового, удаленного или рабочего процесса PowerShell.

## SYNTAX

### Жобпараметерсет (по умолчанию)

```
Debug-Job [-Job] <Job> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобнамепараметерсет

```
Debug-Job [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобидпараметерсет

```
Debug-Job [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобинстанцеидпараметерсет

```
Debug-Job [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Debug-Job** позволяет выполнять отладку скриптов, выполняемых в заданиях.
Командлет предназначен для отладки заданий рабочего процесса PowerShell, фоновых заданий и заданий, выполняемых в удаленных сеансах.
**Debug — задание** принимает объект выполняемого задания, имя, идентификатор или идентификатор экземпляра в качестве входных данных и запускает сеанс отладки в выполняемом сценарии.
Команда **Quit** отладчика останавливает задание и запускает сценарий.
Начиная с Windows PowerShell 5,0, команда **Exit** отсоединяет отладчик и позволяет продолжить выполнение задания.

## Примеры

### Пример 1. Отладка задания по ИДЕНТИФИКАТОРу задания

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

Эта команда разбивается на выполняющееся задание с ИДЕНТИФИКАТОРом 3.

## PARAMETERS

### -Id
Указывает ИДЕНТИФИКАЦИОНный номер выполняемого задания.
Чтобы получить ИДЕНТИФИКАЦИОНный номер задания, выполните командлет Get-Job.

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
Указывает идентификатор GUID экземпляра выполняющегося задания.
Чтобы получить значение *InstanceId* задания, выполните командлет **Get-Job** , передав результаты в командлет **Format-** *, как показано в следующем примере:

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Указывает выполняющийся объект задания.
Самый простой способ использовать этот параметр — Сохранить результаты выполнения команды **Get-Job** , возвращающей выполняемое задание, которое необходимо отладить, в переменной, а затем указать переменную в качестве значения этого параметра.

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Указывает задание по понятному имени задания.
При запуске задания можно указать имя задания, добавив параметр *JobName* в командлетах, таких как Invoke-Command и Start-Job.

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
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

### System. Management. Automation. Ремотингжоб

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Wait-Job](Wait-Job.md)
