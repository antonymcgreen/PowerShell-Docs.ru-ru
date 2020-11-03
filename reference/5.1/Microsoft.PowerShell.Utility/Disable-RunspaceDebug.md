---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 79fe5c58f26f9146adfca18827f65cff53bde23f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227702"
---
# Disable-RunspaceDebug

## Краткий обзор
Отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.

## SYNTAX

### Рунспаценамепараметерсет (по умолчанию)

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### рунспацепараметерсет

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### рунспацеидпараметерсет

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### рунспацеинстанцеидпараметерсет

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### процесснамепараметерсет

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Disable-RunspaceDebug`Командлет отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.

## Примеры

### 1: отключить отладчик пространства выполнения по умолчанию

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
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

[Enable-RunspaceDebug](Enable-RunspaceDebug.md)

[Get-RunspaceDebug](Get-RunspaceDebug.md)
