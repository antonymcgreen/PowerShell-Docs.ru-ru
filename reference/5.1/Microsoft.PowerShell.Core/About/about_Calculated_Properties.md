---
description: PowerShell предоставляет возможность динамического добавления новых свойств и изменения форматирования выходных данных объектов в конвейере.
Locale: en-US
ms.date: 10/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: 4dd7912c7e1a976e20f92093a47355f3a3291093
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232166"
---
# <a name="about-calculated-properties"></a>О вычисляемых свойствах

## <a name="short-description"></a>Краткое описание

PowerShell предоставляет возможность динамического добавления новых свойств и изменения форматирования выходных данных объектов в конвейере.

## <a name="long-description"></a>Полное описание

Несколько командлетов PowerShell преобразуют, объединяют или обрабатывают входные объекты в выходных объектах с помощью параметров, которые позволяют добавлять новые свойства в эти выходные объекты. Эти параметры можно использовать для создания новых вычисляемых свойств для выходных объектов на основе значений входных объектов.
Вычисляемое свойство определяется [Hashtable](about_hash_tables.md) , содержащим пары "ключ-значение", которые указывают имя нового свойства, выражение для вычисления значения и необязательные сведения о форматировании.

## <a name="supported-cmdlets"></a>Поддерживаемые командлеты

Следующие командлеты поддерживают значения вычисляемых свойств для параметра **Property** . `Format-*`Командлеты также поддерживают вычисленные значения для параметра **GroupBy** .

В следующем списке перечислены командлеты, которые поддерживают вычисляемые свойства и пары "ключ-значение", поддерживаемые каждым командлетом.

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - `name`/`label` — необязательно (добавляется в PowerShell 6. x)
  - `expression`
  - `width` — необязательно
  - `alignment` — необязательно

- `Format-Custom`
  - `expression`
  - `depth` — необязательно

- `Format-List`
  - `name`/`label` — необязательно
  - `expression`
  - `formatstring` — необязательно

  Этот же набор пар "ключ-значение" также применяется к вычисляемым значениям свойств, передаваемым параметру **GroupBy** для всех `Format-*` командлетов.

- `Format-Table`
  - `name`/`label` — необязательно
  - `expression`
  - `formatstring` — необязательно
  - `width` — необязательно
  - `alignment` — необязательно

- `Format-Wide`
  - `expression`
  - `formatstring` — необязательно

- `Group-Object`
  - `expression`

- `Measure-Object`
  - Поддерживает только блок скрипта для выражения, а не хэш-таблицы.
  - Не поддерживается в PowerShell 5,1 и более ранних версий.

- `Select-Object`
  - `name`/`label` — необязательно
  - `expression`

- `Sort-Object`
  - `expression`
  - `ascending`/`descending` — необязательно

> [!NOTE]
> Значением параметра `expression` может быть блок скрипта, а не хэш-таблица. Дополнительные сведения см. в разделе " [Примечания](#notes) ".

## <a name="hashtable-key-definitions"></a>Определения ключей хэш-таблицы

- `name`/`label` — Указывает имя создаваемого свойства. Вы можете использовать `name` или его псевдоним, который является `label` взаимозаменяемым.
- `expression` — Блок скрипта, используемый для вычисления значения нового свойства.
- `alignment` — Используется командлетами, которые создают табличные выходные данные для определения способа отображения значений в столбце. Значение должно быть `'left'` , `'center'` или `'right'` .
- `formatstring` — Задает строку формата, определяющую формат значения для вывода. Дополнительные сведения о строках формата см. [в разделе Типы форматов в .NET](/dotnet/standard/base-types/formatting-types).
- `width` — Задает столбец максимальной ширины в таблице при отображении значения. Значение должно быть больше `0` .
- `depth` — Параметр **Depth** параметра `Format-Custom` указывает глубину расширения для всех свойств. `depth`Ключ позволяет указать глубину расширения для каждого свойства.
- `ascending` / `descending` — Позволяет указать порядок сортировки для одного или нескольких свойств. Это логические значения.

Ключи Hashtable не должны быть написаны, пока указанный префикс имени не является неоднозначным. Например, `n` можно использовать вместо `Name` и `e` может использоваться вместо `Expression` .

## <a name="examples"></a>Примеры

### <a name="compare-object"></a>Compare-Object

С помощью вычисляемых свойств можно управлять способом сравнения свойств входных объектов. В этом примере вместо непосредственного сравнения значений значения сравниваются с результатом арифметической операции (модуль из 2).

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a>ConvertTo-Html

`ConvertTo-Html` может преобразовать коллекцию объектов в таблицу HTML.
Вычисляемые свойства позволяют управлять способом представления таблицы.

```powershell
Get-Alias |
  ConvertTo-Html Name,
                 Definition,
                 @{
                    expr={$_.Parameters.Keys.Count}
                    align='center'
                 } |
    Out-File .\aliases.htm -Force
```

