---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 40d60ae57f4d2431defe0b176cbd0b786d5c1073
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347420"
---
# Exit-PSHostProcess

## Краткий обзор
Закрывает интерактивный сеанс с локальным процессом.

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION

`Exit-PSHostProcess`Командлет закрывает интерактивный сеанс с локальным процессом, который был открыт путем запуска `Enter-PSHostProcess` командлета. `Exit-PSHostProcess`Командлет запускается из процесса, когда завершается Отладка или устранение неполадок в скрипте, который выполняется в процессе. Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.

## Примеры

### Пример 1. выход из процесса

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

В этом примере вы работали в активном процессе для отладки сценария, выполняющегося в пространстве выполнения процесса, как описано в разделе `Enter-PSHostProcess` . После ввода `exit` команды для выхода из отладчика выполните `Exit-PSHostProcess` командлет, чтобы закрыть интерактивный сеанс с процессом.
Командлет закрывает сеанс в процессе и возвращает вас в `PS C:\>` командную строку.

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Enter-PSHostProcess](Enter-PSHostProcess.md)
