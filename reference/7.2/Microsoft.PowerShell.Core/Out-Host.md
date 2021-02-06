---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: 4fefb133416b3db6c19c71a916d73fe00f86f3a4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604475"
---
# Out-Host

## Краткий обзор
Отправляет вывод в командную строку.

## SYNTAX

### Все

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`Out-Host`Командлет отправляет выходные данные на узел PowerShell для вывода. Основное приложение отображает вывод в командной строке. Поскольку параметр `Out-Host` является значением по умолчанию, нет необходимости указывать его, если не требуется использовать его параметры.

`Out-Host` автоматически добавляется к каждой выполняемой команде. Он передает выходные данные конвейера на узел, на котором выполняется команда. `Out-Host` игнорирует escape-последовательности ANSI. Управляющие последовательности обрабатываются узлом. `Out-Host` передает escape-последовательности ANSI на узел, не пытаясь интерпретировать или изменять их.

## Примеры

### Пример 1. Отображение выходных данных на одной странице за раз

Этот пример показывает, что система обрабатывается по одной странице за раз.

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

`Get-Process` Возвращает системные процессы и отправляет объекты по конвейеру. `Out-Host` использует параметр **разбиения по страницам** для одновременного вывода одной страницы данных.

### Пример 2. Использование переменной в качестве входных данных

В этом примере используются объекты, хранящиеся в переменной, в качестве входных данных для `Out-Host` .

```powershell
$io = Get-History
Out-Host -InputObject $io
```

`Get-History` Возвращает журнал сеанса PowerShell и сохраняет объекты в `$io` переменной.
`Out-Host` использует параметр **InputObject** для указания `$io` переменной и отображает журнал.

## PARAMETERS

### -InputObject

Задает объекты, которые будут выведены на консоль. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

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

### — Разбиение на страницы

Указывает, что `Out-Host` отображает одну страницу выходных данных за раз и ожидает ввода данных пользователем перед отображением оставшихся страниц. По умолчанию все выходные данные отображаются на одной странице. Размер страницы определяется характеристиками основного приложения.

Нажмите клавишу <kbd>пробел</kbd> , чтобы отобразить следующую страницу выходных данных, или клавишу <kbd>Ввод</kbd> , чтобы просмотреть следующую строку выходных данных. Нажмите клавишу <kbd>Q</kbd> , чтобы выйти.

**Подкачка страниц** аналогична команде **More** .

> [!NOTE]
> Параметр **подкачки** не поддерживается узлом интегрированной среды сценариев PowerShell.

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

Объекты можно отправить по конвейеру в `Out-Host` .

## Выходные данные

### None

`Out-Host` не создает никаких выходных данных. Он отправляет объекты на узел для вывода.

## ПРИМЕЧАНИЯ

Параметр **подкачки** не поддерживается всеми узлами PowerShell. Например, если вы используете параметр **разбиения по страницам** в интегрированной среде сценариев PowerShell, отображается следующая ошибка: `out-lineoutput : The method or operation is not implemented.`

Командлеты, которые содержат команду **out** , `Out-` не отформатируют объекты. Они визуализируют объекты и отправляют их в указанное назначение отображения. При отправке неформатированного объекта в `Out-` командлет командлет отправляет его в командлет форматирования перед отображением.

`Out-`Командлеты не имеют параметров для имен или путей к файлам. Чтобы отправить данные в `Out-` командлет, используйте конвейер для отправки выходных данных команды PowerShell в командлет. Или можно сохранить данные в переменной и использовать параметр **InputObject** для передачи данных в командлет.

`Out-Host` отправляет данные, но не создает никаких выходных объектов. Если выходные данные конвейера `Out-Host` `Get-Member` передаются в командлет, то `Get-Member` сообщает о том, что объекты не указаны.

## Связанные ссылки

[Clear-Host;](Clear-Host.md)

[Out-Default;](Out-Default.md)

[Out-File](../Microsoft.PowerShell.Utility/Out-File.md)

[Out-Null](Out-Null.md)

[Out-Printer](../Microsoft.PowerShell.Utility/Out-Printer.md)

[Out-String](../Microsoft.PowerShell.Utility/Out-String.md)

[Write-Host](../Microsoft.PowerShell.Utility/Write-Host.md)

