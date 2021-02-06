---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: a77695fe32345fda8e6a0284cd29becb432a4273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601506"
---
# Get-RunspaceDebug

## Краткий обзор
Показывает параметры отладки пространства выполнения.

## SYNTAX

### Рунспаценамепараметерсет (по умолчанию)

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### рунспацепараметерсет

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### рунспацеидпараметерсет

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### рунспацеинстанцеидпараметерсет

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### процесснамепараметерсет

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-RunspaceDebug`Командлет показывает параметры отладки пространства выполнения.

## Примеры

### 1: отображение состояния отладчика пространства выполнения по умолчанию

```powershell
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

[Disable-RunspaceDebug](Disable-RunspaceDebug.md)

[Enable-RunspaceDebug](Enable-RunspaceDebug.md)

