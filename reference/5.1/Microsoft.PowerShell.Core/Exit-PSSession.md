---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession;
ms.openlocfilehash: 1e0c8413a37a9b8877b6af9089ac311459ada20d
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975113"
---
# Exit-PSSession;

## Краткий обзор
Завершает интерактивный сеанс с удаленным компьютером.

## SYNTAX

```
Exit-PSSession [<CommonParameters>]
```

## Описание

`Exit-PSSession`Командлет завершает интерактивные сеансы, запущенные с помощью `Enter-PSSession` командлета.

Можно также использовать `exit` ключевое слово для завершения интерактивного сеанса. Результат такой же, как и при использовании `Exit-PSSession` .

## Примеры

### Пример 1. Запуск и завершение интерактивного сеанса

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS C:\>
```

Эти команды создают и затем завершают интерактивный сеанс с удаленным компьютером Server01.

### Пример 2. Запуск и завершение интерактивного сеанса с помощью объекта PSSession

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

Эти команды запускают и останавливают интерактивный сеанс с компьютером Server01, использующим сеанс Windows PowerShell (**PSSession**).

Поскольку интерактивный сеанс запущен с помощью сеанса Windows PowerShell, сеанс **PSSession** по-прежнему доступен по окончании интерактивного сеанса. Если используется параметр _ComputerName_ , `Enter-PSSession` создает временный сеанс, который закрывается по окончании интерактивного сеанса.

Первая команда использует `New-PSSession` командлет для создания **сеанса PSSession** на компьютере Server01. Команда сохраняет **PSSession** в `$s` переменной.

Вторая команда использует `Enter-PSSession` для запуска интерактивного сеанса с использованием **PSSession** в `$s` .

Третья команда использует `Exit-PSSession` для завершения интерактивного сеанса.

Последняя команда отображает **PSSession** в `$s` переменной. Свойство **State** показывает, что **сеанс PSSession** по-прежнему открыт и доступен для использования.

### Пример 3. Использование ключевого слова Exit для завершения сеанса

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS C:\>
```

В этом примере используется `exit` ключевое слово для завершения интерактивного сеанса, запущенного с помощью `Enter-PSSession` . `exit`Ключевое слово имеет тот же результат, что и при использовании `Exit-PSSession` .

## Параметры

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Отсутствуют

Этот командлет не возвращает никакие выходные данные.

## Примечания

Этот командлет принимает только общие параметры.

## Связанные ссылки

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
