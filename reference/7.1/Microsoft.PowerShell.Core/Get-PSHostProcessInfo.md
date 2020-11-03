---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 655cc02e10bdb11092412271c16a002ab89089c3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229510"
---
# Get-PSHostProcessInfo

## Краткий обзор
Возвращает сведения о процессе для узла PowerShell.

## SYNTAX

### Процесснамепараметерсет (по умолчанию)

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### процесспараметерсет

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### процессидпараметерсет

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-PSHostProcessInfo`Командлет возвращает сведения о процессах узла PowerShell, запущенных на локальном компьютере.

Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.

## Примеры

### 1: получение списка узлов PowerShell, запущенных в системе

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### 2. Получение сведений об узле PowerShell для определенного имени процесса

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## PARAMETERS

### -Id

Указывает процесс по ИДЕНТИФИКАТОРу процесса. Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает процесс по имени процесса. Чтобы получить имя процесса, выполните `Get-Process` командлет.

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Process

Указывает процесс в объекте процесса. Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Diagnostics.Process

Объект **процесса** можно передать `Get-Process` в этот командлет по конвейеру.

## Выходные данные

### Microsoft. PowerShell. Commands. PSHostProcessInfo

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Process](../Microsoft.PowerShell.Management/get-process.md)

