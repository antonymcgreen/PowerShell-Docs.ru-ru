---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8a79dcf9c2af7aed0c52c361467cab23f880a893
ms.sourcegitcommit: fb9bafd041e3615b9dc9fb77c9245581b705cd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2020
ms.locfileid: "99605531"
---
# ForEach-Object

## Краткий обзор
Выполняет операцию для каждого элемента в коллекции входных объектов.

## Синтаксис

### Скриптблокксет (по умолчанию)

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### пропертяндмесодсет

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### параллелпараметерсет

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Описание

`ForEach-Object`Командлет выполняет операцию над каждым элементом в коллекции входных объектов. Входные объекты можно передать в командлет или указать с помощью параметра **InputObject** .

Начиная с Windows PowerShell 3,0 существует два разных способа создания `ForEach-Object` команды.

- **Блок скрипта**. Можно использовать блок скрипта, чтобы указать операцию. В блоке скрипта используйте `$_` переменную для представления текущего объекта. Блок скрипта — это значение параметра **Process**. Блок скрипта может содержать любой сценарий PowerShell.

  Например, следующая команда возвращает значение свойства **ProcessName** каждого процесса на компьютере.

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` поддерживает `begin` блоки, `process` и, `end` как описано в разделе [about_functions](about/about_functions.md#piping-objects-to-functions).

  > [!NOTE]
  > Блоки скрипта выполняются в области действия вызывающего объекта. Поэтому блоки имеют доступ к переменным в этой области и могут создавать новые переменные, которые сохраняются в этой области после завершения выполнения командлета.

- **Оператор Operation**. Можно также написать оператор операции, который гораздо более похож на естественный язык. С помощью инструкции операции можно указать значение свойства или вызвать метод. Инструкции операций появились в Windows PowerShell 3.0.

  Например, следующая команда также возвращает значение свойства **ProcessName** каждого процесса на компьютере.

  `Get-Process | ForEach-Object ProcessName`

- **Параллельный выполняющийся блок сценария**. Начиная с PowerShell 7,0, доступен третий набор параметров, который выполняет каждый блок сценария параллельно. Параметр **ThrottleLimit** ограничивает количество параллельных скриптов, выполняемых за раз. Как и ранее, используйте `$_` переменную для представления текущего входного объекта в блоке script. Используйте `$using:` ключевое слово для передачи ссылок на переменные в выполняемый скрипт.

  В PowerShell 7 создается новое пространство выполнения для каждой итерации цикла, чтобы обеспечить максимальную изоляцию.
  Это может быть большой производительностью и достижением ресурсов, если работа, которую вы выполняете, невелика по сравнению с созданием новых пространств выполнения или большим количеством итераций, выполняющих значительную работу. По умолчанию для PowerShell 7,1 пространства выполнения из пула с пространством выполнением используются повторно. Размер пула пространства выполнения определяется параметром **ThrottleLimit** . Размер пула пространства выполнения по умолчанию равен 5. Вы по-прежнему можете создать новое пространство выполнения для каждой итерации с помощью параметра **усеневрунспаце** .

  По умолчанию параллельный скриптблоккс использует текущий рабочий каталог вызывающей стороны, который запустил параллельные задачи.

  Неустранимые ошибки записываются в поток ошибок командлета, как это происходит при параллельном выполнении скриптблоккс. Так как невозможно определить порядок выполнения параллельного сценария ScriptBlock, порядок, в котором ошибки отображаются в потоке ошибок, является случайным. Аналогичным образом сообщения, записанные в другие потоки данных, такие как предупреждения, подробные сведения или информация, записываются в потоки данных в неопределенном порядке.

  Завершающие ошибки, такие как исключения, завершают отдельный параллельный экземпляр скриптблоккс, в котором они происходят. Завершающая ошибка в одном скриптблоккс может не привести к завершению `Foreach-Object` командлета. Другие скриптблоккс, выполняющиеся параллельно, продолжают работать, пока не возникнет завершающей ошибки. Завершающая ошибка записывается в поток данных об ошибке как **ерроррекорд** с **фулликуалифиедеррорид** `PSTaskException` .
  Завершающие ошибки могут быть преобразованы в неустранимые ошибки с помощью блоков try/catch или ловушек PowerShell.

## Примеры

### Пример 1. деление целых чисел в массиве

Этот пример принимает массив из трех целых чисел и делит каждый из них на 1024.

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### Пример 2. Получение длины всех файлов в каталоге

В этом примере выполняется обработка файлов и каталогов в каталоге установки PowerShell `$PSHOME` .

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

Если объект не является каталогом, блок скрипта получает имя файла, делит значение его свойства **length** на 1024 и добавляет пробел (""), чтобы отделить его от следующей записи. Командлет использует свойство **PSISContainer** , чтобы определить, является ли объект каталогом.

### Пример 3. Эксплуатация с самыми последними системными событиями

Этот пример записывает 1000 последних событий из журнала системных событий в текстовый файл. Текущее время отображается до и после обработки событий.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

`Get-EventLog` Возвращает 1000 последних событий из журнала системных событий и сохраняет их в `$Events` переменной. `$Events` затем передается в `ForEach-Object` командлет. Параметр **Begin** используется для отображения текущей даты и времени. Затем параметр **Process** использует `Out-File` командлет для создания текстового файла с именем events.txt и сохраняет свойство Message каждого события в этом файле. Наконец, параметр **End** используется для отображения даты и времени после завершения обработки.

### Пример 4. изменение значения раздела реестра

Этот пример изменяет значение записи реестра **RemotePath** во всех подразделах `HKCU:\Network` раздела на верхний.

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

Этот формат можно использовать для изменения формы или содержимого раздела реестра.

Каждый подраздел в ключе **сети** представляет сопоставленный сетевой диск, который повторно подключается при входе. Запись **RemotePath** содержит UNC-путь подключенного диска. Например, если подключить диск E: к `\\Server\Share` , в параметре реестра  RemotePath будет создан подраздел e `HKCU:\Network` со значением  `\\Server\Share` .

Команда использует командлет, `Get-ItemProperty` чтобы получить все подразделы **сетевого** ключа и `Set-ItemProperty` командлета, чтобы изменить значение записи реестра **RemotePath** в каждом разделе.
В `Set-ItemProperty` команде путь является значением свойства **PSPath** раздела реестра. Это свойство объекта Microsoft .NET Framework, представляющего раздел реестра, а не запись реестра. Команда использует метод **ToUpper ()** значения **RemotePath** , который является строкой (REG_SZ).

Поскольку `Set-ItemProperty` изменяет свойство каждого ключа, `ForEach-Object` для доступа к свойству необходим командлет.

### Пример 5. Использование автоматической переменной $Null

В этом примере показан результат передачи `$Null` автоматической переменной в `ForEach-Object` командлет.

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

Так как PowerShell обрабатывает значение null как явный заполнитель, `ForEach-Object` командлет создает значение для `$Null` , точно так же, как и для других объектов, которые вы выполняете по конвейеру.

### Пример 6. Получение значений свойств

Этот пример возвращает значение свойства **path** для всех установленных модулей PowerShell с помощью параметра **MemberName** `ForEach-Object` командлета.

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

Вторая команда эквивалента первой. Он использует `Foreach` псевдоним `ForEach-Object` командлета и опускает имя параметра **MemberName** , которое является необязательным.

`ForEach-Object`Командлет полезен для получения значений свойств, так как он получает значение без изменения типа, в отличие от командлетов **Format** или `Select-Object` командлетов, которые изменяют тип значения свойства.

### Пример 7. разбиение имен модулей по именам компонентов

В этом примере показано три способа разбиения двух разделенных точками имен модулей в имена их компонентов.

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

Команда вызывает метод **Split** строк. Три команды используют различный синтаксис, но они эквивалентны и являются взаимозаменяемыми.

Первая команда использует традиционный синтаксис, который включает блок сценария и текущий оператор Object `$_` . Точечный синтаксис применяется для указания метода, а аргумент разделителя заключается в круглые скобки.

Вторая команда использует параметр **MemberName**, чтобы указать метод **Split**, и параметр **ArgumentName** для определения точки (".") в качестве разделителя разбиения.

Третья команда использует псевдоним **foreach** `ForEach-Object` командлета и опускает имена параметров **MemberName** и **ArgumentList** , которые являются необязательными.

### Пример 8. Использование ForEach-Object с двумя блоками сценариев

В этом примере мы передаем два блока сценариев по положению. Все блоки скрипта привязываются к параметру **Process** . Однако они обрабатываются так, как будто они были переданы в параметры **Begin** и **Process** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### Пример 9. Использование ForEach-Object с более чем двумя блоками сценариев

В этом примере мы передаем два блока сценариев по положению. Все блоки скрипта привязываются к параметру **Process** . Однако они обрабатываются так, как будто они были переданы в параметры **Begin**, **Process** и **End** .

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> Первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.

### Пример 10. Запуск нескольких блоков скрипта для каждого элемента конвейера

Как показано в предыдущем примере, несколько блоков скрипта, переданных с помощью параметра **Process** , сопоставляются с параметрами **Begin** и **End** . Чтобы избежать этого сопоставления, необходимо предоставить явные значения для параметров **Begin** и **End** .

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### Пример 11. Запуск сценария с задержкой в параллельных пакетах

В этом примере выполняется простой блок скрипта, который вычисляет строку и заждет одну секунду.

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

Значение параметра **ThrottleLimit** устанавливается равным 4, чтобы входные данные обрабатывались пакетами четырех.
`$using:`Ключевое слово используется для передачи `$Message` переменной в каждый параллельный блок скрипта.

### Пример 12. получение записей журнала в параллельном режиме

Этот пример извлекает записи журнала 50 000 из 5 системных журналов на локальном компьютере Windows.

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

С помощью параметра **Parallel** для каждого входного имени журнала указывается блок скрипта, который выполняется параллельно. Параметр **ThrottleLimit** гарантирует, что все пять блоков сценариев выполняются одновременно.

### Пример 13. Параллельное выполнение в качестве задания

В этом примере простой блок скрипта выполняется параллельно, создавая два фоновых задания за раз.

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

`$job`переменная получает объект задания, который собирает выходные данные и отслеживает состояние выполнения.
Объект задания передается в `Receive-Job` параметре **Wait** . И этот поток выводит данные в консоль, как если бы `ForEach-Object -Parallel` она выполнялась без **AsJob**.

### Пример 14. Использование ссылок на переменные потокобезопасные

В этом примере блоки сценариев вызываются параллельно для получения объектов процессов с уникальными именами.

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

Один экземпляр объекта **ConcurrentDictionary** передается в каждый блок сценария для получения объектов. Так как **ConcurrentDictionary** является потокобезопасным, его можно изменять с помощью каждого параллельного скрипта. Непотокобезопасный объект, такой как **System. Collections. Generic. Dictionary**, будет ненадежным для использования здесь.

> [!NOTE]
> Этот пример очень неэффективно использует **параллельный** параметр. Сценарий просто добавляет входной объект в объект параллельного словаря. Это тривиальное и не стоит тратить издержки на вызов каждого скрипта в отдельном потоке. `ForEach-Object`Нормальное выполнение без **параллельного** коммутатора является гораздо более эффективным и быстрым. Этот пример предназначен только для демонстрации использования потокобезопасных переменных.

### Пример 15. запись ошибок с параллельным выполнением

В этом примере выполняется параллельная запись в поток ошибок, в котором порядок записанных ошибок является случайным.

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### Пример 16. прекращение обработки ошибок в параллельном выполнении

В этом примере демонстрируется завершающая ошибка в одном параллельном выполняющемся блоке сценария.

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

`Output: 3` не записывается, так как параллельный блок сценария для этой итерации был завершен.

## Параметры

### -ArgumentList

Задает массив аргументов для вызова метода. Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Begin

Задает блок скрипта, который выполняется перед тем, как этот командлет обрабатывает все входные объекты. Этот блок сценария выполняется только один раз для всего конвейера. Дополнительные сведения о `begin` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -End

Задает блок скрипта, который запускается после того, как этот командлет обрабатывает все входные объекты. Этот блок сценария выполняется только один раз для всего конвейера. Дополнительные сведения о `end` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает входные объекты. `ForEach-Object` выполняет блок скрипта или инструкцию Operation для каждого входного объекта. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

При использовании параметра **InputObject** с параметром `ForEach-Object` , а не с результатами команды трубопроводов в `ForEach-Object` значение **InputObject** рассматривается как один объект. Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` .
Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `ForEach-Object` использовать для выполнения операций с коллекцией объектов для объектов, имеющих определенные значения в определенных свойствах, `ForEach-Object` в конвейере, как показано в примерах этого раздела.

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

