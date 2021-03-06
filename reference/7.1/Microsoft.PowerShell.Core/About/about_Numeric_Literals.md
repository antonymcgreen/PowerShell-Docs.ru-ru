---
description: Целочисленные и вещественные числовые литералы могут иметь суффиксы типа и множителя.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О числовых литералах
ms.openlocfilehash: 19ed71c2571a6cd343adf622a8cf71d6e5589aff
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354989"
---
# <a name="about-numeric-literals"></a>О числовых литералах

Существует два вида числовых литералов: integer и Real. Оба могут иметь суффиксы типа и множителя.

## <a name="integer-literals"></a>Целочисленные литералы

Целочисленные литералы могут быть записаны в десятичной, шестнадцатеричной или двоичной нотации.
Шестнадцатеричные литералы начинаются с префикса `0x` , а двоичные литералы имеют префикс, `0b` чтобы отличать их от десятичных чисел.

Целочисленные литералы могут иметь суффикс типа и суффикс множителя.

| Суффикс |            Значение             |          Примечание           |
| ------ | ------------------------------ | ----------------------- |
| да      | тип данных Byte со знаком          | Добавлено в PowerShell 6,2 |
| Uy     | тип данных Byte без знака        | Добавлено в PowerShell 6,2 |
| s      | short - тип данных                | Добавлено в PowerShell 6,2 |
| us     | короткий тип данных без знака       | Добавлено в PowerShell 6,2 |
| l      | тип данных Long                 |                         |
| u      | целое число без знака или тип данных Long | Добавлено в PowerShell 6,2 |
| ul     | тип данных Long без знака        | Добавлено в PowerShell 6,2 |
| n      | Тип данных BigInteger           | Добавлено в PowerShell 7,0 |
| kb     | множитель в килобайтах            |                         |
| mb     | множитель в мегабайтах            |                         |
| Гбайт     | множитель гигабайта            |                         |
| Тбайт     | терабайт, множитель            |                         |
| МС     | множитель петабайтного уровня            |                         |

Тип целочисленного литерала определяется его значением, суффиксом типа и суффиксом числового множителя.

Для целочисленного литерала без суффикса типа:

- Если значение может быть представлено типом `[int]` , то есть его типом.
- В противном случае, если значение может быть представлено типом `[long]` , то есть его тип.
- В противном случае, если значение может быть представлено типом `[decimal]` , то есть его тип.
- В противном случае он представлен типом `[double]` .

Для целочисленного литерала с суффиксом типа:

- Если суффикс типа — `u` , а значение может быть представлено типом, `[uint]` то его тип — `[uint]` .
- Если суффикс типа — `u` , а значение может быть представлено типом, `[ulong]` то его тип — `[ulong]` .
- Если его значение может быть представлено указанным типом, то это тип.
- В противном случае этот литерал имеет неправильный формат.

## <a name="real-literals"></a>Вещественные литералы

Реальные литералы могут быть записаны только в десятичной нотации. Эта нотация может содержать дробные значения, следующие за десятичной запятой и экспоненциальной нотацией, с использованием экспоненциальной части.

Экспоненциальная часть включает символ "e", за которым следует необязательный знак (+/-) и число, представляющее показатель степени. Например, литеральное значение `1e2` равно числовому значению 100.

Реальные литералы могут иметь суффикс типа и суффикс множителя.

| Суффикс |       Значение       |
| ------ | ------------------- |
| d      | тип данных decimal   |
| kb     | множитель в килобайтах |
| mb     | множитель в мегабайтах |
| Гбайт     | множитель гигабайта |
| Тбайт     | терабайт, множитель |
| МС     | множитель петабайтного уровня |

Существует два вида вещественных литералов: Double и Decimal. Они обозначаются отсутствием или присутствием соответственно для суффикса десятичного типа. PowerShell не поддерживает литеральное представление `[float]` значения. Двойной вещественный литерал имеет тип `[double]` . Десятичный вещественный литерал имеет тип `[decimal]` .
В дробной части вещественного десятичного литерала учитываются нули в конце.

Если значение числа цифр экспоненты в `[double]` вещественном литерале меньше минимального поддерживаемого значения, значение этого `[double]` литерала равно 0. Если значение числа цифр экспоненты в `[decimal]` вещественном литерале меньше минимального поддерживаемого значения, то литерал имеет неправильный формат. Если значение числа цифр экспоненты в `[double]` или `[decimal]` вещественном литерале больше поддерживаемого максимума, этот литерал имеет неправильный формат.

> [!NOTE]
> Синтаксис допускает наличие суффикса длинного типа в двойном вещественном литерале.
> PowerShell обрабатывает этот случай как целочисленный литерал, значение которого представлено типом `[long]` . Эта функция была сохранена для обеспечения обратной совместимости с более ранними версиями PowerShell. Однако программистам не рекомендуется использовать целочисленные литералы этой формы, так как они могут легко скрывать фактическое значение литерала. Например, `1.2L` имеет значение 1, `1.2345e1L` значение 12 и `1.2345e-5L` имеет значение 0, ни одно из этих значений сразу не очевидно.

