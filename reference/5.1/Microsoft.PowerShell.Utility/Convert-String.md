---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227738"
---
# Convert-String

## Краткий обзор
Форматирует строку в соответствии с примерами.

## SYNTAX

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Convert-String** форматирует строку в соответствии с форматом примеров.

## Примеры

### Пример 1. преобразование формата строки

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

Первая команда создает массив, содержащий имя и фамилию.

Вторая команда форматирует имена в соответствии с примером.
Сначала помещается фамилия в выходные данные, а затем — начальное.

### Пример 2. Упрощение формата строки

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

Первая команда создает массив, содержащий имя, отчество и фамилию.
Обратите внимание, что у последней записи нет отчества.

Вторая команда форматирует имена в соответствии с примером.
Сначала в выходных данных помещается фамилия, за которой следует имя.
Все средние имена удалены; запись без промежуточного имени обрабатывается правильно.

### Пример 3. управление выходом при несовпадении строк

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

Первая команда создает массив, содержащий имя, отчество и фамилию.
Обратите внимание, что у последней записи нет отчества.

Вторая команда форматирует имена в соответствии с примером.
Сначала помещается **отчество** в выходных данных, а затем — имя.
Последняя запись в **$composers** пропускается, так как она не соответствует образцу шаблона: имя не имеет отчества.

### Пример 4. предупреждение с помощью непривлекательных пространств

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

Первая команда создает массив первых и последних имен.
Обратите внимание, что второй и четвертый элементы содержат дополнительное место в конце, после последнего имени.

Вторая команда преобразует все строки, которые соответствуют образцу шаблона: _слово, пробел, слово и конечная конечная область_ , все это перед знаком равенства.
Кроме того, обратите внимание на начальное пространство в выходных данных.

### Пример 5. Форматирование сведений о процессе с помощью нескольких шаблонов

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

В примерах **$ExamplePatterns** определяются различные ожидаемые закономерности в данных.

Первый шаблон, `@{before='"Hello","World"'; after='World: Hello'}` , считывается следующим образом: _Ожидание строк, в которых слово заключено в двойные кавычки, затем запятая,_ 
 _а вторая и последняя слова, заключенные в кавычки;_ 
 без _пробелов в строке. На выходе: сначала поместите второе слово,_ 
 _без кавычек, затем один пробел, а затем первое слово без кавычек._

Второй шаблон, `@{before='"Hello","1"'; after='1: Hello'}` , считывается следующим образом: _Ожидание строк, в которых слово заключено в двойные кавычки, затем запятая,_ 
 _а затем число, заключенное в кавычки._ 
 без _пробелов в строке. На выходе: сначала поместите номер_ 
 _без кавычек, а затем — один пробел, а затем слово без кавычек._

Третий шаблон, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , выполняет чтение следующим образом: _Ожидание строк, в которых два слова с дефисом заключены в_ 
 _двойные кавычки, затем запятая, а затем число, заключенное в кавычки._ 
 без _пробелов между запятой и третьей двойной кавычкой._ 
 _На выходе: сначала поместите номер без кавычек, а затем один пробел._ 
 _а затем продефисировать слова без кавычек._

Четвертый и последний, шаблон, `@{before='"hello world","333"'; after='333: hello world'}` , выполняет чтение следующим образом: _ожидайте строки, в которых два слова с пробелами заключены в_ 
 _двойные кавычки, затем запятую, а затем число, заключенное в кавычки._ 
 без _пробелов между запятой и третьей двойной кавычкой._ 
 _На выходе: сначала поместите номер без кавычек, а затем один пробел._ 
 _а затем слова с пробелами между, без кавычек._

Первая команда получает все процессы с помощью командлета Get-Process.
Команда передает их в командлет Select-Object, который выбирает имя процесса и идентификатор процесса. В конце конвейера команда преобразует выходные данные в значения с разделителями запятыми без сведений о типе с помощью командлета ConvertTo-Csv.
Команда сохраняет результаты в переменной **$Processes** .
**$Processes** теперь содержит имена процессов и PID.

Во второй команде указывается пример переменной, которая изменяет порядок входных элементов.
Команда преобразует каждую строку в **$Processes** .

>**Примечание** . Четвертый шаблон неявно говорит о том, что сопоставлены два или более слов, разделенных пробелами.
>
>Без четвертого шаблона сопоставляется только первое слово строки, заключенной в двойные кавычки.

## PARAMETERS

### -Пример

Задает список примеров для целевого формата.
Укажите пары, разделенные знаком равенства (=), с исходным шаблоном слева и целевым шаблоном справа, как показано в следующих примерах:

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

>**Примечание** . Во втором примере используется список шаблонов

Кроме того, можно указать список хэш-таблиц, содержащих свойства **Before** и **After** .

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

>**Внимание!** Старайтесь не использовать пробелы вокруг знака равенства, так как они обрабатываются как часть шаблона.

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает строку для форматирования.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Строка

В этот командлет можно передать строки.

## Выходные данные

### Строка

Этот командлет возвращает строку.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[ConvertFrom-String](ConvertFrom-String.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Out-String](Out-String.md)

[Select-Object](Select-Object.md)
