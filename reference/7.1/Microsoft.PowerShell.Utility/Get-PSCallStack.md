---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: b551f50b024e5fd8083d853195eb9992587ca16c
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209314"
---
# Get-PSCallStack

## Краткий обзор
Отображает текущий стек вызовов.

## SYNTAX

```
Get-PSCallStack [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-PSCallStack** отображает текущий стек вызовов.

Хотя он предназначен для использования с отладчиком PowerShell, этот командлет можно использовать для вывода стека вызовов в скрипте или функции за пределами отладчика.

Чтобы выполнить команду **Get-PSCallStack** в отладчике, введите `k` или `Get-PSCallStack` .

## Примеры

### Пример 1. получение стека вызовов для функции

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

Эта команда использует командлет **Get-PSCallStack** для вывода стека вызовов для простой функции My-Alias, которая получает псевдонимы для имени командлета.

Первая команда вводит функцию в командной строке PowerShell.
Вторая команда использует командлет Set-PSBreakpoint, чтобы установить точку останова на функции My-Alias.
Третья команда использует функцию My-Alias, чтобы получить все псевдонимы в текущем сеансе для командлета Get-Content.

Отладчик останавливается на вызове функции.
Две последовательные команды step-into начинают построчное выполнение функции.
Затем для получения стека вызовов используется команда **Get-PSCallStack** .

Последняя команда Step-Out выходит из отладчика и продолжает выполнение скрипта до конца.

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### System. Management. Automation. Каллстаккфраме

Командлет **Get-PSCallStack** возвращает объект, представляющий элементы в стеке вызовов.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Format-Table](Format-Table.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)