## <a name="numeric-multipliers"></a>Числовые множители

Для удобства целочисленные и реальные литералы могут содержать числовой множитель, указывающий на один из множества часто используемых степеней 2. Числовой множитель можно записать в любом сочетании прописных или строчных букв.

Суффиксы множителя могут использоваться в сочетании с любыми суффиксами типов, но должны присутствовать после суффикса типа. Например, литерал `100gbL` имеет неправильный формат, но литерал `100Lgb` является допустимым.

Если множитель создает значение, которое превышает возможные значения для числового типа, определенного суффиксом, литерал имеет неправильный формат. Например, литерал `1usgb` имеет неправильный формат, так как значение `1gb` больше, чем разрешено для `[ushort]` типа, указанного `us` суффиксом.

### <a name="multiplier-examples"></a>Примеры множителя

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a>Сочетания числовых типов

PowerShell поддерживает следующие ускорители типов:

| Accelerator |         Примечание         |           Описание            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | Byte (без знака)                  |
| `[sbyte]`   |                      | Byte (со знаком)                    |
| `[Int16]`   |                      | 16-разрядное целое число                   |
| `[short]`   | псевдоним для `[int16]`  | 16-разрядное целое число                   |
| `[UInt16]`  |                      | 16-разрядное целое число (без знака)        |
| `[ushort]`  | псевдоним для `[uint16]` | 16-разрядное целое число (без знака)        |
| `[Int32]`   |                      | 32-разрядное целое число                   |
| `[int]`     | псевдоним для `[int32]`  | 32-разрядное целое число                   |
| `[UInt32]`  |                      | 32-разрядное целое число (без знака)        |
| `[uint]`    | псевдоним для `[uint32]` | 32-разрядное целое число (без знака)        |
| `[Int64]`   |                      | 64-разрядное целое число                   |
| `[long]`    | псевдоним для `[int64]`  | 64-разрядное целое число                   |
| `[UInt64]`  |                      | 64-разрядное целое число (без знака)        |
| `[ulong]`   | псевдоним для `[uint64]` | 64-разрядное целое число (без знака)        |
| `[bigint]`  |                      | См. [структуру BigInteger][bigint]  |
| `[single]`  |                      | Одинарная точность с плавающей запятой  |
| `[float]`   | псевдоним для `[single]` | Одинарная точность с плавающей запятой  |
| `[double]`  |                      | Плавающая точка с двойной точностью  |
| `[decimal]` |                      | 128-разрядная с плавающей запятой           |

> [!NOTE]
> В PowerShell 6,2 были добавлены следующие ускорители типов: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .

## <a name="examples"></a>Примеры

Следующая таблица содержит несколько примеров числовых литералов и перечисляет их тип и значение.

|   Число    |    Type    |    Значение     |
| ----------: | ---------- | -----------: |
|         100 | Int32      |          100 |
|        100u | UInt32     |          100 |
|        100D | Decimal    |          100 |
|        100l | Int64      |          100 |
|       100uL | UInt64     |          100 |
|       100us | UInt16     |          100 |
|       100uy | Byte       |          100 |
|        100y | SByte      |          100 |
|         1e2 | Double     |          100 |
|        1. E2 | Double     |          100 |
|       0x1e2 | Int32      |          482 |
|      0x1e2L | Int64      |          482 |
|      0x1e2D | Int32      |         7725 |
|        482D | Decimal    |          482 |
|       482gb | Int64      | 517543559168 |
|      482ngb | BigInteger | 517543559168 |
|    0x1e2lgb | Int64      | 517543559168 |
|   0b1011011 | Int32      |           91 |
|     0xFFFFs | Int16      |           -1 |
|  0xFFFFFFFF | Int32      |           -1 |
| -0xFFFFFFFF | Int32      |            1 |
| 0xFFFFFFFFu | UInt32     |   4294967295 |

### <a name="working-with-binary-or-hexadecimal-numbers"></a>Работа с двоичными или шестнадцатеричными числами

Чрезмерно большие двоичные или шестнадцатеричные литералы могут возвращать `[bigint]` , а не завершать синтаксический анализ, если только `n` указан суффикс. Биты подписи по-прежнему применяются к даже `[decimal]` диапазонам. Однако:

- Если двоичная строка представляет собой несколько из 8 битов, самый высокий бит рассматривается как бит знака.
- Если шестнадцатеричная строка с длиной, кратной 8, имеет первую цифру, равную 8 или выше, то цифра считается отрицательной.

Указание неподписанного суффикса для двоичных и шестнадцатеричных литералов игнорирует биты знака. Например, `0xFFFFFFFF` возвращает `-1` , но `0xFFFFFFFFu` возвращает значение `[uint]::MaxValue` 4294967295.

В PowerShell 7,1 использование суффикса типа в шестнадцатеричном литерале теперь возвращает значение со знаком этого типа. Например, в PowerShell 7,0 выражение `0xFFFFs` возвращает ошибку, так как положительное значение слишком велико для `[int16]` типа.
PowerShell 7,1 интерпретирует это как `-1` `[int16]` тип.

