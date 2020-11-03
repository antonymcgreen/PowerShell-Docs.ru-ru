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
# <a name="about-calculated-properties"></a><span data-ttu-id="62435-103">О вычисляемых свойствах</span><span class="sxs-lookup"><span data-stu-id="62435-103">About calculated properties</span></span>

## <a name="short-description"></a><span data-ttu-id="62435-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="62435-104">Short Description</span></span>

<span data-ttu-id="62435-105">PowerShell предоставляет возможность динамического добавления новых свойств и изменения форматирования выходных данных объектов в конвейере.</span><span class="sxs-lookup"><span data-stu-id="62435-105">PowerShell provides the ability to dynamically add new properties and alter the formatting of objects output to the pipeline.</span></span>

## <a name="long-description"></a><span data-ttu-id="62435-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="62435-106">Long Description</span></span>

<span data-ttu-id="62435-107">Несколько командлетов PowerShell преобразуют, объединяют или обрабатывают входные объекты в выходных объектах с помощью параметров, которые позволяют добавлять новые свойства в эти выходные объекты.</span><span class="sxs-lookup"><span data-stu-id="62435-107">A number of PowerShell cmdlets transform, aggregate, or process input objects into output objects using parameters that allow the addition of new properties to those output objects.</span></span> <span data-ttu-id="62435-108">Эти параметры можно использовать для создания новых вычисляемых свойств для выходных объектов на основе значений входных объектов.</span><span class="sxs-lookup"><span data-stu-id="62435-108">These parameters can be used to generate new, calculated properties on output objects based on the values of input objects.</span></span>
<span data-ttu-id="62435-109">Вычисляемое свойство определяется [Hashtable](about_hash_tables.md) , содержащим пары "ключ-значение", которые указывают имя нового свойства, выражение для вычисления значения и необязательные сведения о форматировании.</span><span class="sxs-lookup"><span data-stu-id="62435-109">The calculated property is defined by a [hashtable](about_hash_tables.md) containing key-value pairs that specify the name of the new property, an expression to calculate the value, and optional formatting information.</span></span>

## <a name="supported-cmdlets"></a><span data-ttu-id="62435-110">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="62435-110">Supported cmdlets</span></span>

<span data-ttu-id="62435-111">Следующие командлеты поддерживают значения вычисляемых свойств для параметра **Property** .</span><span class="sxs-lookup"><span data-stu-id="62435-111">The following cmdlets support calculated property values for the **Property** parameter.</span></span> <span data-ttu-id="62435-112">`Format-*`Командлеты также поддерживают вычисленные значения для параметра **GroupBy** .</span><span class="sxs-lookup"><span data-stu-id="62435-112">The `Format-*` cmdlets also support calculated values for the **GroupBy** parameter.</span></span>

