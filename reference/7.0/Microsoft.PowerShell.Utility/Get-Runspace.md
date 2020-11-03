---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 7d2dc7ce170d3f5de15fe5ad289e664e9f11847b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226042"
---
# Get-Runspace

## Краткий обзор
Возвращает активные пространства выполнения в хост-процессе PowerShell.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### идпараметерсет

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-Runspace`Командлет получает активные пространства выполнения в хост-процессе PowerShell.

## Примеры

### Пример 1. получение пространств выполнения

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### Пример 2. Получение пространства выполнения по идентификатору

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### Пример 3. Получение пространства выполнения по имени

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### Пример 4. Получение пространства выполнения по InstanceId

В этом примере мы выявлением доступного пространства выполнения с помощью `Name` параметра и сохраняем возвращаемый объект в переменной `$activeRunspace` . Это позволяет использовать свойства **пространства выполнения** при последующих запусках `Get-Runspace` .

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## PARAMETERS

### -Id

Указывает идентификатор пространства выполнения

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификатор GUID экземпляра выполняющегося задания.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает имя пространства выполнения

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
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

### System. Management. Automation. пространства выполнения

Результаты команды можно передать `Get-Runspace` в `Debug-Runspace` .

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Debug-Runspace](Debug-Runspace.md)