Предваряющий литерал с помощью `0` будет обходить это и обрабатываться как неподписанные.
Например, введите `0b011111111`. Это может быть необходимо при работе с литералами в `[bigint]` диапазоне, так как `u` `n` суффиксы и не могут быть объединены.

Можно также инвертировать двоичные и шестнадцатеричные литералы с помощью `-` префикса. Это может привести к положительному числу, так как разрешены биты знаков.

Биты знаков принимаются для цифр с суффиксом BigInteger:

- BigInteger-Hex рассматривает старший бит любого литерала с длиной, кратной 8 символам, как бит знака. Длина не включает `0x` префикс или суффиксы.
- Двоичный файл с суффиксом BigInteger принимает биты знаков 96 и 128 символов и каждые 8 символов после.

### <a name="commands-that-look-like-numeric-literals"></a>Команды, которые выглядят как числовые литералы

Любая команда, похожая на допустимый числовой литерал, должна выполняться с помощью оператора Call ( `&` ), в противном случае он интерпретируется как число. Неверно сформированные литералы с допустимым синтаксисом, например `1usgb` , приведут к следующей ошибке:

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

Однако неправильно сформированные литералы с недопустимым синтаксисом `1gbus` будут интерпретироваться как стандартная строка, и ее можно интерпретировать как допустимое имя команды в контекстах, где могут быть вызваны команды.

### <a name="access-properties-and-methods-of-numeric-objects"></a>Доступ к свойствам и методам числовых объектов

Для доступа к элементу числового литерала бывают случаи, когда необходимо заключить литерал в круглые скобки.

- Литерал не имеет десятичной запятой
- Литерал не содержит цифр после десятичной запятой
- У литерала нет суффикса

Например, следующий пример завершается ошибкой:

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

Ниже приведены примеры работы.

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

Первые два примера работают без заключения литерального значения в круглые скобки, так как средство синтаксического анализа PowerShell может определить, где заканчивается числовой литерал, и запустить метод **GetType** .

## <a name="how-powershell-parses-numeric-literals"></a>Как PowerShell анализирует числовые литералы

PowerShell версии 7.0 изменил способ синтаксического анализа числовых литералов, чтобы включить новые функции.

### <a name="parsing-real-numeric-literals"></a>Синтаксический анализ вещественных числовых литералов

Если литерал содержит десятичную запятую или электронную нотацию, то литеральная строка анализирует вещественное число.

- Если десятичный суффикс представлен, то непосредственно в `[decimal]` .
- В противном случае следует выполнить синтаксический анализ `[Double]` и применить множитель к значению. Затем проверьте суффиксы типов и попытайтесь привести их в соответствующий тип.
- Если строка не имеет суффикса типа, выполните синтаксический анализ как `[Double]` .

### <a name="paring-integer-numeric-literals"></a>Геосвязь целые числовые литералы

Литералы целочисленного типа анализируются с помощью следующих шагов:

1. Определение формата системы счисления
   - Для двоичных форматов следует выполнить синтаксический анализ в `[BigInteger]` .
   - Для формата в шестнадцатеричном формате следует выполнить синтаксический анализ `[BigInteger]` с помощью специального касиес, чтобы хранить исходные поведения, когда значение находится в `[int]` `[long]` диапазоне или.
   - Если не задан ни двоичный, ни шестнадцатеричный, то синтаксический анализ обычно является `[BigInteger]` .
2. Примените значение множителя перед попыткой выполнить приведения, чтобы обеспечить правильную проверку границ типов без переполняется.
3. Проверьте суффиксы типов.
   - Проверьте границы типа и попытайтесь выполнить синтаксический анализ этого типа.
   - Если суффикс не используется, значение является ограничивающим и проверяется в следующем порядке, что приводит к первому успешному тестированию, определяющему тип числа.
     - `[int]`
     - `[long]`
     - `[decimal]` (только литералы Base-10)
     - `[double]` (только литералы Base-10)
   - Если значение выходит за пределы `[long]` диапазона для шестнадцатеричных и двоичных чисел, анализ завершается ошибкой.
   - Если значение находится за пределами `[double]` диапазона для базового 10 числа, анализ завершается ошибкой.
   - Более высокие значения должны быть написаны явным образом с помощью `n` суффикса, чтобы проанализировать литерал как `BigInteger` .

### <a name="parsing-large-value-literals"></a>Синтаксический анализ литералов с большими значениями

Ранее более высокие целочисленные значения были проанализированы как Double перед их приведением к любому другому типу. Это приводит к утрате точности в более высоких диапазонах. Пример:

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

Чтобы избежать этой проблемы, необходимо было записывать значения как строки и затем преобразовывать их:

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

В PowerShell 7,0 необходимо использовать `N` суффикс.

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

Кроме того, значения между `[ulong]::MaxValue` и `[decimal]::MaxValue` должны быть отмечены с помощью десятичного суффикса `D` для обеспечения точности. Без суффикса эти значения анализируются `[Double]` с использованием режима реального анализа.

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