### -MemberName

Указывает свойство, которое необходимо получить, или метод, который требуется вызвать.

Подстановочные знаки разрешены, но работают только в том случае, если результирующая строка разрешается в уникальное значение.
Например, если запустить `Get-Process | ForEach -MemberName *Name` , шаблон с подстановочными знаками будет соответствовать более чем одному члену, вызывающему сбой команды.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Process

Указывает операцию, которая выполняется с каждым входным объектом. Этот блок скрипта выполняется для каждого объекта в конвейере. Дополнительные сведения о `process` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).

Если параметру **Process** предоставлено несколько блоков скрипта, первый блок сценария всегда сопоставляется с `begin` блоком. При наличии только двух блоков сценариев второй блок сопоставляется с `process` блоком. При наличии трех или более блоков сценариев первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ремаинингскриптс

Задает все блоки скриптов, которые не выполняются параметром **Process** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parallel

Задает блок скрипта, используемый для параллельной обработки входных объектов. Введите блок скрипта, который описывает операцию.

Этот параметр появился в PowerShell 7,0.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает число параллельно обрабатываемых блоков скрипта. Входные объекты блокируются до тех пор, пока число блоков выполняющегося сценария не станет меньше **ThrottleLimit**. Значение по умолчанию — `5`.

Этот параметр появился в PowerShell 7,0.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

