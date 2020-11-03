---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 7a1f7e2879b0eeefe8771a5e5a8bf763e48ff106
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225613"
---
# Set-TraceSource

## Краткий обзор
Настраивает, запускает и останавливает трассировку компонентов PowerShell.

## SYNTAX

### заданный по умолчанию параметр

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### ремовеалллистенерссет

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### ремовефилелистенерссет

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Set-TraceSource** настраивает, запускает и останавливает трассировку компонента PowerShell.
С его помощью можно указать, какие компоненты следует трассировать и куда нужно отправить результат трассировки.

## Примеры

### Пример 1. Трассировка компонента ParameterBinding оболочки

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

Эта команда запускает трассировку для компонента ParameterBinding оболочки PowerShell.
Он использует параметр *Name* для указания источника трассировки, параметр *Option* для выбора событий трассировки ExecutionFlow, а параметр *PSHost* — для выбора прослушивателя узла PowerShell, который отправляет выходные данные в консоль.
Параметр *листенероптион* добавляет значения ProcessID и timestamp к префиксу сообщения трассировки.

### Пример 2. Завершение трассировки

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

Эта команда останавливает трассировку компонента ParameterBinding оболочки PowerShell.
Он использует параметр *Name* для выявления отслеживаемого компонента и параметр *ремовелистенер* для обнаружения прослушивателя трассировки.

## PARAMETERS

### -Отладчик

Указывает, что командлет отправляет выходные данные трассировки в отладчик.
Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Microsoft Visual Studio.
Данный параметр также определяет прослушиватель трассировки по умолчанию.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает файл, в который этот командлет отправляет выходные данные трассировки.
Данный параметр также определяет прослушиватель трассировки файла.
При использовании этого параметра для запуска трассировки используйте параметр *RemoveFileListener* , чтобы прерывать трассировку.

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что командлет перезаписывает файл, доступный только для чтения.
Используйте с параметром *FilePath* .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Листенероптион

Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.
Допустимые значения для этого параметра:

- Нет
- LogicalOperationStack
- Дата и время
- Отметка времени
- ProcessId
- Tидентификатор
- Части

Значение по умолчанию — None.

Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает, какие компоненты будут трассироваться.
Введите имя источника трассировки для каждого компонента.
Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Параметр-Option

Указывает тип отслеживаемых событий.
Допустимые значения для этого параметра:

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
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете.
По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSHost

ндикатес, что этот командлет отправляет выходные данные трассировки на узел PowerShell.
Данный параметр также определяет прослушиватель трассировки PSHost.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveFileListener

Прекращает трассировку, удаляя прослушиватель трассировки, связанный с указанным файлом.
Введите путь и имя выходного файла трассировки.

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ремовелистенер

Прекращает трассировку, удаляя прослушиватель трассировки.

Используйте следующие значения с *ремовелистенер* :

- Чтобы удалить PSHost (Console), введите `Host` .
- Чтобы удалить отладчик, введите `Debug` .
- Чтобы удалить все прослушиватели трассировки, введите `*` .

Чтобы удалить прослушиватель трассировки файлов, используйте параметр *RemoveFileListener* .

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
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

### System.String

Строку, содержащую имя, можно передать в командлет **Set-TraceSource** по конвейеру.

## Выходные данные

### None или System. Management. Automation. Пстрацесаурце

При использовании параметра *PassThru* командлет **Set-TraceSource** создает объект **System. Management. Automation. пстрацесаурце** , представляющий сеанс трассировки.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Трассировка — это метод, применяемый разработчиками для отладки и изменения программы. Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.

  Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.
Они позволяют отслеживать практически все аспекты функциональности PowerShell.

  Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.
Чтобы выполнить трассировку компонента, указать определить его источник трассировки.

  Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.
Вы можете выбрать отправку данных трассировки в отладчике пользовательского режима или в режиме ядра в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .

* Чтобы запустить трассировку, используйте параметр *Name* , чтобы указать источник трассировки, а также параметры *FilePath* , *Debugger* или *PSHost* , чтобы указать прослушиватель (назначение для выходных данных). Используйте параметр *Options* , чтобы определить типы отслеживаемых событий и параметр *листенероптион* для настройки выходных данных трассировки.
* Чтобы изменить конфигурацию трассировки, введите команду **Set-TraceSource** , как при запуске трассировки. PowerShell распознает, что источник трассировки уже отслеживается. Она остановит трассировку, добавит новую конфигурацию и запустит или перезапустит трассировку.
* Чтобы отключить трассировку, используйте параметр *ремовелистенер* . Чтобы отключить трассировку, использующую прослушиватель файла (трассировка, запущенная с помощью параметра *FilePath* ), используйте параметр *RemoveFileListener* . При удалении прослушивателя трассировка останавливается.
* Чтобы определить, какие компоненты можно трассировать, используйте командлет Get-TraceSource. Источники трассировки для каждого модуля загружаются автоматически при использовании компонента и отображаются в выходных данных **Get-TraceSource**.

## Связанные ссылки

[Get-TraceSource](Get-TraceSource.md)

[Trace-Command](Trace-Command.md)
