---
description: Описание ключевых слов в языке сценариев PowerShell.
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_keywords?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Keywords
ms.openlocfilehash: 4136e5fe6b0e3ad2ba1ec41d2dc9a8fba7b88f56
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600465"
---
# <a name="about-language-keywords"></a>О ключевых словах языка

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описание ключевых слов в языке сценариев PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

PowerShell имеет следующие ключевые слова языка. Дополнительные сведения см. в разделе о ключевом слове и сведениях, следующих за таблицей.

Ключевое слово     | Справочник
---         | ---
Начать       | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Разбиение       | [about_Break](about_Break.md), [about_Trap](about_Trap.md)
Catch       | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Class       | [about_Classes](about_Classes.md)
Продолжить    | [about_Continue](about_Continue.md), [about_Trap](about_Trap.md)
Данные        | [about_Data_Sections](about_Data_Sections.md)
Определение      | Зарезервировано для использования в будущем.
Рекомендуется          | [about_Do](about_Do.md), [about_While](about_While.md)
динамикпарам| [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)
ELSE        | [about_If](about_If.md)
ElseIf      | [about_If](about_If.md)
Конец         | [about_Functions](about_Functions.md), [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Перечисление        | [about_Enum](about_Enum.md)
Выход        | [Описывается в этом разделе](#exit)
Фильтр      | [about_Functions](about_Functions.md)
Finally     | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Для         | [about_For](about_For.md)
ForEach     | [about_ForEach](about_ForEach.md)
От        | Зарезервировано для использования в будущем.
Компонент    | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Скрытый      | [about_Hidden](about_Hidden.md)
If          | [about_If](about_If.md)
В          | [about_ForEach](about_ForEach.md)
Параметр       | [about_Functions](about_Functions.md)
Процесс     | [about_Functions](about_Functions.md), [about_Functions_Advanced](about_Functions_Advanced.md)
Возвращает      | [about_Return](about_Return.md)
Статические      | [about_Classes](about_Classes.md)
Коммутатор      | [about_Switch](about_Switch.md)
Ключевое слово throw       | [about_Throw](about_Throw.md), [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Ключевое слово trap        | [about_Trap](about_Trap.md), [about_Break](about_Break.md) [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Попытка         | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Вплот       | [about_Do](about_Do.md)
Использование       | [about_Using](about_Using.md), [about_Classes](about_Classes.md)
Var         | Зарезервировано для использования в будущем.
While       | [about_While](about_While.md), [about_Do](about_Do.md)

ключевые слова языка;

### <a name="begin"></a>Начать

Задает одну часть тела функции, а также `DynamicParam` `Process` `End` Ключевые слова, и. `Begin`Список инструкций выполняется один раз перед получением любых объектов из конвейера.

Синтаксис:

```Syntax
function <name> {
    DynamicParam {<statement list>}
    begin {<statement list>}
    process {<statement list>}
    end {<statement list>}
}
```

### <a name="break"></a>Разбиение

Заставляет скрипт выйти из цикла.

Синтаксис:

```Syntax
while (<condition>) {
   <statements>
   ...

   break
   ...

   <statements>
}
```

### <a name="catch"></a>Catch

Указывает список инструкций для выполнения в случае возникновения ошибки в сопутствующем списке инструкций try. Для типа ошибки требуются квадратные скобки. Вторая пара скобок указывает, что тип ошибки является необязательным.

Синтаксис:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
```

### <a name="class"></a>Class

Указывает новый класс в PowerShell.

Синтаксис:

```Syntax
class <class-name> {
    [[hidden] [static] <property-definition> ...]
    [<class-name>([argument-list>]) {<constructor-statement-list>} ...]
    [[hidden] [static] <method-definition> ...]
}
```

### <a name="continue"></a>Продолжить

Заставляет сценарий прерывать выполнение цикла и возвращаться к условию. Если условие выполнено, скрипт начинает цикл снова.

Синтаксис:

```Syntax
while (<condition>) {
   <statements>
   ...

   continue
   ...

   <statements>
}
```

### <a name="data"></a>Данные

В скрипте определяет раздел, который изолирует данные из логики скрипта. Также может включать `If` инструкции и некоторые ограниченные команды.

Синтаксис:

```Syntax
data <variable> [-supportedCommand <cmdlet-name>] {<permitted content>}
```

### <a name="do"></a>Рекомендуется

Используется с `While` `Until` ключевым словом или в качестве циклической конструкции. PowerShell запускает список инструкций по крайней мере один раз, в отличие от цикла, в котором используется `While` .

Синтаксис для `While`:

```Syntax
do {<statement list>} while (<condition>)
```

Синтаксис для `Until`:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="dynamicparam"></a>динамикпарам

Задает одну часть тела функции, а также `Begin` `Process` `End` Ключевые слова, и. Динамические параметры добавляются во время выполнения.

Синтаксис:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="else"></a>ELSE

Используется с `If` ключевым словом для указания списка инструкций по умолчанию.

Синтаксис:

```Syntax
if (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="elseif"></a>ElseIf

Используется с `If` `Else` ключевыми словами и для указания дополнительных условий. `Else`Ключевое слово является необязательным.

Синтаксис:

```Syntax
if (<condition>) {<statement list>}
elseif (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="end"></a>Конец

Задает одну часть тела функции, а также `DynamicParam` `Begin` `End` Ключевые слова, и. `End`Список инструкций выполняется один раз после того, как все объекты были получены из конвейера.

Синтаксис:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="enum"></a>Перечисление

`enum` используется для объявления перечисления; отдельный тип, состоящий из набора именованных меток, который называется списком перечислителей.

Синтаксис:

```Syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

### <a name="exit"></a>Выход

Заставляет PowerShell выйти из скрипта или экземпляра PowerShell.

Синтаксис:

```Syntax
exit
exit <exitcode>
```

При использовании `pwsh` с параметром **File** `.ps1` сам файл (скрипт) должен содержать инструкции для обработки ошибок и исключений, происходящих во время выполнения скрипта. Оператор следует использовать только `exit` для указания состояния скрипта после выполнения.

В Windows допускается любое число между `[int]::MinValue` и `[int]::MaxValue` .

В UNIX разрешены только положительные числа в диапазоне от `[byte]::MinValue` до `[byte]::MaxValue` . Отрицательное число в диапазоне от `-1` до `-255` автоматически преобразуется в положительное число путем сложения 256. Например, `-2` преобразуется в `254` .

В PowerShell `exit` инструкция задает значение `$LASTEXITCODE` переменной. В командной оболочке Windows (cmd.exe) оператор Exit задает значение `%ERRORLEVEL%` переменной среды.

Любой аргумент, который не является числовым или вне диапазона, зависящего от платформы, преобразуется в значение `0` .

В следующем примере пользователь задает для переменной уровня ошибки значение 4, добавив `exit 4` в файл скрипта `test.ps1` .

```cmd
C:\scripts\test>type test.ps1
1
2
3
exit 4

C:\scripts\test>pwsh -file ./test.ps1
1
2
3

C:\scripts\test>echo %ERRORLEVEL%
4
```

При запуске `pwsh.exe -File <path to a script>` и завершении файла скрипта с помощью `exit` команды в качестве кода выхода задается числовой аргумент, используемый в `exit` команде. Если в скрипте нет `exit` оператора, код выхода всегда выполняется, `0` когда сценарий завершается без ошибок или `1` когда скрипт завершается из необработанного исключения.

### <a name="filter"></a>Фильтр

Указывает функцию, в которой список инструкций выполняется один раз для каждого входного объекта. Он действует так же, как функция, содержащая только блок Process.

Синтаксис:

```Syntax
filter <name> {<statement list>}
```

### <a name="finally"></a>Finally

Определяет список инструкций, выполняемых после инструкций, связанных с try и catch. `Finally`Список инструкций выполняется, даже если нажать клавишу, `CTRL+C` чтобы выйти из скрипта или использовать в скрипте ключевое слово Exit.

Синтаксис:

```Syntax
try {<statement list>}
catch [<error type>] {<statement list>}
finally {<statement list>}
```

### <a name="for"></a>Для

Определяет цикл с помощью условия.

Синтаксис:

```Syntax
for (<initialize>; <condition>; <iterate>) { <statement list> }
```

### <a name="foreach"></a>ForEach

Определяет цикл, используя каждый элемент коллекции.

Синтаксис:

```Syntax
ForEach (<item> in <collection>) { <statement list> }
```

### <a name="from"></a>От

Зарезервировано для будущего использования.

### <a name="function"></a>Компонент

Создает список именованных инструкций для повторного использования кода. Можно задать имя области, которой принадлежит функция. И можно указать один или несколько именованных параметров с помощью `Param` ключевого слова. В списке инструкций Function можно включать `DynamicParam` `Begin` `Process` списки инструкций,, и `End` .

Синтаксис:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1> [, [type]<$pname2>])
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

Кроме того, можно определить один или несколько параметров вне списка операторов после имени функции.

Синтаксис:

```Syntax
function [<scope:>]<name> [([type]<$pname1>, [[type]<$pname2>])] {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="if"></a>If

Определяет условное значение.

Синтаксис:

```Syntax
if (<condition>) {<statement list>}
```

### <a name="hidden"></a>Скрытый

Скрывает члены класса от результатов по умолчанию для `Get-Member` командлета, а также от результатов выполнения функций IntelliSense и табуляции.

Синтаксис:

```Syntax
Hidden [data type] $member_name
```

### <a name="in"></a>В

Используется в `ForEach` инструкции для создания цикла, использующего каждый элемент коллекции.

Синтаксис:

```Syntax
ForEach (<item> in <collection>){<statement list>}
```

### <a name="inlinescript"></a>InlineScript (Встроенный сценарий)

Запускает команды рабочего процесса в общем сеансе PowerShell. Это ключевое слово допустимо только в рабочем процессе PowerShell.

Синтаксис:

```Syntax
workflow <verb>-<noun>
{
   InlineScript
   {
      <Command/Expression>
      ...

   }
}
```

`InlineScript`Ключевое слово указывает на `InlineScript` действие, которое запускает команды в сеансе общего стандартного (не рабочего процесса). `InlineScript`Ключевое слово можно использовать для выполнения команд, которые не являются допустимыми в рабочем процессе, а также для выполнения команд, которые совместно используют данные. По умолчанию команды в блоке сценария InlineScript выполняются в отдельном процессе.

Дополнительные сведения см. [в разделе Выполнение команд PowerShell в рабочем процессе](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574197(v=ws.11)).

### <a name="param"></a>Параметр

Определяет параметры в функции.

Синтаксис:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1>[, [[type]<$pname2>]])
   <statement list>
}
```

### <a name="process"></a>Процесс

Указывает часть тела функции, а также `DynamicParam` `Begin` `End` Ключевые слова, и. Когда `Process` список инструкций получает входные данные из конвейера, `Process` список инструкций выполняется один раз для каждого элемента из конвейера. Если конвейер не предоставляет никаких объектов, `Process` список инструкций не выполняется. Если команда является первой командой в конвейере, `Process` список инструкций выполняется один раз.

Синтаксис:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="return"></a>Возвращает

Приводит к тому, что PowerShell оставляет текущую область, например сценарий или функцию, и записывает необязательное выражение в выходные данные.

Синтаксис:

```Syntax
return [<expression>]
```

### <a name="static"></a>Статические

Указывает, что определяемое свойство или метод является общим для всех экземпляров класса, в которых определен.

`Class`Примеры использования см. в разделе.

### <a name="switch"></a>Коммутатор

Чтобы проверить несколько условий, используйте `Switch` оператор. `Switch`Оператор эквивалентен ряду `If` операторов, но проще.

`Switch`Инструкция перечисляет все условия и необязательное действие. Если условие получает значение, выполняется действие.

Синтаксис 1:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] ( <value> )
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

Синтаксис 2:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] -file <filename>
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

### <a name="throw"></a>Ключевое слово throw

Создает объект как ошибку.

Синтаксис:

```Syntax
throw [<object>]
```

### <a name="trap"></a>Ключевое слово trap

Определяет список инструкций для выполнения в случае возникновения ошибки. Для типа ошибки требуются квадратные скобки. Вторая пара скобок указывает, что тип ошибки является необязательным.

Синтаксис:

```Syntax
trap [[<error type>]] {<statement list>}
```

### <a name="try"></a>Попытка

Определяет список инструкций, проверяемых на наличие ошибок во время выполнения инструкций. При возникновении ошибки PowerShell продолжит выполнение в `Catch` `Finally` операторе или. Для типа ошибки требуются квадратные скобки. Вторая пара скобок указывает, что тип ошибки является необязательным.

Синтаксис:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
finally {<statement list>}
```

### <a name="until"></a>Вплот

Используется в `Do` инструкции в качестве циклической конструкции, где список инструкций выполняется по крайней мере один раз.

Синтаксис:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="using"></a>Использование

Позволяет указать, какие пространства имен используются в сеансе. Для упоминания классов и членов требуется меньше ввода. Также можно включать классы из модулей.

#1 синтаксиса:

```Syntax
using namespace <.Net-framework-namespace>
```

#2 синтаксиса:

```Syntax
using module <module-name>
```

### <a name="while"></a>While

`while`Оператор является циклической конструкцией, в которой условие проверяется перед выполнением инструкций. Если условие имеет значение FALSE, инструкции не выполняются.

Синтаксис инструкции:

```Syntax
while (<condition>) {
   <statements>
 }
```

При использовании в `Do` операторе `while` является частью циклической конструкции, где список инструкций выполняется по крайней мере один раз.

Синтаксис цикла Do:

```Syntax
do {<statement list>} while (<condition>)
```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_Special_Characters](about_Special_Characters.md)
- [about_Wildcards](about_Wildcards.md)

