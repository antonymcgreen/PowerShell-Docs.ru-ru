---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: d8f7df3a4c7197b6cf62eecc0b0b314d9668de90
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225514"
---
# Invoke-Expression

## Краткий обзор
Выполняет команды или выражения на локальном компьютере.

## SYNTAX

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## DESCRIPTION

`Invoke-Expression`Командлет вычисляет или выполняет указанную строку в качестве команды и возвращает результаты выражения или команды. Без `Invoke-Expression` изменений строка, отправленная в командной строке, возвращается (вывод) не изменяется.

Выражения вычисляются и выполняются в текущей области. Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

> [!CAUTION]
> При использовании `Invoke-Expression` командлета в скриптах примите меры предосторожности. При использовании `Invoke-Expression` для выполнения команды, введенной пользователем, убедитесь, что команда является надежной для запуска перед ее запуском. Как правило, при создании сценариев лучше предусматривать предварительно определенные варианты входных данных, не допуская ввода данных в свободной форме.

## Примеры

### Пример 1. Вычисление выражения

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

В этом примере демонстрируется использование `Invoke-Expression` для вычисления выражения. Без `Invoke-Expression` выражение печатается, но не вычисляется.

Первая команда присваивает `Get-Process` переменной значение (String) `$Command` .

Вторая команда демонстрирует результат ввода имени переменной в командной строке. PowerShell возвращает строку.

Третья команда использует `Invoke-Expression` для вычисления строки.

### Пример 2. Запуск скрипта на локальном компьютере

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

Эти команды используют `Invoke-Expression` для запуска скрипта, TestScript.ps1 на локальном компьютере. Команды эквивалентны. Первый использует параметр **Command** для указания выполняемой команды.
Во втором используется оператор конвейера ( `|` ) для отправки строки команды `Invoke-Expression` .

### Пример 3. выполнение команды в переменной

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

В этом примере выполняется Командная строка, сохраненная в `$Command` переменной.

Командная строка заключается в одинарные кавычки, так как включает переменную, `$_` которая представляет текущий объект. Если он заключен в двойные кавычки, `$_` переменная будет заменена ее значением до сохранения в `$Command` переменной.

### Пример 4. получение и запуск примера справки по командлетам

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

Эта команда извлекает и выполняет первый пример в `Get-EventLog` разделе справки по командлетам.

Чтобы выполнить пример другого командлета, измените значение `$Cmdlet_name` переменной на имя командлета. И измените `$Example_number` переменную на номер примера, который требуется запустить. Команда завершается ошибкой, если номер примера недопустим.

## PARAMETERS

### -Command

Указывает команду или выражение для выполнения. Введите команду или выражение либо укажите переменную, которая содержит команду или выражение. Параметр **команды** является обязательным.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System. String или PSObject

Объект, представляющий команду, можно передать по конвейеру `Invoke-Expression` .
Используйте `$Input` автоматическую переменную для представления входных объектов в команде.

## Выходные данные

### PSObject

Возвращает выходные данные, формируемые вызванной командой (значение параметра **команды** ).

## ПРИМЕЧАНИЯ

В большинстве случаев вы вызываете выражения с помощью оператора Call PowerShell и достигаете тех же результатов.
Оператор Call является более безопасным методом. Дополнительные сведения см. в разделе [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).

## Связанные ссылки

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)
