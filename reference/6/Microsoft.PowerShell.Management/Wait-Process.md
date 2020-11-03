---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 97b29f13fd1106a04204f97f02d82e9760fa41ae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226766"
---
# Wait-Process

## Краткий обзор
Ожидает остановки процессов, прежде чем принимать дополнительный ввод.

## SYNTAX

### Имя (по умолчанию)

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### Идентификатор

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### InputObject

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Wait-Process** ожидает остановки одного или нескольких запущенных процессов перед приемом входных данных.
В консоли PowerShell этот командлет подавляет командную строку до тех пор, пока процессы не будут остановлены.
Можно указать процесс по имени или ИДЕНТИФИКАТОРу процесса (PID) или передать объект процесса в **Wait-Process**.

**Wait-Process** работает только с процессами, запущенными на локальном компьютере.

## Примеры

### Пример 1. завершение процесса и ожидание

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

В этом примере останавливается процесс «Блокнот», а затем происходит ожидание остановки процесса, прежде чем продолжить выполнение следующей команды.

Первая команда использует командлет **Get-Process** для получения идентификатора процесса Блокнота.
Идентификатор сохраняется в переменной $nid.

Вторая команда использует командлет Stop-Process для завершения процесса с ИДЕНТИФИКАТОРом, хранящимся в $nid.

Третья команда использует **Wait-Process** для ожидания остановки процесса Блокнота.
Для идентификации процесса в нем используется параметр *идентификатора* **ожидания процесса** .

### Пример 2. Указание процесса

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

Эти команды демонстрируют три разных способа указания процесса **ожидания обработки**.
Первая команда получает процесс блокнота и сохраняет его в переменной $p.

Вторая команда использует параметр *ID* , третья команда использует параметр *Name* , а четвертая команда использует параметр *InputObject* .

Эти команды приводят к одинаковому результату и могут быть взаимозаменяемыми.

### Пример 3. Ожидание процессов в течение указанного времени

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

Эта команда 30 секунд ожидает окончания процессов Outlook и Winword.
Если оба процесса не остановлены, командлет отображает непрерывающую ошибку и командную строку.

## PARAMETERS

### -Id

Указывает идентификаторы процессов.
При указании нескольких идентификаторов разделяйте их запятыми.
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

Указывает процессы с помощью отправки объектов процессов.
Введите переменную, которая содержит объекты процесса, или введите команду или выражение, которое получает объекты процесса, например командлет Get-Process.

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

Указывает имя процессов.
При указании нескольких имен разделяйте их запятыми.
Подстановочные знаки не поддерживаются.

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

### -Timeout

Указывает максимальное время в секундах, в течение которого командлет ожидает завершения указанных процессов.
По истечении указанного времени команда отображает не прерывающую ошибку со списком еще выполняющихся процессов и завершает ожидание.
По умолчанию время ожидания отсутствует.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Diagnostics.Process

Объект процесса можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Этот командлет использует метод **ваитфорексит** класса System. Diagnostics. Process. Дополнительные сведения об этом методе см. в пакете SDK для Microsoft .NET Framework.

*

## Связанные ссылки

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
