---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 660d2b4845df8091ff8b69b28c4e7695af557122
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603948"
---
# Debug-Process

## Краткий обзор
Выполняет отладку одного или нескольких процессов, запущенных на локальном компьютере.

## SYNTAX

### Имя (по умолчанию)

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Debug-Process`Командлет присоединяет отладчик к одному или нескольким запущенным процессам на локальном компьютере.
Процессы можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID), или же можно передать объекты Process в этот командлет.

Этот командлет присоединяет отладчик, который в настоящее время зарегистрирован для процесса. Перед использованием этого командлета убедитесь, что отладчик загружен и правильно настроен.

## Примеры

### Пример 1. подключение отладчика к процессу на компьютере

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

Эта команда присоединяет отладчик к процессу PowerShell на компьютере.

### Пример 2. подключение отладчика ко всем процессам, начинающимся с указанной строки

```
PS C:\> Debug-Process -Name "SQL*"
```

Эта команда присоединяет отладчик ко всем процессам, имена которых начинаются с SQL.

### Пример 3. подключение отладчика к нескольким процессам

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

Эта команда присоединяет отладчик к процессам Winlogon, Explorer и Outlook.

### Пример 4. подключение отладчика к нескольким идентификаторам процессов

```
PS C:\> Debug-Process -Id 1132, 2028
```

Эта команда присоединяет отладчик к процессам с идентификатором 1132 и 2028.

### Пример 5. Использование Get-Process для получения процесса с последующим подключением к нему отладчика

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

Эта команда присоединяет отладчик к процессам PowerShell на компьютере. Он использует `Get-Process` командлет для получения процессов PowerShell на компьютере и использует оператор конвейера ( `|` ) для отправки процессов в `Debug-Process` командлет.

Чтобы указать конкретный процесс PowerShell, используйте параметр ID параметра `Get-Process` .

### Пример 6. подключение отладчика к текущему процессу на локальном компьютере

```
PS C:\> $PID | Debug-Process
```

Эта команда присоединяет отладчик к текущим процессам PowerShell на компьютере.

Команда использует `$PID` автоматическую переменную, которая содержит идентификатор процесса текущего процесса PowerShell. Затем он использует оператор конвейера ( `|` ) для отправки идентификатора процесса в `Debug-Process` командлет.

Дополнительные сведения об `$PID` автоматической переменной см. в разделе about_Automatic_Variables.

### Пример 7. подключение отладчика к процессу, использующему параметр InputObject

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

Эта команда присоединяет отладчик к процессам PowerShell на локальном компьютере.

Первая команда использует `Get-Process` командлет для получения процессов PowerShell на компьютере. Он сохраняет полученный объект процесса в переменной с именем `$P` .

Вторая команда использует параметр **InputObject** `Debug-Process` командлета для отправки объекта процесса в `$P` переменную.

## PARAMETERS

### -Id

Указывает идентификаторы процессов, которые необходимо отладить. Имя параметра **идентификатора** является необязательным.

Чтобы найти идентификатор процесса, введите `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Указывает объекты процессов, которые необходимо отладить. Введите переменную, которая содержит объекты процесса, или команду, которая получает объекты процесса, такие как `Get-Process` командлет. Вы также можете передать объекты Process в этот командлет.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена процессов, которые необходимо отладить. Если существует несколько процессов с одним и тем же именем, этот командлет присоединяет отладчик ко всем процессам с таким именем. Параметр **Name** является необязательным.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Int32, System. Diagnostics. Process, System. String

В этот командлет можно передать по конвейеру идентификатор процесса (Int32), объект процесса (System. Diagnostics. Process) или имя процесса (строка).

## Выходные данные

### None

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет использует метод AttachDebugger класса Win32_Process инструментария управления Windows (WMI). Дополнительные сведения об этом методе см. в разделе [метод аттачдебугжер](https://go.microsoft.com/fwlink/?LinkId=143640) в библиотеке MSDN.

## Связанные ссылки

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
