---
description: Объясняет, как использовать параметр для выполнения нескольких `If` инструкций.
keywords: powershell,командлет
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 1cb0e95aa942af4aa29f449da0c7cbbaf15d7dc5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231910"
---
# <a name="about-switch"></a>О параметре

## <a name="short-description"></a>Краткое описание
Объясняет, как использовать параметр для выполнения нескольких `If` инструкций.

## <a name="long-description"></a>Подробное описание

Чтобы проверить условие в скрипте или функции, используйте `If` инструкцию. `If`Инструкция может проверять различные типы условий, в том числе значения переменных и свойства объектов.

Чтобы проверить несколько условий, используйте `Switch` оператор. `Switch`Оператор эквивалентен ряду `If` операторов, но проще. `Switch`Инструкция перечисляет все условия и необязательное действие. Если условие получает значение, выполняется действие.

`Switch`Инструкция может использовать `$_` `$switch` переменные и автоматически. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

Базовый `Switch` оператор имеет следующий формат:

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

Например, следующая `Switch` инструкция сравнивает тестовое значение, 3, с каждым из условий. Когда тестовое значение соответствует условию, выполняется действие.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

В этом простом примере значение сравнивается с каждым условием в списке, несмотря на совпадение со значением 3. Следующая `Switch` инструкция имеет два условия для значения 3. В нем показано, что по умолчанию проверяются все условия.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

Чтобы перенаправление `Switch` для отмены сравнения после совпадения, используйте `Break` инструкцию. `Break`Оператор завершает выполнение `Switch` инструкции.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

Если тестовое значение является коллекцией, например массивом, каждый элемент в коллекции вычисляется в том порядке, в котором он отображается. В следующих примерах вычисляется 4, а затем 2.

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

Любые `Break` инструкции применяются к коллекции, а не к каждому значению, как показано в следующем примере. `Switch`Оператор завершается `Break` оператором в условии value 4.

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a>Синтаксис

Полный `Switch` синтаксис инструкции выглядит следующим образом:

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

or

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

Если параметры не используются, `Switch` ведет себя так же, как при использовании **точного** параметра. Для этого значения выполняется сравнение без учета регистра. Если значение является коллекцией, каждый элемент вычисляется в том порядке, в котором он отображается.

`Switch`Инструкция должна включать хотя бы одну инструкцию Condition.

`Default`Предложение активируется, если значение не соответствует ни одному из условий. Он эквивалентен `Else` предложению в `If` операторе. `Default`В каждой инструкции допускается только одно предложение `Switch` .

`Switch` имеет следующие параметры:

- **Подстановочный знак** — указывает, что условие является строкой с подстановочными знаками. Если предложение Match не является строкой, параметр игнорируется. При сравнении регистр не учитывается.
- **СОВПАД** — указывает, что предложение Match, если оно является строкой, должно точно совпадать. Если предложение Match не является строкой, этот параметр игнорируется. При сравнении регистр не учитывается.
- **CaseSensitive** — выполняет совпадение с учетом регистра. Если предложение Match не является строкой, этот параметр игнорируется.
- **Файл** — принимает входные данные из файла, а не из оператора значения. Если включено несколько параметров **файла** , используется только последний из них. Каждая строка файла считывается и оценивается `Switch` инструкцией. При сравнении регистр не учитывается.
- **Regex** — выполняет регулярное выражение, совпадающее со значением условия. Если предложение Match не является строкой, этот параметр игнорируется.
  При сравнении регистр не учитывается. `$matches`Автоматическая переменная доступна для использования в блоке инструкций Match.

> [!NOTE]
> При указании конфликтующих значений, таких как **регулярное выражение** и **подстановочный знак** , последний заданный параметр имеет приоритет, а все конфликтующие параметры игнорируются. Также разрешено использовать несколько экземпляров параметров. Однако действует только последний использованный параметр.

В этом примере объект, не являющийся строкой или числовыми данными, передается в `Switch` . `Switch`Выполняет приведение строк для объекта и вычисляет результат.

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

В этом примере нет соответствующего регистра, поэтому выходные данные отсутствуют.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

Добавив `Default` предложение, можно выполнить действие, когда никакие другие условия не будут выполнены.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

Чтобы слово «четырнадцать» соответствовало регистру, необходимо использовать `-Wildcard` `-Regex` параметр или.

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

В следующем примере используется `-Regex` параметр.

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

Условие оператора switch может иметь одно из следующих условий:

- Выражение, значение которого сравнивается с входным значением
- Блок скрипта, который должен возвращать, `$true` Если условие выполнено.

`$_`Автоматическая переменная содержит значение, передаваемое оператору switch, и доступно для оценки и использования в области операторов условия.

Действие для каждого условия не зависит от действий в других условиях.

В следующем примере показано использование блоков script в качестве `Switch` условий инструкции.

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

Если значение соответствует нескольким условиям, выполняется действие для каждого условия. Чтобы изменить это поведение, используйте `Break` `Continue` Ключевые слова или.

`Break`Ключевое слово останавливает обработку и завершает выполнение `Switch` инструкции.

`Continue`Ключевое слово останавливает обработку текущего значения, но возобновляет обработку всех последующих значений.

В следующем примере выполняется обработка массива чисел и отображение, если они являются нечетными или четными. Отрицательные числа пропускаются с помощью `Continue` ключевого слова. Если обнаружено нечисловое значение, выполнение завершается с помощью `Break` ключевого слова.

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a>См. также статью

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)
