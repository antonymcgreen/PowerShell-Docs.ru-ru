---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228405"
---
# Get-ComputerRestorePoint

## Краткий обзор
Получает точки восстановления на локальном компьютере.

## SYNTAX

### Идентификатор (по умолчанию)

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### LastStatus

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerRestorePoint`Командлет получает точки восстановления системы локального компьютера. Кроме того, он может отобразить состояние последней попытки восстановления компьютера.

`Get-ComputerRestorePoint`Для выбора точки восстановления можно использовать сведения из. Например, используйте порядковый номер для указания точки восстановления для `Restore-Computer` командлета.

Точки восстановления системы и `Get-ComputerRestorePoint` командлеты поддерживаются только в клиентских операционных системах, таких как Windows 10, Windows 7, Windows Vista и Windows XP.

## Примеры

### Пример 1. получение всех точек восстановления системы

В этом примере `Get-ComputerRestorePoint` получает все точки восстановления системы локального компьютера.

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### Пример 2. получение конкретных порядковых номеров

Этот пример получает точки восстановления системы для конкретных порядковых номеров.

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

`Get-ComputerRestorePoint` использует параметр **ресторепоинт** , чтобы указать разделенный запятыми массив порядковых номеров.

### Пример 3. Отображение состояния восстановления системы

В этом примере отображается состояние последнего восстановления системы на локальном компьютере.

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

`Get-ComputerRestorePoint` использует параметр **LastStatus** для вывода результатов последнего восстановления системы.

### Пример 4. Использование выражения для преобразования CreationTime

`Get-ComputerRestorePoint` выводит **CreationTime** в виде строки даты и времени инструментарий управления Windows (WMI) (WMI).

В этом примере переменная хранит выражение, преобразующее строку **CreationTime** в объект **DateTime** . Чтобы просмотреть строки **CreationTime** перед их преобразованием, используйте команду `((Get-ComputerRestorePoint).CreationTime)` . Дополнительные сведения о строке даты и времени WMI см. в разделе [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

`$date`Переменная хранит хэш-таблицу с выражением, использующим метод **ConvertToDateTime** . Выражение преобразует значение свойства **CreationTime** из строки WMI в объект **DateTime** .

`Get-ComputerRestorePoint` отправляет объекты точки восстановления системы по конвейеру. `Select-Object` использует параметр **Property** для указания отображаемых свойств. Для каждого объекта в конвейере выражение в `$date` преобразует **CreationTime** и выводит результат в свойстве **Date** .

### Пример 5. использование свойства для получения порядкового номера

Этот пример получает порядковый номер с помощью свойства **SequenceNumber** и индекса массива. Выходные данные содержат только порядковый номер.

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

`Get-ComputerRestorePoint` использует свойство **SequenceNumber** с индексом массива. Индекс массива `-1` возвращает последний порядковый номер в массиве.

## PARAMETERS

### -LastStatus

Указывает, что `Get-ComputerRestorePoint` получает состояние последней операции восстановления системы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ресторепоинт

Указывает порядковые номера точек восстановления системы. Можно указать либо один порядковый номер, либо разделенный запятыми массив порядковых номеров.

Если параметр **ресторепоинт** не указан, `Get-ComputerRestorePoint` возвращает все точки восстановления системы локального компьютера.

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете отправить объекты по конвейеру в `Get-ComputerRestorePoint` .

## Выходные данные

### System. Management. ManagementObject # Рут\дефаулт\системресторе или строка

`Get-ComputerRestorePoint` Возвращает объект **SystemRestore** , являющийся экземпляром класса инструментарий управления Windows (WMI) (WMI) **SystemRestore** .

При использовании параметра **LastStatus** `Get-ComputerRestorePoint` возвращает строку.

## ПРИМЕЧАНИЯ

Чтобы выполнить `Get-ComputerRestorePoint` команду в Windows Vista и более поздних версиях Windows, откройте PowerShell с параметром **Запуск от имени администратора** .

`Get-ComputerRestorePoint` использует класс **SYSTEMRESTORE** инструментария WMI.

## Связанные ссылки

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[SystemRestore](/windows/win32/sr/systemrestore)