В этом примере создается таблица HTML, содержащая список псевдонимов PowerShell и числовые параметры для каждой команды с псевдонимом. Значения столбца **параметеркаунт** центрируются по центру.

### <a name="format-custom"></a>Format-Custom

`Format-Custom` предоставляет пользовательское представление объекта в формате, аналогичном определению класса. Более сложные объекты могут содержать элементы, которые глубоко вложены в сложные типы. Параметр **Depth** параметра `Format-Custom` указывает глубину расширения для всех свойств. `depth`Ключ позволяет указать глубину расширения для каждого свойства.

В этом примере `depth` ключ упрощает пользовательский вывод для `Get-Date` командлета. `Get-Date` Возвращает объект **DateTime** . Свойство **Date** этого объекта также является объектом **DateTime** , поэтому объект является вложенным.

```powershell
Get-Date | Format-Custom @{expr={$_.Date};depth=1},TimeOfDay
```

```Output
class DateTime
{
  $_.Date =
    class DateTime
    {
      Date = 8/7/2020 12:00:00 AM
      Day = 7
      DayOfWeek = Friday
      DayOfYear = 220
      Hour = 0
      Kind = Local
      Millisecond = 0
      Minute = 0
      Month = 8
      Second = 0
      Ticks = 637323552000000000
      TimeOfDay = 00:00:00
      Year = 2020
      DateTime = Friday, August 07, 2020 12:00:00 AM
    }
  TimeOfDay =
    class TimeSpan
    {
      Ticks = 435031592302
      Days = 0
      Hours = 12
      Milliseconds = 159
      Minutes = 5
      Seconds = 3
      TotalDays = 0.503508787386574
      TotalHours = 12.0842108972778
      TotalMilliseconds = 43503159.2302
      TotalMinutes = 725.052653836667
      TotalSeconds = 43503.1592302
    }
}
```

### <a name="format-list"></a>Format-List

В этом примере мы используем вычисляемые свойства для изменения имени и формата выходных данных из `Get-ChildItem` .

```powershell
Get-ChildItem *.json -File |
  Format-List Fullname,
              @{
                 name='Modified'
                 expression={$_.LastWriteTime}
                 formatstring='O'
              },
              @{
                 name='Size'
                 expression={$_.Length/1KB}
                 formatstring='N2'
              }
```

```Output
FullName : C:\Git\PS-Docs\PowerShell-Docs\.markdownlint.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.40

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.publish.config.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.25

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.redirection.json
Modified : 2020-07-27T13:05:24.3887629-07:00
Size     : 324.60
```

### <a name="format-table"></a>Format-Table

