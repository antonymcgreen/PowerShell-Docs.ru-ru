---
description: Описывает операторы, которые соединяют инструкции в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: f8db290b87043451241613358a2f6d4fdf1dc342
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230889"
---
# <a name="about_logical_operators"></a>about_Logical_Operators

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает операторы, которые соединяют инструкции в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Логические операторы PowerShell соединяют выражения и операторы, позволяя использовать одно выражение для проверки нескольких условий.

Например, следующая инструкция использует оператор and и оператор OR для соединения трех условных операторов. Оператор имеет значение true, только если значение $a больше значения $b, а либо $a, либо $b меньше
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

PowerShell поддерживает следующие логические операторы.

|Оператор|Описание                        |Пример                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |Логический оператор AND. TRUE, если оба        |`(1 -eq 1) -and (1 -eq 2)`|
|        |операторы имеют значение TRUE.               |`False`                   |
|`-or`   |Логический оператор OR. TRUE, если либо       |`(1 -eq 1) -or (1 -eq 2)` |
|        |Инструкция имеет значение TRUE.                 |`True`                    |
|`-xor`  |Логическое ИСКЛЮЧАЮЩее или. TRUE, если    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |только одна инструкция имеет значение TRUE         |`False`                   |
|`-not`  |Логическое не. Инвертирует оператор |`-not (1 -eq 1)`          |
|        |Далее.                      |`False`                   |
|`!`     |То же, что `-not`                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 Примечание.

В предыдущих примерах также используется оператор сравнения EQUAL TO `-eq` . Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md). В примерах также используются логические значения целых чисел. Целое число 0 имеет значение FALSE. Все остальные целые числа имеют значение TRUE.

Синтаксис логических операторов выглядит следующим образом:

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

Инструкции, использующие логические операторы, возвращают логические значения (TRUE или FALSE).

Логические операторы PowerShell оценивают только те операторы, которые необходимы для определения истинного значения инструкции. Если левый операнд в операторе, содержащем оператор and, имеет значение FALSE, правый операнд не вычисляется.
Если левый операнд в операторе, содержащем оператор или, имеет значение TRUE, правый операнд не вычисляется. В результате эти инструкции можно использовать точно так же, как при использовании `If` оператора.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Operators](about_Operators.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[about_Comparison_operators](about_Comparison_Operators.md)

[about_If](about_If.md)

