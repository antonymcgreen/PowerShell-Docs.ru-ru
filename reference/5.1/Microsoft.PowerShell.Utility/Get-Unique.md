---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: 584e36dbb6db251906dfbf4f700ced78f1cb6830
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227621"
---
# Get-Unique

## Краткий обзор
Возвращает уникальные элементы из сортированного списка.

## SYNTAX

### AsString (по умолчанию)

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### уникуебитипе

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## DESCRIPTION

`Get-Unique`Командлет сравнивает каждый элемент отсортированного списка со следующим элементом, удаляет дубликаты и возвращает только один экземпляр каждого элемента. Чтобы командлет работал правильно, список должен быть отсортирован.

`Get-Unique` учитывает регистр. Поэтому строки, которые отличаются только регистром символов, считаются уникальными.

## Примеры

### Пример 1. получение уникальных слов в текстовом файле

Эти команды определяют число уникальных слов в текстовом файле.

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

Первая команда возвращает содержимое файла File.txt. Она преобразует каждую строку текста в строчные буквы, а затем выделяет каждое слово, отделенное пробелом (" "), в отдельную строку. Затем он сортирует полученный список в алфавитном порядке (по умолчанию) и использует `Get-Unique` командлет для удаления повторяющихся слов. Результаты хранятся в `$A` переменной.

Вторая команда использует свойство **Count** коллекции строк в `$A` для определения количества элементов в `$A` .

### Пример 2. получение уникальных целых чисел в массиве

Эта команда находит уникальные члены во множестве целых чисел.

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

Первая команда принимает массив целых чисел, введенный в командной строке, передает их в командлет, который `Sort-Object` должен быть отсортирован, а затем передает их в `Get-Unique` , что устраняет дублирование записей.

### Пример 3. получение уникальных типов объектов в каталоге

Эта команда использует `Get-ChildItem` командлет для получения содержимого локального каталога, включающего файлы и каталоги.

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

Оператор конвейера (|) отправляет результаты в `Sort-Object` командлет. `$_.GetType()`Оператор применяет метод **GetType** к каждому файлу или каталогу. Затем `Sort-Object` сортирует элементы по типу. Другой конвейерный оператор отправляет результаты в `Get-Unique` . Параметр **OnType** направляет `Get-Unique` возврат только одного объекта каждого типа.

### Пример 4. получение уникальных процессов

Эта команда возвращает имена запущенных на компьютере процессов без повторяющихся имен.

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

`Get-Process`Команда получает все процессы на компьютере. Оператор конвейера (|) передает результат в `Sort-Object` , который по умолчанию сортирует процессы в алфавитном порядке по ProcessName. Результаты передаются в `Select-Object` командлет, который выбирает только значения свойства ProcessName каждого объекта. Затем результаты передаются в, чтобы `Get-Unique` исключить дубликаты.

Параметр **AsString** указывает `Get-Unique` , что значения **processName** должны обрабатываться как строки.
Без этого параметра `Get-Unique` обрабатывает значения **processName** как объекты и возвращает только один экземпляр объекта, то есть имя первого процесса в списке.

## PARAMETERS

### -AsString

Указывает, что этот командлет использует данные в качестве строки. Без этого параметра данные обрабатываются как объект, поэтому при отправке коллекции объектов одного типа в `Get-Unique` , например коллекции файлов, возвращается только один (первый). С помощью этого параметра можно находить уникальные значения свойств объектов, например имена файлов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает входные данные для `Get-Unique` . Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

Этот командлет рассматривает входные данные, отправленные с помощью **InputObject** , в качестве коллекции. Он не перечисляет отдельные элементы в коллекции. Поскольку коллекция является одним элементом, входные данные, отправленные с помощью **InputObject** , всегда возвращаются без изменений.

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

### -OnType

Указывает, что этот командлет возвращает только один объект каждого типа.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Можно передать объект любого типа в `Get-Unique` .

## Выходные данные

### System.Management.Automation.PSObject

Тип `Get-Unique` возвращаемого объекта определяется входными данными.

## ПРИМЕЧАНИЯ

Также можно ссылаться `Get-Unique` по встроенному псевдониму `gu` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Чтобы отсортировать список, используйте командлет Sort-Object. **Unique** `Sort-Object` Для поиска уникальных элементов в списке можно также использовать уникальный параметр.

## Связанные ссылки

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)
