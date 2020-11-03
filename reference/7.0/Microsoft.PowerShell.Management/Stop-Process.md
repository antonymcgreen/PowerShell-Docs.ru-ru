---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: f5f5b8c912664c96762890633297f6325968f3fa
ms.sourcegitcommit: 11abf355ac545531c2b04217a08ebe6be609c0bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "93230669"
---
# Stop-Process

## Краткий обзор
Останавливает один или несколько запущенных процессов.

## SYNTAX

### Id (по умолчанию)

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### name

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Stop-Process** останавливает один или несколько запущенных процессов.
Процесс можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID) или передать объект **процесса в Process** .
Функция **останавливает-Process** работает только в процессах, запущенных на локальном компьютере.

В Windows Vista и более поздних версиях операционной системы Windows для завершения процесса, который не принадлежит текущему пользователю, необходимо запустить PowerShell с помощью команды Запуск от имени администратора.
Кроме того, запрос подтверждения не запрашивается, если не указан параметр *Confirm* .

## Примеры

### Пример 1. завершение всех экземпляров процесса

```
PS C:\> Stop-Process -Name "notepad"
```

Эта команда останавливает все экземпляры процесса Блокнота на компьютере.
Каждый экземпляр блокнота выполняется в собственном процессе.
В нем используется параметр *Name* для указания процессов, каждый из которых имеет одно и то же имя.
Если вы использовали параметр *ID* для завершения тех же процессов, необходимо перечислить идентификаторы каждого экземпляра блокнота.

### Пример 2. останавливает конкретный экземпляр процесса

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

Эта команда останавливает определенный экземпляр процесса Блокнота.
Для указания процесса в ней используется идентификатор процесса 3952.
Параметр *Confirm* направляет PowerShell запрос перед остановкой процесса.
Так как запрос содержит имя процесса, дополненное к ИДЕНТИФИКАТОРу, рекомендуется использовать его.
Параметр *PassThru* передает объект процесса модулю форматирования для вывода.
Без этого параметра отображение после команды " **прерывать процесс** " будет отсутствовать.

### Пример 3. остановка процесса и обнаружение его остановки

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

Эта серия команд запускает и останавливает процесс Calc, а затем обнаруживает остановленные процессы.

Первая команда запускает экземпляр калькулятора.

Вторая команда использует **Get-Process для получения** объекта, представляющего процесс Calc, и сохраняет его в переменной $p.

Третья команда останавливает процесс Calc.
Он использует параметр *InputObject* для передачи объекта в командлет **Processing** .

Последняя команда возвращает все процессы на компьютере, которые были запущены, но теперь остановлены.
Для получения всех процессов на компьютере используется **Get-Process** .
Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает, где значение свойства **хасекситед** равно $true.
**Хасекситед** — это только одно свойство объектов Process.
Чтобы найти все свойства, введите `Get-Process | Get-Member` .

### Пример 4. завершение процесса, не принадлежащего текущему пользователю

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'`
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

Эти команды показывают последствия использования *Force* для завершения процесса, который не принадлежит пользователю.

Первая команда использует **Get-Process** для получения процесса Lsass.
Оператор конвейера отправляет процесс для его отмены **процессом** .
Как показано в примере выходных данных, первая команда завершается с сообщением об отказе в доступе, так как этот процесс может быть остановлен только членом группы администраторов на компьютере.

При открытии PowerShell с параметром Запуск от имени администратора и повторной команде PowerShell запрашивает подтверждение.

Вторая команда указывает *Force* для подавления запроса.
В результате процесс останавливается без предупреждения.

## PARAMETERS

### -Force

Останавливает указанные параметры без запроса подтверждения.
По умолчанию **остановить-Process** запрашивает подтверждение перед остановкой процесса, который не принадлежит текущему пользователю.

Чтобы найти владельца процесса, используйте `Get-CimInstance` командлет для получения объекта **Win32_Process** , который представляет процесс, а затем используйте метод GetObject объекта. **GetOwner**

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

### -Id

Указывает идентификаторы процессов для завершения.
При указании нескольких идентификаторов разделяйте их запятыми.
Чтобы найти идентификатор процесса, введите `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Задает останавливаемые объекты процесса.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена процессов, которые нужно прерывать.
Можно ввести несколько имен процессов, разделенных запятыми, или использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Возвращает объект, представляющий процесс.
По умолчанию этот командлет не создает выходные данные.

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

### System.Diagnostics.Process

Объект процесса можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет, System. Диагностика. Process

Этот командлет возвращает объект **System. Diagnostics. Process** , представляющий остановленный процесс, если указан параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Можно также ссылаться на **остановить процесс** по его встроенным псевдонимам, **Kill** и **СППС** . Подробнее см. в разделе "about_Aliases".

  Также можно использовать свойства и методы **Win32_Process** объекта инструментарий управления Windows (WMI) (WMI) в Windows PowerShell.
Дополнительные сведения см `Get-CimInstance` . в разделе и пакете SDK для инструментария WMI.

* При остановке процессов следует понимать, что остановка процесса может остановить процесс и службы, зависящие от этого процесса.
В крайнем случае остановка процесса может привести к остановке Windows.

## Связанные ссылки

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
