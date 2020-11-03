---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: 69d78550d68457c92deb3e4d690483bf742544b0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229349"
---
# Out-Printer

## Краткий обзор
Отправляет выходные данные на принтер.

## SYNTAX

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`Out-Printer`Командлет отправляет выходные данные на принтер по умолчанию или на другой принтер, если он указан.

> [!NOTE]
> Этот командлет был повторно введен в PowerShell 7. Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.

## Примеры

### Пример 1. Отправка файла для печати на принтере по умолчанию

В этом примере показано, как напечатать файл, даже если у `Out-Printer` него нет параметра **path** .

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

`Get-Content`Возвращает содержимое `readme.txt` файла в текущем каталоге и передает его в `Out-Printer` , который отправляется на принтер по умолчанию.

### Пример 2. Печать строки на удаленном принтере

В этом примере выполняется печать на `Hello, World` принтере **PRT-6B Color** на Server01.

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

Параметр **Name** выбирает конкретный принтер, а не используемый по умолчанию.

### Пример 3. Печать раздела справки на принтере по умолчанию

В этом примере выводится полная версия раздела справки для `Get-CimInstance` .

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

`Get-Help` Возвращает полную версию раздела справки для `Get-CimInstance` и сохраняет ее в `$H` переменной. Параметр **InputObject** передает значение `$H` в `Out-Printer` .

## PARAMETERS

### -InputObject

Указывает объекты, которые нужно передать на принтер. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

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

### -Name

Отправляет выходные данные на указанный принтер. **Имя параметра является** необязательным.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в `Out-Printer` .

## Выходные данные

### Нет

`Out-Printer` не возвращает никаких объектов.

## ПРИМЕЧАНИЯ

Командлеты, содержащие `Out` команду, не отформатируют объекты. Они просто отображают их и отправляют в указанное место назначения. При отправке неформатированного объекта в `Out` командлет командлет отправляет его в командлет форматирования перед отображением.

`Out-Printer` отправляет данные на принтер, но не выдает выходные объекты в конвейер. При передаче выходных данных `Out-Printer` в в `Get-Member` `Get-Member` сообщает о том, что объекты не указаны.

## Связанные ссылки

[Out-File](Out-File.md)

[Out-String](Out-String.md)

