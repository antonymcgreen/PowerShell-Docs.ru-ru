---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 1cc0b0f51d84f3471bc3f54a91daba10f3528a8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228433"
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
Командлет **Debug-Process** присоединяет отладчик к одному или нескольким запущенным процессам на локальном компьютере.
Процессы можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID), или же можно передать объекты Process в этот командлет.

Этот командлет присоединяет отладчик, который в настоящее время зарегистрирован для процесса.
Перед использованием этого командлета убедитесь, что отладчик загружен и правильно настроен.

## Примеры

### Пример 1. подключение отладчика к процессу на компьютере

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

Эта команда присоединяет отладчик к процессу Windows PowerShell на компьютере.

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

Эта команда присоединяет отладчик к процессам Windows PowerShell на компьютере.
Он использует командлет **Get-Process** для получения процессов Windows PowerShell на компьютере и использует оператор конвейера (|) для отправки процессов в командлет **Debug-Process** .

Чтобы указать конкретный процесс PowerShell, используйте параметр ID командлета **Get-Process** .

### Пример 6. подключение отладчика к текущему процессу на локальном компьютере

```
PS C:\> $PID | Debug-Process
```

Эта команда присоединяет отладчик к текущим процессам Windows PowerShell на компьютере.

Команда использует автоматическую переменную $PID, которая содержит идентификатор процесса текущего процесса Windows PowerShell.
Затем он использует оператор конвейера (|) для отправки идентификатора процесса в командлет **Debug-Process** .

Дополнительные сведения об автоматической переменной $PID см. в разделе about_Automatic_Variables.

### Пример 7. подключение отладчика к указанному процессу на нескольких компьютерах

```
PS C:\> Get-Process -ComputerName "Server01", "Server02" -Name "MyApp" | Debug-Process
```

Эта команда присоединяет отладчик к процессам MyApp на компьютерах Server01 и Server02.

Команда использует командлет **Get-Process** для получения процессов MyApp на компьютерах Server01 и Server02.
Оператор конвейера (|) применяется для отправки процессов командлету Debug-Process, который присоединяет отладчики.

### Пример 8. подключение отладчика к процессу, использующему параметр InputObject

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

Эта команда присоединяет отладчик к процессам Windows PowerShell на локальном компьютере.

Первая команда использует командлет **Get-Process** для получения процессов Windows PowerShell на компьютере.
Он сохраняет полученный объект процесса в переменной с именем $P.

Вторая команда использует параметр *InputObject* командлета **Debug-Process** для отправки объекта процесса в переменную $P.

## PARAMETERS

### -Id
Указывает идентификаторы процессов, которые необходимо отладить.
Имя параметра *идентификатора* является необязательным.

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
Указывает объекты процессов, которые необходимо отладить.
Введите переменную, которая содержит объекты процесса, или команду, которая получает объекты процесса, например командлет Get-Process.
Вы также можете передать объекты Process в этот командлет.

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
Указывает имена процессов, которые необходимо отладить.
Если существует несколько процессов с одним и тем же именем, этот командлет присоединяет отладчик ко всем процессам с таким именем.
Параметр *Name* является необязательным.

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
Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Этот командлет использует метод AttachDebugger класса Win32_Process инструментария управления Windows (WMI). Дополнительные сведения об этом методе см. в разделе [метод аттачдебугжер](https://go.microsoft.com/fwlink/?LinkId=143640) в библиотеке MSDN.

## Связанные ссылки

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