В этом примере вычисляемое свойство добавляет свойство **Type** , используемое для классификации файлов по типу содержимого.

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Format-Table Name, Length -GroupBy @{
      name='Type'
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
   Type: Metacontent

Name              Length
----              ------
ThirdPartyNotices   1229
LICENSE-CODE        1106
LICENSE            19047

   Type: Configuration

Name                                Length
----                                ------
.editorconfig                          183
.gitattributes                         419
.gitignore                             228
.markdownlint.json                    2456
.openpublishing.publish.config.json   2306
.openpublishing.redirection.json    332394
.localization-config                   232

   Type: Content

Name            Length
----            ------
README.md         3355
CONTRIBUTING.md    247

   Type: Automation

Name                      Length
----                      ------
.openpublishing.build.ps1    796
build.ps1                   7495
ci.yml                       645
ci-steps.yml                2035
daily.yml                   1271
```

### <a name="format-wide"></a>Format-Wide

`Format-Wide`Командлет позволяет отображать значение одного свойства для объектов в коллекции в виде списка с несколькими столбцами.

В этом примере мы хотим увидеть имя файла и размер (в килобайтах) в качестве широкого списка. Поскольку не `Format-Wide` отображает более одного свойства, мы используем вычисляемое свойство, чтобы объединить значения двух свойств в одно значение.

```powershell
Get-ChildItem -File |
  Format-Wide -Property @{e={'{0} ({1:N2}kb)' -f $_.name,($_.length/1kb)}}
```

```Output
.editorconfig (0.18kb)                          .gitattributes (0.41kb)
.gitignore (0.22kb)                             .localization-config (0.23kb)
.markdownlint.json (2.40kb)                     .openpublishing.build.ps1 (0.78kb)
.openpublishing.publish.config.json (2.25kb)    .openpublishing.redirection.json (324.60kb)
build.ps1 (7.32kb)                              ci.yml (0.63kb)
ci-steps.yml (1.99kb)                           CONTRIBUTING.md (0.24kb)
daily.yml (1.24kb)                              LICENSE (18.60kb)
LICENSE-CODE (1.08kb)                           README.md (3.28kb)
ThirdPartyNotices (1.20kb)
```

### <a name="group-object"></a>Group-Object

`Group-Object`Командлет отображает объекты в группах на основе значения указанного свойства. В этом примере вычисляемое свойство подсчитывает количество файлов каждого типа содержимого.

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Group-Object -NoElement -Property @{
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
Count Name
----- ----
    5 Automation
    7 Configuration
    2 Content
    3 Metacontent
```

### <a name="select-object"></a>Select-Object;

Вычисляемые свойства можно использовать для добавления дополнительных элементов в выходные данные объектов с помощью `Select-Object` командлета. В этом примере мы перечислим псевдонимы PowerShell, которые начинаются с буквы `C` . Используя `Select-Object` , мы выводим псевдоним, командлет, с которым он сопоставлен, и количество параметров, определенных для командлета. Используя вычисляемое свойство, можно создать свойство **параметеркаунт** .

```powershell
$aliases = Get-Alias c* |
  Select-Object Name,
                Definition,
                @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                }
$aliases | Get-Member
$aliases
```

```Output
   TypeName: Selected.System.Management.Automation.AliasInfo

Name           MemberType   Definition
----           ----------   ----------
Equals         Method       bool Equals(System.Object obj)
GetHashCode    Method       int GetHashCode()
GetType        Method       type GetType()
ToString       Method       string ToString()
Definition     NoteProperty string Definition=Get-Content
Name           NoteProperty string Name=cat
ParameterCount NoteProperty System.Int32 ParameterCount=21

Name    Definition         ParameterCount
----    ----------         --------------
cat     Get-Content                    21
cd      Set-Location                   15
cdd     Push-MyLocation                 1
chdir   Set-Location                   15
clc     Clear-Content                  20
clear   Clear-Host                      0
clhy    Clear-History                  17
cli     Clear-Item                     20
clp     Clear-ItemProperty             22
cls     Clear-Host                      0
clv     Clear-Variable                 19
cnsn    Connect-PSSession              29
compare Compare-Object                 20
copy    Copy-Item                      24
cp      Copy-Item                      24
cpi     Copy-Item                      24
cpp     Copy-ItemProperty              23
cvpa    Convert-Path                   13
```

### <a name="sort-object"></a>Sort-Object

С помощью вычисляемых свойств можно сортировать данные по разным заказам для каждого свойства. В этом примере данные из CSV-файла сортируются в порядке возрастания по **дате**. Но внутри каждой даты сортируются строки в убывающем порядке по **унитссолд**.

```powershell
Import-Csv C:\temp\sales-data.csv |
  Sort-Object Date, @{expr={$_.UnitsSold}; desc=$true}, Salesperson  |
    Select-Object Date, Salesperson, UnitsSold
```

```Output
Date       Salesperson UnitsSold
----       ----------- ---------
2020-08-01 Sally       3
2020-08-01 Anne        2
2020-08-01 Fred        1
2020-08-02 Anne        6
2020-08-02 Fred        2
2020-08-02 Sally       0
2020-08-03 Anne        5
2020-08-03 Sally       3
2020-08-03 Fred        1
2020-08-04 Anne        2
2020-08-04 Fred        2
2020-08-04 Sally       2
```

## <a name="notes"></a>Примечания

- Блок скрипта выражения можно указать _непосредственно_ в качестве аргумента вместо того, чтобы указывать его в качестве `Expression` записи в хэш-таблице. Пример:

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  Этот пример удобен для командлетов, которым не требуется (или не поддерживается) именование свойства с помощью `Name` ключа, например `Sort-Object` , `Group-Object` и `Measure-Object` .

  Для командлетов, которые поддерживают именование свойства, блок скрипта преобразуется в строку и используется в качестве имени свойства в выходных данных.

- `Expression` блоки скриптов выполняются в _дочерних_ областях, то есть переменные вызывающего объекта нельзя изменять напрямую.

- Логика конвейера применяется к выходным данным из `Expression` блоков скриптов. Это означает, что вывод массива с одним элементом приводит к развернутому массиву.

- Для большинства командлетов ошибки внутри блоков скриптов выражений не учитываются.
  Для `Sort-Object` , завершающие выполнение инструкций и ошибки, заканчивающиеся скриптом, являются _выходными_ , но не завершают инструкцию.

## <a name="see-also"></a>См. также:

[about_Hash_Tables](about_hash_tables.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[Format-Custom](xref:Microsoft.PowerShell.Utility.Format-Custom)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Format-Wide](xref:Microsoft.PowerShell.Utility.Format-Wide)

[Group-Object](xref:Microsoft.PowerShell.Utility.Group-Object)

[Measure-Object;](xref:Microsoft.PowerShell.Utility.Measure-Object)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Sort-Object](xref:Microsoft.PowerShell.Utility.Sort-Object)

[Форматирование типов в .NET](/dotnet/standard/base-types/formatting-types)
