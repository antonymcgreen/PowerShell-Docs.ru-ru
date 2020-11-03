---
description: Описывает команду языка, которую можно использовать для выполнения списков инструкций на основе результатов одного или нескольких условных тестов.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: f5bda1b3530c104361dba12de029219a5dd0db60
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231794"
---
# <a name="about-if"></a>О программе

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает команду языка, которую можно использовать для выполнения списков инструкций на основе результатов одного или нескольких условных тестов.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Можно использовать `If` инструкцию для выполнения блоков кода, если заданная условная проверка имеет значение true. Можно также указать один или несколько дополнительных условных тестов для выполнения, если все предыдущие тесты имеют значение false. Наконец, можно указать дополнительный блок кода, который будет выполняться, если ни одна из предыдущих условных тестов не возвращает значение true.

### <a name="syntax"></a>Синтаксис

В следующем примере показан `If` синтаксис инструкции:

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

При выполнении `If` инструкции PowerShell вычисляет `<test1>` условное выражение как true или false. Если `<test1>` имеет значение true, `<statement list 1>` выполняется, а PowerShell завершает выполнение `If` инструкции. Если `<test1>` значение равно false, то PowerShell оценивает условие, заданное `<test2>` условным оператором.

Если `<test2>` имеет значение true, `<statement list 2>` выполняется, а PowerShell завершает выполнение `If` инструкции. Если оба `<test1>` `<test2>` аргумента и имеют значение false, `<statement list 3`> блок кода выполняется, а PowerShell завершает инструкцию if.

Можно использовать несколько операторов ElseIf для сцепления последовательности условных тестов. Таким образом, каждый тест выполняется только в том случае, если все предыдущие тесты имеют значение false.
Если необходимо создать `If` инструкцию, содержащую множество операторов ElseIf, рассмотрите возможность использования оператора switch.

Примеры:

Простейшая `If` инструкция содержит одну команду и не содержит ни операторов ElseIf, ни инструкций else. В следующем примере показана простейшая форма `If` оператора:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

В этом примере, если переменная $a больше 2, условие принимает значение true и выполняется список инструкций. Однако если $a меньше или равно 2 или не является существующей переменной, `If` инструкция не отображает сообщение.

При добавлении инструкции else отображается сообщение, если $a меньше или равно 2. Как показано в следующем примере:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

Для дальнейшего уточнения этого примера можно использовать Оператор ElseIf для вывода сообщения, если значение $a равно 2. Как показано в следующем примере:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

### <a name="using-the-ternary-operator-syntax"></a>Использование синтаксиса оператора ternary

В PowerShell 7,0 появился новый синтаксис с помощью оператора ternary. Он соответствует синтаксису оператора C# ternary:

```Syntax
<condition> ? <if-true> : <if-false>
```

Оператор ternary ведет себя так же, как и упрощенная `if-else` инструкция. `<condition>`Выражение вычисляется, и результат преобразуется в логическое значение, чтобы определить, какую ветвь следует вычислить следующим образом:

- Выражение `<if-true>` выполняется, если выражение `<condition>` имеет значение true.
- Выражение `<if-false>` выполняется, если выражение `<condition>` имеет значение false.

Пример:

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

В этом примере `$message` при возврате возвращается значение «Path Exists» `Test-Path` `$true` . При `Test-Path` возврате `$false` значение `$message` равно "путь не найден".

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

В этом примере, если служба запущена, она останавливается и, если ее состояние не **выполняется** , запускается.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Switch](about_Switch.md)
