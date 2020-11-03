---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "93230605"
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

## Описание

`ForEach-Object`Командлет выполняет операцию над каждым элементом в коллекции входных объектов. Входные объекты можно передать в командлет или указать с помощью параметра **InputObject** .

Начиная с Windows PowerShell 3,0 существует два разных способа создания `ForEach-Object` команды.

- **Блок скрипта** . Можно использовать блок скрипта, чтобы указать операцию. В блоке скрипта используйте `$_` переменную для представления текущего объекта. Блок скрипта — это значение параметра **Process** . Блок скрипта может содержать любой сценарий PowerShell.

  Например, следующая команда возвращает значение свойства **ProcessName** каждого процесса на компьютере.

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` поддерживает `begin` блоки, `process` и, `end` как описано в разделе [about_functions](about/about_functions.md#piping-objects-to-functions).

  > [!NOTE]
  > Блоки скрипта выполняются в области действия вызывающего объекта. Поэтому блоки имеют доступ к переменным в этой области и могут создавать новые переменные, которые сохраняются в этой области после завершения выполнения командлета.

- **Оператор Operation** . Можно также написать оператор операции, который гораздо более похож на естественный язык. С помощью инструкции операции можно указать значение свойства или вызвать метод. Инструкции операций появились в Windows PowerShell 3.0.

  Например, следующая команда также возвращает значение свойства **ProcessName** каждого процесса на компьютере.

  `Get-Process | ForEach-Object ProcessName`

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

Каждый подраздел **Network** представляет сопоставленный сетевой диск, который будет подключаться при входе в систему.
Запись **RemotePath** содержит UNC-путь подключенного диска. Например, если подключить диск E: к `\\Server\Share` , будет указан подраздел **e** , `HKCU:\Network` а в подразделе **e** — значение параметра реестра **RemotePath** `\\Server\Share` .

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

`ForEach-Object`Командлет очень полезен для получения значений свойств, так как он получает значение без изменения типа, в отличие от командлетов **Format** или `Select-Object` командлетов, которые изменяют тип значения свойства.

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

Вторая команда использует параметр **MemberName** , чтобы указать метод **Split** , и параметр **ArgumentName** для определения точки (".") в качестве разделителя разбиения.

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

В этом примере мы передаем два блока сценариев по положению. Все блоки скрипта привязываются к параметру **Process** . Однако они обрабатываются так, как будто они были переданы в параметры **Begin** , **Process** и **End** .

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
Если, например, выполняется `Get-Process | ForEach -MemberName *Name` несколько элементов с именем, содержащим имя строки, например свойства **processName** и **Name** , команда завершается ошибкой.

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

### System.Management.Automation.PSObject

В этот командлет можно передать по конвейеру любой объект.

## Выходные данные

### System.Management.Automation.PSObject

Этот командлет возвращает объекты, определяемые входными данными.

## Примечания

- `ForEach-Object`Командлет работает во многом подобно оператору **foreach** , за исключением того, что нельзя передавать входные данные оператору **foreach** . Дополнительные сведения об операторе **foreach** см. в разделе [about_Foreach](./About/about_Foreach.md).

- Начиная с PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями. Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)

## Связанные ссылки

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object;](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
