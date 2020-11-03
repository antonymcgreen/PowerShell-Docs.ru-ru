---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 29a72bac55dd4aabca52673a192b13f75b88f308
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209033"
---
# Exit-PSHostProcess

## Краткий обзор
Закрывает интерактивный сеанс с локальным процессом.

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION
Командлет **Exit-PSHostProcess** закрывает интерактивный сеанс с локальным процессом, который был открыт, выполняя командлет Enter-PSHostProcess.
При завершении отладки или устранении неполадок скрипта, выполняемого в процессе, запускается командлет **Exit-PSHostProcess** из процесса.

## Примеры

### Пример 1. выход из процесса

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

В этом примере вы работали в активном процессе для отладки сценария, выполняющегося в пространстве выполнения процесса, как описано в разделе Ввод-PSHostProcess.
После ввода команды **Exit** для выхода из отладчика выполните командлет **Exit-PSHostProcess** , чтобы закрыть интерактивный сеанс с процессом.
Командлет закрывает сеанс в процессе и возвращает вас в строку PS C: \\ \> Prompt.

## PARAMETERS

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Enter-PSHostProcess](Enter-PSHostProcess.md)
