---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: aa97115217be5363e2f81e87c4d6ce7e03c453a4
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230302"
---
# Group-Object

## Краткий обзор
Группирует объекты, в которых указанные свойства имеют одно и то же значение.

## SYNTAX

### Хеш

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

`Group-Object`Командлет отображает объекты в группах на основе значения указанного свойства.
`Group-Object` Возвращает таблицу с одной строкой для каждого значения свойства и столбец, в котором отображается количество элементов с этим значением.

Если указано более одного свойства, `Group-Object` сначала сгруппируйте их по значениям первого свойства, а затем в каждой группе свойств она группируется по значению свойства Next.

Начиная с PowerShell 7, `Group-Object` может сочетать параметры **CaseSensitive** и **AsHashtable** для создания хэш-таблицы с учетом регистра. В ключах хэш-таблицы используются сравнения с учетом регистра и вывод объекта **System. Collections. Hashtable** .

## Примеры

### Пример 1. Группировка файлов по расширению

Этот пример рекурсивно получает файлы в `$PSHOME` и группирует их по расширению имени файла. Выходные данные отправляются в `Sort-Object` командлет, который сортирует их по файлам счетчика, найденным для данного расширения. Пустое **имя** представляет каталоги.

В этом примере используется параметр **элемента** , чтобы опустить члены группы.

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### Пример 2. Группирование целых чисел с помощью вероятность и даже

В этом примере показано, как использовать блоки script в качестве значения параметра **Property** . Эта команда отображает целые числа от 1 до 20, сгруппированные по значениям вероятность и даже.

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### Пример 3. Группировка событий журнала событий по EntryType

В этом примере отображаются 1 000 последних записей в журнале системных событий, сгруппированных по **EntryType** .

В выходных данных столбец **Count** представляет количество записей в каждой группе. Столбец **Name** представляет значения **EventType** , определяющие группу. Столбец **Group** представляет объекты в каждой группе.

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### Пример 4. Группирование процессов по классу приоритета

В этом примере демонстрируется действие параметра **элемента** . Эти команды группируют процессы на компьютере по классу приоритета.

Первая команда использует `Get-Process` командлет для получения процессов на компьютере и отправляет объекты по конвейеру. `Group-Object`Группирует объекты по значению свойства **PriorityClass значение** процесса.

Во втором примере используется параметр **элемента** , чтобы исключить члены группы из выходных данных. Результатом является таблица с только значением свойства **Count** и **Name** .

Результаты отображаются в следующем примере вывода.

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### Пример 5. Группирование процессов по имени

В следующем примере используется `Group-Object` для группирования нескольких экземпляров процессов, запущенных на локальном компьютере. `Where-Object` Отображает процессы с более чем одним экземпляром.

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### Пример 6. Группирование объектов в хэш-таблице

В этом примере используются параметры **AsHashTable** и **AsString** для возврата групп в хэш-таблице в виде коллекции пар "ключ-значение".

В полученной хэш-таблице каждое значение свойства является ключом, а элементы группы — значениями.
Поскольку каждый ключ является свойством объекта хэш-таблицы, для отображения значений можно использовать точечную нотацию.

Первая команда получает `Get` `Set` командлеты и в сеансе, группирует их по команде, возвращает группы в виде хэш-таблицы и сохраняет хэш-таблицу в `$A` переменной.

Вторая команда отображает хэш-таблицу в `$A` . Существует две пары «ключ-значение»: одна для `Get` командлетов и одна для `Set` командлетов.