<span data-ttu-id="62435-113">В следующем списке перечислены командлеты, которые поддерживают вычисляемые свойства и пары "ключ-значение", поддерживаемые каждым командлетом.</span><span class="sxs-lookup"><span data-stu-id="62435-113">The following list itemizes the cmdlets that support calculated properties and the key-value pairs that are supported by each cmdlet.</span></span>

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - <span data-ttu-id="62435-114">`name`/`label` — необязательно (добавляется в PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="62435-114">`name`/`label` - optional (added in PowerShell 6.x)</span></span>
  - `expression`
  - <span data-ttu-id="62435-115">`width` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-115">`width` - optional</span></span>
  - <span data-ttu-id="62435-116">`alignment` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-116">`alignment` - optional</span></span>

- `Format-Custom`
  - `expression`
  - <span data-ttu-id="62435-117">`depth` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-117">`depth` - optional</span></span>

- `Format-List`
  - <span data-ttu-id="62435-118">`name`/`label` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-118">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="62435-119">`formatstring` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-119">`formatstring` - optional</span></span>

  <span data-ttu-id="62435-120">Этот же набор пар "ключ-значение" также применяется к вычисляемым значениям свойств, передаваемым параметру **GroupBy** для всех `Format-*` командлетов.</span><span class="sxs-lookup"><span data-stu-id="62435-120">This same set of key-value pairs also apply to calculated property values passed to the **GroupBy** parameter for all `Format-*` cmdlets.</span></span>

- `Format-Table`
  - <span data-ttu-id="62435-121">`name`/`label` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-121">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="62435-122">`formatstring` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-122">`formatstring` - optional</span></span>
  - <span data-ttu-id="62435-123">`width` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-123">`width` - optional</span></span>
  - <span data-ttu-id="62435-124">`alignment` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-124">`alignment` - optional</span></span>

- `Format-Wide`
  - `expression`
  - <span data-ttu-id="62435-125">`formatstring` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-125">`formatstring` - optional</span></span>

- `Group-Object`
  - `expression`

- `Measure-Object`
  - <span data-ttu-id="62435-126">Поддерживает только блок скрипта для выражения, а не хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="62435-126">Only supports a script block for the expression, not a hashtable.</span></span>
  - <span data-ttu-id="62435-127">Не поддерживается в PowerShell 5,1 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="62435-127">Not supported in PowerShell 5.1 and older.</span></span>

- `Select-Object`
  - <span data-ttu-id="62435-128">`name`/`label` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-128">`name`/`label` - optional</span></span>
  - `expression`

- `Sort-Object`
  - `expression`
  - <span data-ttu-id="62435-129">`ascending`/`descending` — необязательно</span><span class="sxs-lookup"><span data-stu-id="62435-129">`ascending`/`descending` - optional</span></span>

> [!NOTE]
> <span data-ttu-id="62435-130">Значением параметра `expression` может быть блок скрипта, а не хэш-таблица.</span><span class="sxs-lookup"><span data-stu-id="62435-130">The value of the `expression` can be a script block instead of a hashtable.</span></span> <span data-ttu-id="62435-131">Дополнительные сведения см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="62435-131">For more information, see the [Notes](#notes) section.</span></span>

## <a name="hashtable-key-definitions"></a><span data-ttu-id="62435-132">Определения ключей хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="62435-132">Hashtable key definitions</span></span>

- <span data-ttu-id="62435-133">`name`/`label` — Указывает имя создаваемого свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-133">`name`/`label` - Specifies the name of the property being created.</span></span> <span data-ttu-id="62435-134">Вы можете использовать `name` или его псевдоним, который является `label` взаимозаменяемым.</span><span class="sxs-lookup"><span data-stu-id="62435-134">You can use `name` or its alias, `label`, interchangeably.</span></span>
- <span data-ttu-id="62435-135">`expression` — Блок скрипта, используемый для вычисления значения нового свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-135">`expression` - A script block used to calculate the value of the new property.</span></span>
- <span data-ttu-id="62435-136">`alignment` — Используется командлетами, которые создают табличные выходные данные для определения способа отображения значений в столбце.</span><span class="sxs-lookup"><span data-stu-id="62435-136">`alignment` - Used by cmdlets that produce tabular output to define how the values are displayed in a column.</span></span> <span data-ttu-id="62435-137">Значение должно быть `'left'` , `'center'` или `'right'` .</span><span class="sxs-lookup"><span data-stu-id="62435-137">The value must be `'left'`, `'center'`, or `'right'`.</span></span>
- <span data-ttu-id="62435-138">`formatstring` — Задает строку формата, определяющую формат значения для вывода.</span><span class="sxs-lookup"><span data-stu-id="62435-138">`formatstring` - Specifies a format string that defines how the value is formatted for output.</span></span> <span data-ttu-id="62435-139">Дополнительные сведения о строках формата см. [в разделе Типы форматов в .NET](/dotnet/standard/base-types/formatting-types).</span><span class="sxs-lookup"><span data-stu-id="62435-139">For more information about format strings, see [Format types in .NET](/dotnet/standard/base-types/formatting-types).</span></span>
- <span data-ttu-id="62435-140">`width` — Задает столбец максимальной ширины в таблице при отображении значения.</span><span class="sxs-lookup"><span data-stu-id="62435-140">`width` - Specifies the maximum width column in a table when the value is displayed.</span></span> <span data-ttu-id="62435-141">Значение должно быть больше `0` .</span><span class="sxs-lookup"><span data-stu-id="62435-141">The value must be greater than `0`.</span></span>
- <span data-ttu-id="62435-142">`depth` — Параметр **Depth** параметра `Format-Custom` указывает глубину расширения для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="62435-142">`depth` - The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="62435-143">`depth`Ключ позволяет указать глубину расширения для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-143">The `depth` key allows you to specify the depth of expansion per property.</span></span>
- <span data-ttu-id="62435-144">`ascending` / `descending` — Позволяет указать порядок сортировки для одного или нескольких свойств.</span><span class="sxs-lookup"><span data-stu-id="62435-144">`ascending` / `descending` - Allows you to specify the order of sorting for one or more properties.</span></span> <span data-ttu-id="62435-145">Это логические значения.</span><span class="sxs-lookup"><span data-stu-id="62435-145">These are boolean values.</span></span>

<span data-ttu-id="62435-146">Ключи Hashtable не должны быть написаны, пока указанный префикс имени не является неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="62435-146">The hashtable keys need not be spelled out as long as the specified name prefix is unambiguous.</span></span> <span data-ttu-id="62435-147">Например, `n` можно использовать вместо `Name` и `e` может использоваться вместо `Expression` .</span><span class="sxs-lookup"><span data-stu-id="62435-147">For example, `n` can be used in lieu of `Name` and `e` can be used in lieu of `Expression`.</span></span>

## <a name="examples"></a><span data-ttu-id="62435-148">Примеры</span><span class="sxs-lookup"><span data-stu-id="62435-148">Examples</span></span>

### <a name="compare-object"></a><span data-ttu-id="62435-149">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="62435-149">Compare-Object</span></span>

<span data-ttu-id="62435-150">С помощью вычисляемых свойств можно управлять способом сравнения свойств входных объектов.</span><span class="sxs-lookup"><span data-stu-id="62435-150">With calculated properties, you can control how the properties of the input objects are compared.</span></span> <span data-ttu-id="62435-151">В этом примере вместо непосредственного сравнения значений значения сравниваются с результатом арифметической операции (модуль из 2).</span><span class="sxs-lookup"><span data-stu-id="62435-151">In this example, rather than comparing the values directly, the values are compared to the result of the arithmetic operation (modulus of 2).</span></span>

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a><span data-ttu-id="62435-152">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="62435-152">ConvertTo-Html</span></span>

<span data-ttu-id="62435-153">`ConvertTo-Html` может преобразовать коллекцию объектов в таблицу HTML.</span><span class="sxs-lookup"><span data-stu-id="62435-153">`ConvertTo-Html` can convert a collection of objects to an HTML table.</span></span>
<span data-ttu-id="62435-154">Вычисляемые свойства позволяют управлять способом представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="62435-154">Calculated properties allow you to control how the table is presented.</span></span>

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

<span data-ttu-id="62435-155">В этом примере создается таблица HTML, содержащая список псевдонимов PowerShell и числовые параметры для каждой команды с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="62435-155">This example creates an HTML table containing a list of PowerShell aliases and the number parameters for each aliased command.</span></span> <span data-ttu-id="62435-156">Значения столбца **параметеркаунт** центрируются по центру.</span><span class="sxs-lookup"><span data-stu-id="62435-156">The values of **ParameterCount** column are centered.</span></span>

### <a name="format-custom"></a><span data-ttu-id="62435-157">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="62435-157">Format-Custom</span></span>

<span data-ttu-id="62435-158">`Format-Custom` предоставляет пользовательское представление объекта в формате, аналогичном определению класса.</span><span class="sxs-lookup"><span data-stu-id="62435-158">`Format-Custom` provides a custom view of an object in a format similar to a class definition.</span></span> <span data-ttu-id="62435-159">Более сложные объекты могут содержать элементы, которые глубоко вложены в сложные типы.</span><span class="sxs-lookup"><span data-stu-id="62435-159">More complex objects can contain members that are deeply nested with complex types.</span></span> <span data-ttu-id="62435-160">Параметр **Depth** параметра `Format-Custom` указывает глубину расширения для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="62435-160">The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="62435-161">`depth`Ключ позволяет указать глубину расширения для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-161">The `depth` key allows you to specify the depth of expansion per property.</span></span>

<span data-ttu-id="62435-162">В этом примере `depth` ключ упрощает пользовательский вывод для `Get-Date` командлета.</span><span class="sxs-lookup"><span data-stu-id="62435-162">In this example, the `depth` key simplifies the custom output for the `Get-Date` cmdlet.</span></span> <span data-ttu-id="62435-163">`Get-Date` Возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="62435-163">`Get-Date` returns a **DateTime** object.</span></span> <span data-ttu-id="62435-164">Свойство **Date** этого объекта также является объектом **DateTime** , поэтому объект является вложенным.</span><span class="sxs-lookup"><span data-stu-id="62435-164">The **Date** property of this object is also a **DateTime** object, so the object is nested.</span></span>

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

### <a name="format-list"></a><span data-ttu-id="62435-165">Format-List</span><span class="sxs-lookup"><span data-stu-id="62435-165">Format-List</span></span>

<span data-ttu-id="62435-166">В этом примере мы используем вычисляемые свойства для изменения имени и формата выходных данных из `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="62435-166">In this example, we use calculated properties to change the name and format of the output from `Get-ChildItem`.</span></span>

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

### <a name="format-table"></a><span data-ttu-id="62435-167">Format-Table</span><span class="sxs-lookup"><span data-stu-id="62435-167">Format-Table</span></span>

<span data-ttu-id="62435-168">В этом примере вычисляемое свойство добавляет свойство **Type** , используемое для классификации файлов по типу содержимого.</span><span class="sxs-lookup"><span data-stu-id="62435-168">In this example, the calculated property adds a **Type** property used to classify the files by the content type.</span></span>

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

### <a name="format-wide"></a><span data-ttu-id="62435-169">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="62435-169">Format-Wide</span></span>

<span data-ttu-id="62435-170">`Format-Wide`Командлет позволяет отображать значение одного свойства для объектов в коллекции в виде списка с несколькими столбцами.</span><span class="sxs-lookup"><span data-stu-id="62435-170">The `Format-Wide` cmdlet allows you to display the value of one property for objects in a collection as a multi-column list.</span></span>

<span data-ttu-id="62435-171">В этом примере мы хотим увидеть имя файла и размер (в килобайтах) в качестве широкого списка.</span><span class="sxs-lookup"><span data-stu-id="62435-171">For this example, we want to see the filename and the size (in kilobytes) as a wide listing.</span></span> <span data-ttu-id="62435-172">Поскольку не `Format-Wide` отображает более одного свойства, мы используем вычисляемое свойство, чтобы объединить значения двух свойств в одно значение.</span><span class="sxs-lookup"><span data-stu-id="62435-172">Since `Format-Wide` does not display more than one property, we use a calculated property to combine the value of two properties into a single value.</span></span>

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

### <a name="group-object"></a><span data-ttu-id="62435-173">Group-Object</span><span class="sxs-lookup"><span data-stu-id="62435-173">Group-Object</span></span>

<span data-ttu-id="62435-174">`Group-Object`Командлет отображает объекты в группах на основе значения указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-174">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span> <span data-ttu-id="62435-175">В этом примере вычисляемое свойство подсчитывает количество файлов каждого типа содержимого.</span><span class="sxs-lookup"><span data-stu-id="62435-175">In this example, the calculated property counts the number of files of each content type.</span></span>

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

### <a name="select-object"></a><span data-ttu-id="62435-176">Select-Object;</span><span class="sxs-lookup"><span data-stu-id="62435-176">Select-Object</span></span>

<span data-ttu-id="62435-177">Вычисляемые свойства можно использовать для добавления дополнительных элементов в выходные данные объектов с помощью `Select-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="62435-177">You can use calculated properties to add additional members to the objects output with the `Select-Object` cmdlet.</span></span> <span data-ttu-id="62435-178">В этом примере мы перечислим псевдонимы PowerShell, которые начинаются с буквы `C` .</span><span class="sxs-lookup"><span data-stu-id="62435-178">In this example, we are listing the PowerShell aliases that begin with the letter `C`.</span></span> <span data-ttu-id="62435-179">Используя `Select-Object` , мы выводим псевдоним, командлет, с которым он сопоставлен, и количество параметров, определенных для командлета.</span><span class="sxs-lookup"><span data-stu-id="62435-179">Using `Select-Object`, we output the alias, the cmdlet it's mapped to, and a count for the number of parameters defined for the cmdlet.</span></span> <span data-ttu-id="62435-180">Используя вычисляемое свойство, можно создать свойство **параметеркаунт** .</span><span class="sxs-lookup"><span data-stu-id="62435-180">Using a calculated property, we can create the **ParameterCount** property.</span></span>

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

### <a name="sort-object"></a><span data-ttu-id="62435-181">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="62435-181">Sort-Object</span></span>

<span data-ttu-id="62435-182">С помощью вычисляемых свойств можно сортировать данные по разным заказам для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="62435-182">Using the calculated properties, you can sort data in different orders per property.</span></span> <span data-ttu-id="62435-183">В этом примере данные из CSV-файла сортируются в порядке возрастания по **дате**.</span><span class="sxs-lookup"><span data-stu-id="62435-183">This example sorts data from a CSV file in ascending order by **Date**.</span></span> <span data-ttu-id="62435-184">Но внутри каждой даты сортируются строки в убывающем порядке по **унитссолд**.</span><span class="sxs-lookup"><span data-stu-id="62435-184">But within each date, it sorts the rows in descending order by **UnitsSold**.</span></span>

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

## <a name="notes"></a><span data-ttu-id="62435-185">Примечания</span><span class="sxs-lookup"><span data-stu-id="62435-185">Notes</span></span>

- <span data-ttu-id="62435-186">Блок скрипта выражения можно указать _непосредственно_ в качестве аргумента вместо того, чтобы указывать его в качестве `Expression` записи в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="62435-186">You may specify the expression script block _directly_ , as an argument, rather than specifying it as the `Expression` entry in a hashtable.</span></span> <span data-ttu-id="62435-187">Пример:</span><span class="sxs-lookup"><span data-stu-id="62435-187">For example:</span></span>

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  <span data-ttu-id="62435-188">Этот пример удобен для командлетов, которым не требуется (или не поддерживается) именование свойства с помощью `Name` ключа, например `Sort-Object` , `Group-Object` и `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="62435-188">This example is convenient for cmdlets that do not require (or support) naming a property via the `Name` key, such as `Sort-Object`, `Group-Object`, and `Measure-Object`.</span></span>

  <span data-ttu-id="62435-189">Для командлетов, которые поддерживают именование свойства, блок скрипта преобразуется в строку и используется в качестве имени свойства в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="62435-189">For cmdlets that support naming the property, the script block is converted to a string and used as the name of the property in the output.</span></span>

- <span data-ttu-id="62435-190">`Expression` блоки скриптов выполняются в _дочерних_ областях, то есть переменные вызывающего объекта нельзя изменять напрямую.</span><span class="sxs-lookup"><span data-stu-id="62435-190">`Expression` script blocks run in _child_ scopes, meaning that the caller's variables cannot be directly modified.</span></span>

- <span data-ttu-id="62435-191">Логика конвейера применяется к выходным данным из `Expression` блоков скриптов.</span><span class="sxs-lookup"><span data-stu-id="62435-191">Pipeline logic is applied to the output from `Expression` script blocks.</span></span> <span data-ttu-id="62435-192">Это означает, что вывод массива с одним элементом приводит к развернутому массиву.</span><span class="sxs-lookup"><span data-stu-id="62435-192">This means that outputting a single-element array causes that array to be unwrapped.</span></span>

- <span data-ttu-id="62435-193">Для большинства командлетов ошибки внутри блоков скриптов выражений не учитываются.</span><span class="sxs-lookup"><span data-stu-id="62435-193">For most cmdlets, errors inside expression script blocks are quietly ignored.</span></span>
  <span data-ttu-id="62435-194">Для `Sort-Object` , завершающие выполнение инструкций и ошибки, заканчивающиеся скриптом, являются _выходными_ , но не завершают инструкцию.</span><span class="sxs-lookup"><span data-stu-id="62435-194">For `Sort-Object`, statement-terminating and script-terminating errors are _output_ but they do not terminate the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="62435-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="62435-195">See Also</span></span>

[<span data-ttu-id="62435-196">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="62435-196">about_Hash_Tables</span></span>](about_hash_tables.md)

[<span data-ttu-id="62435-197">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="62435-197">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="62435-198">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="62435-198">ConvertTo-Html</span></span>](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[<span data-ttu-id="62435-199">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="62435-199">Format-Custom</span></span>](xref:Microsoft.PowerShell.Utility.Format-Custom)

[<span data-ttu-id="62435-200">Format-List</span><span class="sxs-lookup"><span data-stu-id="62435-200">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

[<span data-ttu-id="62435-201">Format-Table</span><span class="sxs-lookup"><span data-stu-id="62435-201">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="62435-202">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="62435-202">Format-Wide</span></span>](xref:Microsoft.PowerShell.Utility.Format-Wide)

[<span data-ttu-id="62435-203">Group-Object</span><span class="sxs-lookup"><span data-stu-id="62435-203">Group-Object</span></span>](xref:Microsoft.PowerShell.Utility.Group-Object)

[<span data-ttu-id="62435-204">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="62435-204">Measure-Object</span></span>](xref:Microsoft.PowerShell.Utility.Measure-Object)

[<span data-ttu-id="62435-205">Select-Object</span><span class="sxs-lookup"><span data-stu-id="62435-205">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="62435-206">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="62435-206">Sort-Object</span></span>](xref:Microsoft.PowerShell.Utility.Sort-Object)

[<span data-ttu-id="62435-207">Форматирование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="62435-207">Format types in .NET</span></span>](/dotnet/standard/base-types/formatting-types)