Указывает время ожидания (в секундах), в течение которого все входные данные будут обрабатываться параллельно. По истечении заданного времени ожидания все выполняющиеся сценарии останавливаются. И все остальные входные объекты для обработки игнорируются. Значение по умолчанию `0` отключает время ожидания и `ForEach-Object -Parallel` может выполняться бессрочно. Команда <kbd>CTRL</kbd> + <kbd>C</kbd> в командной строке останавливает выполнение `ForEach-Object -Parallel` команды. Этот параметр нельзя использовать вместе с параметром **AsJob** .

Этот параметр появился в PowerShell 7,0.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Усеневрунспаце

Приводит к тому, что параллельный вызов создает новое пространство выполнения для каждой итерации цикла, а не повторно использует пространства выполнения из пула.

Этот параметр появился в PowerShell 7,1

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Вызывает выполнение параллельного вызова в качестве задания PowerShell. Вместо выходных данных выполняемых блоков сценария возвращается один объект задания. Объект задания содержит дочерние задания для каждого выполняемого блока параллельного скрипта. Объект задания может использоваться всеми командлетами задания PowerShell для отслеживания состояния выполнения и получения данных.

Этот параметр появился в PowerShell 7,0.

```yaml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
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
Type: SwitchParameter
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
Type: SwitchParameter
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

### System.Management.Automation.PSObject

В этот командлет можно передать по конвейеру любой объект.

## Выходные данные

### System.Management.Automation.PSObject

Этот командлет возвращает объекты, определяемые входными данными.

## Примечания

- `ForEach-Object`Командлет работает во многом подобно оператору **foreach** , за исключением того, что нельзя передавать входные данные оператору **foreach** . Дополнительные сведения об операторе **foreach** см. в разделе [about_Foreach](./About/about_Foreach.md).

- Начиная с PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями. Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)

- `ForEach-Object -Parallel`Набор параметров использует внутренний API PowerShell для выполнения каждого блока скрипта. Это значительно больше издержек, чем `ForEach-Object` обычно выполняется с последовательной обработкой. Важно использовать **Parallel** , где затраты на параллельное выполнение выполняются немало по сравнению с работой блока сценария. Пример:

  - Ресурсоемкие сценарии на компьютерах с несколькими ядрами
  - Сценарии, которые тратят время на ожидание результатов или выполнение файловых операций

  Использование параметра **Parallel** может привести к тому, что скрипты выполняются намного медленнее, чем обычные. Особенно если параллельные сценарии являются тривиальными. Поэкспериментируйте с **Parallel** , чтобы узнать, где это может быть полезно.

  > [!IMPORTANT]
  > `ForEach-Object -Parallel`Набор параметров запускает блоки сценариев параллельно в отдельных потоках процесса. `$using:`Ключевое слово позволяет передавать ссылки на переменные из потока вызова командлета в каждый выполняемый поток блока сценария. Так как блоки скрипта выполняются в разных потоках, объектные переменные, передаваемые по ссылке, должны использоваться безопасно. Как правило, можно легко считывать объекты, на которые имеются ссылки, которые не изменяются. Но если состояние объекта изменяется, необходимо использовать потокобезопасные объекты, такие как .NET **System. Collection. Параллельные** типы (см. Пример 11).

## Связанные ссылки

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object;](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