Третья команда использует точечную нотацию `$A.Get` для вывода значений ключа **Get** в `$A` . Значения — **CmdletInfo** Object. Параметр **AsString** не преобразует объекты в группах в строки.

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                                Version    Source
-----------     ----                                -------    ------
Cmdlet          Get-Acl                             7.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                           7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation        2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                 2.0.0.0    AppLocker
...
```

### Пример 7. Создание хэш-таблицы с учетом регистра

В этом примере объединяются параметры **CaseSensitive** и **AsHashTable** для создания хэш-таблицы с учетом регистра. Файлы в примере имеют расширения `.txt` и `.TXT` .

```powershell
$hash = Get-ChildItem -Path C:\Files | Group-Object -Property Extension -CaseSensitive -AsHashTable
$hash
```

```Output
Name           Value
----           -----
.TXT           {C:\Files\File7.TXT, C:\Files\File8.TXT, C:\Files\File9.TXT}
.txt           {C:\Files\file1.txt, C:\Files\file2.txt, C:\Files\file3.txt}
```

`$hash`Переменная хранит объект **System. Collections. Hashtable** . `Get-ChildItem` Получает имена файлов из `C:\Files` каталога и отправляет объекты **System. IO. FileInfo** вниз по конвейеру. `Group-Object`Группирует объекты с помощью **расширения** значения **Свойства** . Параметры **CaseSensitive** и **AsHashTable** создают хэш-таблицу, а ключи группируются с использованием ключей с учетом регистра `.txt` и `.TXT` .

## PARAMETERS

### -AsHashTable

Указывает, что этот командлет возвращает группу в виде хэш-таблицы. Ключами хэш-таблицы являются значения свойств, по которым группируются объекты. Значениями хэш-таблицы являются объекты, имеющие это значение свойства.

Сам по себе параметр **AsHashTable** возвращает каждую хэш-таблицу, в которой каждый ключ является экземпляром сгруппированного объекта. При использовании с параметром **AsString** ключи в хэш-таблице являются строками.

Начиная с PowerShell 7, чтобы создавать хэш-таблицы с учетом регистра, в команде следует включать **CaseSensitive** и **AsHashtable** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Указывает, что этот командлет преобразует ключи хэш-таблицы в строки. По умолчанию ключами хэш-таблицы являются экземпляры группируемых объектов. Этот параметр допустим только при использовании с параметром **AsHashTable** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaseSensitive

Указывает, что этот командлет делает группирование с учетом регистра. Без этого параметра в группу будут включаться значения свойств в разных регистрах.

Начиная с PowerShell 7, чтобы создавать хэш-таблицы с учетом регистра, в команде следует включать **CaseSensitive** и **AsHashtable** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Задает язык и региональные параметры. которые будут использоваться при сравнении строк.

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

### -InputObject

Задает объекты, которые будут включаться в группу. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

При использовании параметра **InputObject** для отправки коллекции объектов в `Group-Object` `Group-Object` получается один объект, представляющий коллекцию. В результате командлет создает одну группу, в которую входит этот объект.

Чтобы сгруппировать объекты в коллекции, передаем объекты в `Group-Object` .

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

### -NoElement

Указывает, что этот командлет опускает члены группы из результатов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Определяет свойства для группирования. Объекты объединяются в группы на основании значения заданного свойства.

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Выражение — `<string>` или `<script block>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в `Group-Object` .

## Выходные данные

### Microsoft.PowerShell.Commands.GroupInfo или System.Collections.Hashtable

При использовании параметра **AsHashTable** `Group-Object` возвращает объект **Hashtable** .
В противном случае возвращается объект **GroupInfo** .

## ПРИМЕЧАНИЯ

Для группирования объектов можно использовать параметр **GroupBy** командлетов форматирования, например `Format-Table` и `Format-List` . В отличие от `Group-Object` , при котором создается одна таблица со строкой для каждого значения свойства, параметры **GroupBy** создают таблицу для каждого значения свойства со строкой для каждого элемента, имеющего значение свойства.

`Group-Object` не требует, чтобы сгруппированные объекты совпадали с типом Microsoft .NET Core. При группировании объектов различных типов .NET Core `Group-Object` использует следующие правила.

- Одинаковые имена и типы свойств.

  Если у объектов есть свойство с указанным именем, а значения свойств имеют один и тот же тип .NET Core, то значения свойств группируются с использованием тех же правил, которые использовались для объектов того же типа.

- Одинаковые имена свойств, различные типы.

  Если у объектов есть свойство с указанным именем, но значения свойств имеют разные типы .NET Core в разных объектах, `Group-Object` использует тип .NET Core первого экземпляра свойства в качестве типа .NET Core для этой группы свойств. Если у объекта имеется свойство другого типа, значение этого свойства преобразуется в тип данной группы. Если преобразование типа завершается неудачей, объект не включается в группу.

- Отсутствующие свойства.

  Объекты, у которых нет указанного свойства, не могут быть сгруппированы. Объекты, которые не группируются, отображаются в конечном выводе объекта **GroupInfo** в группе с именем `AutomationNull.Value` .

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Measure-Object;](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
