---
description: Перечисляет операторы PowerShell в порядке очередности.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 8f0f69f2328343b9655ebd0d7515a469565ff5f5
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483112"
---
# <a name="about-operator-precedence"></a>О приоритете операторов

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Перечисляет операторы PowerShell в порядке очередности.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Операторы PowerShell позволяют создавать простые, но мощные выражения. В этом разделе перечислены операторы в порядке очередности. Порядок очередности — это порядок, в котором PowerShell вычисляет операторы, если в одном выражении отображается несколько операторов.

Если у операторов одинаковый приоритет, PowerShell вычисляет их слева направо, как они появляются в выражении. Исключениями являются операторы присваивания, операторы CAST и операторы отрицания ( `!` , `-not` , `-bnot` ), которые вычисляются справа налево.

Можно использовать вложения, например круглые скобки, для переопределения стандартного порядка приоритетов и принудительного выполнения PowerShell для вычисления вложенной части выражения перед незамкнутой частью.

В следующем списке Операторы перечисляются в том порядке, в котором они оцениваются. Операторы на одной строке или в одной группе имеют одинаковый приоритет.

В столбце Оператор перечислены операторы. Ссылочный столбец содержит раздел справки PowerShell, в котором описывается оператор. Чтобы отобразить раздел, введите `get-help <topic-name>` .

|         OPERATOR         |           ISREFERENCE            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | [about_Operators][]            |
| `. ?.` (доступ к членам)   | [about_Operators][]            |
| `::` статически            | [about_Operators][]            |
| `[0] ?[0]` (Оператор Index) | [about_Operators][]         |
| `[int]` (операторы CAST) | [about_Operators][]            |
| `-split` унар         | [about_Split][]                |
| `-join` унар          | [about_Join][]                 |
| `,` (оператор запятой)     | [about_Operators][]            |
| `++ --`                  | [about_Assignment_Operators][] |
| `! -not`                 | [about_Logical_Operators][]    |
| `..` (оператор Range)    | [about_Operators][]            |
| `-f` (оператор Format)   | [about_Operators][]            |
| `-` (унарный/отрицательный)     | [about_Arithmetic_Operators][] |
| `* / %`                  | [about_Arithmetic_Operators][] |
| `+ -`                    | [about_Arithmetic_Operators][] |

Следующая группа операторов имеет одинаковый приоритет. С учетом регистра и без учета регистра одни и те же варианты имеют одинаковый приоритет.

|         OPERATOR          |           ISREFERENCE            |
| ------------------------- | ------------------------------ |
| `-split` двоичный         | [about_Split][]                |
| `-join` двоичный          | [about_Join][]                 |
| `-is -isnot -as`          | [about_Type_Operators][]       |
| `-eq -ne -gt -gt -lt -le` | [about_Comparison_Operators][] |
| `-like -notlike`          | [about_Comparison_Operators][] |
| `-match -notmatch`        | [about_Comparison_Operators][] |
| `-in -notIn`              | [about_Comparison_Operators][] |
| `-contains -notContains`  | [about_Comparison_Operators][] |
| `-replace`                | [about_Comparison_Operators][] |

Список возобновляется с помощью следующих операторов в порядке очередности:

|                OPERATOR                 |           ISREFERENCE            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | [about_Arithmetic_Operators][] |
| `-and -or -xor`                         | [about_Logical_Operators][]    |

Следующие элементы не являются истинными операторами. Они являются частью синтаксиса команд PowerShell, а не синтаксиса выражений. Назначение всегда является последним выполняемым действием.

|                SYNTAX                   |           ISREFERENCE            |
| --------------------------------------- | ------------------------------ |
| `.` (точка-источник)                        | [about_Operators][]            |
| `&` обращение                              | [about_Operators][]            |
| `? <if-true> : <if-false>` (Оператор Ternary) | [about_Operators][]      |
| `??` (оператор, сокрывающийся со значением NULL)            | [about_Operators][]            |
| <code>&#124;</code> (оператор конвейера) | [about_Operators][]            |
| `> >> 2> 2>> 2>&1`                      | [about_Redirection][]          |
| <code>&& &#124;&#124;</code> (операторы цепочки конвейеров) | [about_Operators][] |
| `= += -= *= /= %= ??=`                  | [about_Assignment_Operators][] |

## <a name="examples"></a>Примеры

Следующие две команды показывают арифметические операторы и результат использования круглых скобок для принудительного вычисления в PowerShell заключенной в нем части выражения.

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

В следующем примере выполняется получение текстовых файлов только для чтения из локального каталога и их сохранение в `$read_only` переменной.

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

Это эквивалентно следующему примеру.

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

Так как оператор конвейера ( `|` ) имеет более высокий приоритет, чем оператор присваивания ( `=` ), файлы, получаемые `Get-ChildItem` командлетом, отправляются в `Where-Object` командлет для фильтрации до того, как они будут назначены `$read_only` переменной.

В следующем примере показано, что оператор index имеет приоритет над оператором Cast.

Это выражение создает массив из трех строк. Затем он использует оператор index со значением 0 для выбора первого объекта в массиве, который является первой строкой. Наконец, выбранный объект приводится в виде строки. В этом случае приведение не оказывает никакого влияния.

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

Это выражение использует круглые скобки, чтобы принудительно выполнить операцию приведения перед выбором индекса. В результате весь массив приводится к строковому типу (Single). Затем оператор index выбирает первый элемент в массиве строк, который является первым символом.

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

В следующем примере, поскольку оператор « `-gt` больше чем» имеет более высокий приоритет, чем `-and` оператор (логический и), результатом выражения будет false.

```powershell
PS> 2 -gt 4 -and 1
False
```

Он эквивалентен следующему выражению.

```powershell
PS> (2 -gt 4) -and 1
False
```

Если оператор-and имеет более высокий приоритет, ответ будет равен TRUE.

```powershell
PS> 2 -gt (4 -and 1)
True
```

Однако в этом примере демонстрируется важный принцип управления приоритетом операторов. Если выражение трудно интерпретировать, используйте круглые скобки, чтобы принудительно применить порядок вычисления, даже если он вызывает приоритет оператора по умолчанию. Круглые скобки делают ваши намерения понятными для тех, кто читает и обслуживает ваши сценарии.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Operators][]

[about_Assignment_Operators][]

[about_Comparison_Operators][]

[about_Arithmetic_Operators][]

[about_Join][]

[about_Redirection][]

[about_Scopes][]

[about_Split][]

[about_Type_Operators][]

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md
