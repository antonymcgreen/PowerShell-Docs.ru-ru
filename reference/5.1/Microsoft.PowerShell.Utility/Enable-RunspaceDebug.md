---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 54fb9500a924d2e5de98489fa4fb391accb23d0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227701"
---
# Enable-RunspaceDebug

## Краткий обзор
Включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.

## SYNTAX

### Рунспаценамепараметерсет (по умолчанию)

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### рунспацепараметерсет

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### рунспацеидпараметерсет

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### рунспацеинстанцеидпараметерсет

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### процесснамепараметерсет

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Enable-RunspaceDebug`Командлет включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.

## Примеры

### 1: включить отладчик пространства выполнения по умолчанию

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## PARAMETERS

### -Аппдомаиннаме

Имя домена приложения, в котором размещается пространство выполнения PowerShell.

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BreakAll

Вызывает остановку любой выполняемой команды или скрипта в пространстве выполнения в пошаговом режиме, независимо от того, присоединен ли отладчик. Сценарий или команда будет оставаться остановленной до тех пор, пока не будет присоединен отладчик для отладки текущей точки останова.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessName

Имя процесса, в котором размещается пространство выполнения PowerShell.

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Пространство выполнения

Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Рунспацеид

Один или несколько идентификаторов **пространства выполнения** для отключения.

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рунспацеинстанцеид

Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рунспаценаме

Одно или несколько имен **пространства выполнения** , которые необходимо отключить.

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Disable-RunspaceDebug](Disable-RunspaceDebug.md)

[Get-RunspaceDebug](Get-RunspaceDebug.md)
