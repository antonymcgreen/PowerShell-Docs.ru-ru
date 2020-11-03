---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227842"
---
# Use-Transaction

## Краткий обзор
Добавляет блок сценариев в активную транзакцию.

## SYNTAX

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Use-Transaction** добавляет блок скрипта в активную транзакцию.
Это позволяет выполнять транзакции скриптов с помощью объектов Microsoft .NET Framework с поддержкой транзакций.
Этот блок сценариев может содержать только объекты Microsoft .NET Framework с поддержкой транзакций, например экземпляры класса Microsoft.PowerShell.Commands.Management.TransactedString.

Параметр *UseTransaction* , необязательный для большинства командлетов, является обязательным при использовании этого командлета.

**Use-Transaction**  — один из набора командлетов, которые поддерживают компонент транзакций в Windows PowerShell.
Дополнительные сведения см. в разделе about_Transactions.

## Примеры

### Пример 1. Выполнение скрипта с использованием объекта, поддерживающего транзакции

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

В этом примере показано, как использовать командлет **Use-Transaction** , чтобы выполнить скрипт для поддерживающего транзакции объекта .NET Framework.
В этом случае объект является объектом **TransactedString** .

Первая команда использует командлет Start-Transaction для запуска транзакции.

Вторая команда использует команду New-Object для создания объекта **TransactedString** .
Она хранит объект в переменной $TransactedString.

Третья и четвертая команды используют метод **append** объекта **TransactedString** для добавления текста к значению $TransactedString.
Одна команда входит в транзакцию,
а вторая — нет.

Третья команда использует метод **append** строки транзакции для добавления Hello к значению $TransactedString.
Так как команда не является частью транзакции, изменение вступает в силу немедленно.

Четвертая команда с помощью командлета **Use-Transaction** добавляет текст к строке в рамках транзакции.
Команда использует метод **append** для добавления ", мира" к значению $TransactedString.
Команда заключается в фигурные скобки ( {} ), чтобы сделать ее блоком сценария.
В этой команде требуется параметр *UseTransaction* .

Пятая и шестая команды используют метод **ToString** объекта **TransactedString** для вывода значения **TransactedString** в виде строки.
И снова одна команда входит в транзакцию,
а вторая — нет.

Пятая команда использует метод **ToString** для вывода текущего значения переменной $TransactedString.
Так как она не является частью транзакции, то отображает только текущее состояние строки.

Шестая команда использует командлет **Use-Transaction** для запуска той же команды внутри транзакции.
Так как команда не является частью, она отображает текущее значение строки внутри транзакции, так же, как предварительную версию изменений транзакции.

Седьмая команда использует командлет Complete-Transaction для отправки транзакции.

Последняя команда использует метод **ToString** для вывода результирующего значения переменной в виде строки.

### Пример 2. Откат транзакции

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

В этом примере показан результат отката транзакции, включающей команды **Use-Transaction** .
Как и все команды в транзакции при ее откате, изменения транзакций удаляются, и данные остаются неизменными.

Первая команда с помощью командлета **Start-Transaction** запускает транзакцию.

Вторая команда с помощью командлета **New-Object** создает объект **TransactedString** .
Она хранит объект в переменной $TransactedString.

Третья команда, не входящая в транзакцию, использует метод **append** для добавления "Hello" к значению $TransactedString.

Четвертая команда использует командлет **Use-Transaction** для запуска другой команды, использующей метод **Append** , внутри транзакции.
Команда использует метод **append** для добавления ", мира" к значению $TransactedString.

Пятая команда использует командлет Undo-Transaction для отката транзакции.
В результате все команды, выполненные в рамках транзакции, отменяются.

Последняя команда использует метод **ToString** для вывода результирующего значения $TransactedString в виде строки.
Из результатов видно, что к объекту применены только изменения, внесенные за рамками транзакции.

## PARAMETERS

### -TransactedScript
Указывает блок сценариев, выполняемых в транзакции.
Введите любой допустимый блок сценариев, заключенный в фигурные скобки( { } ).
Этот параметр обязателен.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction
Включает команду в активную транзакцию.
Этот параметр доступен только при выполнении транзакции.
Дополнительные сведения см. в разделе about_transactions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### PSObject
Этот командлет возвращает результат транзакции.

## ПРИМЕЧАНИЯ

* Параметр *UseTransaction* включает команду в активную транзакцию. Поскольку командлет **Use-Transaction** всегда используется в транзакциях, этот параметр необходим, чтобы команда **Use-Transaction** действовала.

*

## Связанные ссылки

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)
