---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231053"
---
# Export-Counter

## Краткий обзор
Экспортирует данные счетчика производительности в файлы журнала.

## SYNTAX

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## DESCRIPTION

`Export-Counter`Командлет экспортирует данные счетчика производительности (объекты PerformanceCounterSampleSet) в файлы журнала в двоичном файле журнала производительности (. blg), с разделителями-запятыми (CSV) или в формате с разделителями-символами табуляции (TSV). Этот командлет используется для записи данных счетчика производительности.

`Export-Counter`Командлет предназначен для экспорта данных, возвращаемых `Get-Counter` `Import-Counter` командлетами и.

Этот командлет выполняется только в Windows 7, Windows Server 2008 R2 и более поздних версиях Windows.

## Примеры

### Пример 1. экспорт данных счетчиков в файл

В этом примере данные счетчика экспортируются в BLG-файл.

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

Команда использует `Get-Counter` командлет для получения данных о времени процессора. Для отправки данных в командлет используется оператор конвейера (|) `Export-Counter` . `Export-Counter`Команда использует переменную **path** для указания выходного файла.

Так как набор данных может быть очень большим, в этом примере данные отправляются `Export-Counter` через конвейер. Если данные были сохранены в переменной, то можно использовать непропорциональное количество памяти.

### Пример 2. Экспорт файла в формат файла счетчика

В этом примере CSV-файл преобразуется в формат BLG данных счетчика.

`Import-Counter`Командлет импортирует данные счетчика производительности из `Threads.csv` файла. В примере предполагается, что этот файл был ранее экспортирован с помощью `Export-Counter` командлета. Оператор конвейера ( `|` ) отправляет импортированные данные в `Export-Counter` командлет. Команда использует параметр **Path** , чтобы указать расположение выходного файла. Он использует параметры **циклического** и **MAXSIZE** , чтобы направить `Export-Counter` командлету создание циклического журнала, который включает в себя 1 ГБ. Параметр **MAXSIZE** выражается в мегабайтах.

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### Пример 3. получение данных счетчика с удаленного компьютера и сохранение данных в файле

В этом примере показано, как получить данные счетчиков производительности с удаленного компьютера и сохранить данные в файл на удаленном компьютере.

Первая команда использует `Get-Counter` командлет для получения данных счетчика рабочего набора из Server01, удаленного компьютера. Команда сохраняет данные в `$C` переменной.

Вторая команда использует оператор конвейера ( `|` ) для отправки данных в `$C` `Export-Counter` командлет, который сохраняет его в `Workingset.blg` файле в общей папке производительности на компьютере Server01.

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### Пример 4. повторное ведение журнала существующих данных

В этом примере показано, как использовать `Import-Counter` `Export-Counter` командлеты и для повторного ведения журнала существующих данных.

Первая команда использует `Import-Counter` командлет для импорта данных счетчиков производительности из журнала места. blg. Данные сохраняются в `$All` переменной. Этот файл содержит примеры \% счетчика "свободное место на диске" на более чем 200 удаленных компьютерах в Организации.

Вторая команда использует `Where-Object` командлет для выбора объектов с **кукедвалуе** менее 15 (процентов). Команда сохраняет результаты в `$LowSpace` переменной.

Третья команда использует конвейерный оператор ( `|` ) для отправки данных `$LowSpace` переменной в `Export-Counter` командлет. Команда использует параметр **Path** , чтобы указать, что выбранные данные следует зарегистрировать в файле LowDiskSpace.blg.

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## PARAMETERS

### -Циклический

Указывает, что выходной файл является циклическим журналом с первым в, первым выходом (FIFO).
Если вы включаете этот параметр, необходимо указать параметр **MaxSize**.

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

### -FileFormat

Задает выходной формат выходного файла журнала.

Допустимые значения для этого параметра:

- CSV
- TSV
- BLG

Значение по умолчанию: BLG.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Перезаписывает и заменяет существующий файл, если он существует в расположении, указанном параметром **path** .

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

### -InputObject

Указывает в виде массива данные счетчика для экспорта. Введите переменную, которая содержит данные, или команду, которая получает данные, например `Get-Counter` `Import-Counter` командлет или.

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaxSize

Указывает максимальный размер выходного файла в мегабайтах (МБ).

Если указан **циклический** параметр, то при достижении указанного максимального размера файла журнала самые старые записи удаляются по мере добавления новых. Если **циклический** параметр не указан, то при достижении файлом журнала указанного максимального размера новые данные не добавляются и командлет создает неустранимую ошибку.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Задает путь и имя выходного файла. Введите относительный или абсолютный путь на локальном компьютере или UNC-путь к удаленному компьютеру, например `\\Computer\Share\file.blg` . Этот параметр обязателен.

Формат файла определяется значением параметра **FileFormat** , а не расширением имени файла в пути.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet

Данные счетчика производительности можно передать в `Get-Counter` Этот командлет по конвейеру `Import-Counter` .

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

Генератор файлов журнала ожидает, что все входные объекты имеют один и тот же путь счетчика и объекты располагаются в порядке возрастания по времени.

Тип счетчика и путь первого входного объекта определяет свойства, записываемые в файл журнала. Если другие входные объекты не имеют значений для записанного свойства, поле свойства будет пустым. Если объекты имеют значения свойств, которые не были записаны, дополнительные значения свойств игнорируются.

Возможно, системный монитор не сможет считывать все журналы, создаваемые `Export-Counter` . Например, системный монитор требует, чтобы все объекты имели одинаковый путь, а все объекты были разделены одним и тем же интервалом времени.

`Import-Counter`Командлет не имеет параметра **ComputerName** . Однако если компьютер настроен для удаленной оболочки Windows PowerShell Windows PowerShell, можно использовать `Invoke-Command` командлет для выполнения `Import-Counter` команды на удаленном компьютере.

## Связанные ссылки

[Get-Counter](Get-Counter.md)

[Import-Counter](Import-Counter.md)
