---
description: Описывает инструкцию, которую можно использовать для немедленного выхода из операторов,,,, `foreach` `for` `while` `do` `switch` или `trap` .
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 3c418f5bae11f957880c8b53ee0bcf2fb44515ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604498"
---
# <a name="about-break"></a>О прерывании

## <a name="short-description"></a>Краткое описание

Описывает инструкцию, которую можно использовать для немедленного выхода из операторов,,,, `foreach` `for` `while` `do` `switch` или `trap` .

## <a name="long-description"></a>Подробное описание

`break`Оператор предоставляет способ выхода из текущего управляющего блока.
Выполнение продолжится в следующей инструкции после блока управления. Инструкция поддерживает метки. Метка — это имя, назначаемое оператору в скрипте.

## <a name="using-break-in-loops"></a>Использование циклов Break

Если `break` оператор присутствует в цикле, таком как `foreach` цикл,, `for` `do` или `while` , PowerShell немедленно завершает работу цикла.

`break`Оператор может включать метку, которая позволяет выйти из встраиваемых циклов. Метка может указывать любое ключевое слово Loop, такое как `foreach` , `for` или `while` , в скрипте.

В следующем примере показано, как использовать `break` оператор для выхода из `for` оператора:

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

В этом примере `break` оператор завершает `for` цикл, если `$i` переменная равна 1. Несмотря на то `for` , что оператор принимает **значение true** до тех пор `$i` , пока не будет больше 10, PowerShell достигают оператора break при первом `for` запуске цикла.

Чаще используется `break` оператор в цикле, где должно выполняться внутреннее условие. Рассмотрим следующий `foreach` пример инструкции:

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

В этом примере `foreach` оператор выполняет итерацию `$varB` массива. `if`Оператор возвращает значение false, если первые два раза выполняются в цикле, а переменная `$i` увеличивается на 1. Третье время выполнения цикла `$i` равно 2, а `$val` переменная равна 30. На этом этапе `break` выполняется инструкция, и `foreach` цикл завершает работу.

### <a name="using-a-labeled-break-in-a-loop"></a>Использование приостановки с меткой в цикле

`break`Оператор может включать метку. При использовании `break` ключевого слова с меткой PowerShell выходит из цикла с меткой, а не выходит из текущего цикла.
Метка — это двоеточие, за которым следует присвоенное имя. Метка должна быть первой лексемой в операторе, а за ней должно следовать ключевое слово Loop, например `while` .

`break` Перемещает выполнение из цикла с меткой. Во встроенных циклах результат отличается от результата `break` ключевого слова при его использовании. В этом примере имеется `while` оператор с `for` оператором:

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

Если условие 2 принимает **значение true**, выполнение сценария пропускается до оператора после помеченного цикла. В этом примере выполнение начинается с оператора `$a = $c` .

Можно вложить много циклов с метками, как показано в следующем примере.

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

Если `$b` переменная имеет значение true, выполнение сценария возобновляется после цикла, помеченного как "Red". Если значение `$c` переменной равно true, выполнение элемента управления скрипта возобновляется после цикла, помеченного как "желтый".

Если значение `$a` переменной равно true, выполнение возобновляется после самого внутреннего цикла. Метка не требуется.

PowerShell не ограничивает, насколько далеко могут возобновить выполнение меток. Метка может даже передавать управление между скриптом и границами вызовов функций.

## <a name="using-break-in-a-switch-statement"></a>Использование оператора break в операторе switch

В `switch` конструкции `break` заставляет PowerShell выйти из `switch` блока кода.

`break`Ключевое слово используется для выхода из `switch` конструкции. Например, следующая `switch` инструкция использует `break` инструкции для проверки наиболее конкретного условия:

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

В этом примере `$var` переменная создается и инициализируется строковым значением `word2` . `switch`Инструкция использует класс **Regex** для сопоставления значения переменной сначала с термином `word2` . Так как значение переменной и первый тест в `switch` операторе совпадают, первый блок кода в `switch` операторе выполняется.

Когда PowerShell достигает первого `break` оператора, `switch` инструкция завершается. Если четыре `break` инструкции удаляются из примера, выполняются все четыре условия. В этом примере используется `break` оператор для вывода результатов при выполнении наиболее конкретного условия.

## <a name="using-break-in-a-trap-statement"></a>Использование функции break в операторе Trap

Если последняя инструкция, выполняемая в теле `trap` инструкции, имеет значение `break` , то объект Error подавляется и исключение создается повторно.

В следующем примере создается исключение **DivideByZeroException** , перехваченное с помощью `trap` инструкции.

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Обратите внимание, что выполнение останавливается при возникновении исключения. `After loop`Никогда не достигается.
Исключение создается повторно после `trap` выполнения.

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a>Не используйте Break вне цикла, переключателя или ловушки

Если `break` используется вне конструкции, которая напрямую поддерживает эту функцию (циклы, `switch` , `trap` ), PowerShell ищет _Стек вызовов_ для включающей конструкции. Если не удается найти включающую конструкцию, текущее пространство выполнения беззвучно завершается.

Это означает, что функции и скрипты, которые случайно используют `break` вне включающей конструкции, поддерживающей эту функцию, могут случайно завершить свои _вызывающие объекты_.

Использование `break` внутри конвейера `break` , такого как `ForEach-Object` блок скрипта, не только завершает работу конвейера, но и может привести к завершению всего пространства выполнения.

## <a name="see-also"></a>См. также

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Continue](about_Continue.md)

[about_For](about_For.md)

[about_Foreach](about_Foreach.md)

[about_Switch](about_Switch.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)

[about_While](about_While.md)
