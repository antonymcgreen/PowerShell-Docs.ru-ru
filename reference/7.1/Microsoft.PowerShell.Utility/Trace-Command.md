---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: c26e1c46db8f7c6eeeb5c970bc17921622cd023e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226538"
---
# Trace-Command

## Краткий обзор
Настраивает и запускает трассировку указанного выражения или команды.

## SYNTAX

### "выражение" (по умолчанию)

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### commandSet

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## DESCRIPTION
`Trace-Command`Командлет настраивает и запускает трассировку указанного выражения или команды.
Он аналогичен командлету Set-TraceSource за тем исключением, что его действие распространяется только на указанную команду.

## Примеры

### Пример 1. Обработка метаданных трассировки, привязка параметров и выражение

В этом примере запускается трассировка обработки метаданных, привязки параметров и создания и уничтожения `Get-Process Notepad` выражения.

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

Он использует параметр **Name** для указания источников трассировки, параметр **Expression** для указания команды и параметр **PSHost** для отправки выходных данных в консоль. Поскольку параметры трассировки и параметры прослушивателя не указаны, команда использует значения по умолчанию:

- Все для параметров трассировки
- Нет для параметров прослушивателя

### Пример 2. трассировка действий операций ParameterBinding оболочки

В этом примере отслеживаются действия **ParameterBinding оболочки** операций PowerShell во время обработки `Get-Alias` выражения, принимающего входные данные из конвейера.

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

В `Trace-Command` параметр **InputObject** передает объект в выражение, обрабатываемое во время трассировки.

Первая команда сохраняет строку `i*` в `$A` переменной. Вторая команда использует `Trace-Command` командлет с источником трассировки ParameterBinding оболочки. Параметр **PSHost** отправляет выходные данные в консоль.

Обрабатываемое выражение имеет значение `Get-Alias $Input` , где `$Input` переменная связана с параметром **InputObject** . Параметр **InputObject** передает переменную в `$A` выражение. По сути, команда, обрабатываемая во время трассировки, имеет значение `Get-Alias -InputObject $A" or "$A | Get-Alias` .

## PARAMETERS

### -ArgumentList

Указывает параметры и значения параметров для трассируемой команды. Псевдоним для **ArgumentList** — **Args**. Эта функция особенно полезна для отладки динамических параметров.

Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Указывает команду, обрабатываемую во время трассировки.

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Отладчик

Указывает, что командлет отправляет выходные данные трассировки в отладчик. Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Visual Studio. Данный параметр также определяет прослушиватель трассировки по умолчанию.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expression

Указывает выражение, обрабатываемое во время трассировки. Заключите выражение в фигурные скобки ( `{}` ).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает файл, в который командлет отправляет выходные данные трассировки. Данный параметр также определяет прослушиватель трассировки файла.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем. Используется с параметром **FilePath** . Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает входные данные для выражения, обрабатываемого во время трассировки. Можно ввести переменную, которая представляет выходные данные, принимаемые этим выражением, или передать объект по конвейеру.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Листенероптион

Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных. Допустимые значения для этого параметра:

- Нет
- LogicalOperationStack
- Дата и время
- Отметка времени
- ProcessId
- Tидентификатор
- Части

Значение по умолчанию — **None** .

Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает массив отслеживаемых компонентов PowerShell. Введите имя источника трассировки для каждого компонента. Разрешено использовать подстановочные знаки. Чтобы найти источники трассировки на компьютере, введите `Get-TraceSource` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Параметр-Option

Определяет тип трассируемых событий. Допустимые значения для этого параметра:

- Нет
- Конструктор
- Dispose
- Метод завершения
- Метод
- Свойство
- Делегаты
- События
- Исключение
- Блокировка
- Ошибка
- ошибки
- Предупреждение
- Подробный
- WriteLine
- Данные
- Область
- ExecutionFlow
- Assert
- Все

По умолчанию используется значение All.

Следующие значения являются комбинацией других значений:

- ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)
- Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)
- Ошибки: (ошибка и исключение).

Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSHost

Указывает, что командлет отправляет выходные данные трассировки на узел PowerShell. Данный параметр также определяет прослушиватель трассировки PSHost.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объекты, представляющие входные данные для выражения, можно передать в `Trace-Command` .

## Выходные данные

### System.Management.Automation.PSObject

Возвращает выходные данные трассировки в поток отладки.

## ПРИМЕЧАНИЯ

- Трассировка — это метод, применяемый разработчиками для отладки и изменения программы. Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.

- Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям. Они позволяют отслеживать практически все аспекты функциональных возможностей оболочки.

- Чтобы найти компоненты PowerShell, для которых включена трассировка, введите `Get-Help Get-TraceSource` .

  Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента. Чтобы выполнить трассировку компонента, указать определить его источник трассировки.

  Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю. Вы можете выбрать отправку данных трассировки в отладчик в пользовательском режиме или в режиме ядра, на узел или в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .

- Если используется набор параметров набора команд, PowerShell обрабатывает команду так же, как она будет обработана в конвейере. Например, обнаружение команды не повторяется для каждого поступающего объект

- **Имена,** **выражения** **, параметры и** **команды** не являются обязательными. Если имена параметров не заданы, то значения неименованных параметров должны отображаться в следующем порядке: **имя** , **выражение** , **параметр** или **имя** , **команда** , **параметр**. При указании имен параметры могут следовать в любом порядке.

## Связанные ссылки

[Get-TraceSource](Get-TraceSource.md)

[Measure-Command](Measure-Command.md)

[Set-TraceSource](Set-TraceSource.md)

