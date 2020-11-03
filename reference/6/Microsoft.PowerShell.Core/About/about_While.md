---
description: Описывает языковую инструкцию, которую можно использовать для выполнения блока команд на основе результатов условного теста.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 0adc435eeba6b07e1f16aec5dd1328ddd80c4612
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231186"
---
# <a name="about-while"></a>О программе while

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает языковую инструкцию, которую можно использовать для выполнения блока команд на основе результатов условного теста.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Оператор while (также называемый циклом while) — это языковая конструкция для создания цикла, запускающего команды в блоке команд, если условный тест имеет значение true. Оператор while проще создавать, чем оператор for, поскольку его синтаксис менее сложен. Кроме того, он является более гибким, чем оператор foreach, так как в инструкции While указывается условный тест, определяющий, сколько раз выполняется цикл.

Ниже показан синтаксис инструкции While:

```powershell
while (<condition>){<statement list>}
```

При выполнении инструкции While PowerShell вычисляет `<condition>` раздел инструкции перед входом в `<statement list>` раздел. Часть условия инструкции разрешается как true или false. Пока условие остается истинным, PowerShell повторно выполнят этот `<statement list>` раздел.

`<statement list>`Раздел инструкции содержит одну или несколько команд, которые выполняются каждый раз при входе или повторении цикла.

Например, следующая инструкция while отображает числа от 1 до 3, если переменная $val не была создана или если $val переменная была создана и инициализирована значением 0.

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

В этом примере условие ($val не равно 3) имеет значение true, когда $val \= 0, 1, 2. Каждый раз с помощью цикла $val увеличивается на 1 с помощью \+ \+ оператора унарного инкремента ($Val \+ \+ ). Последний раз в цикле, $val \= 3. Если $val равно 3, то оператор Condition принимает значение false, а цикл завершается.

Чтобы удобно написать эту команду в командной строке PowerShell, введите ее следующим образом:

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

Обратите внимание, что точка с запятой отделяет первую команду, которая добавляет 1 к $val из второй команды, которая записывает значение $val в консоль.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Do](about_Do.md)

[about_Foreach](about_Foreach.md)

[about_For](about_For.md)

[about_Language_Keywords](about_Language_Keywords.md)
