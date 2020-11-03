---
description: Описывает, как `continue` инструкция немедленно возвращает поток программы в начало цикла программы, `switch` инструкции или `trap` инструкции.
keywords: powershell,командлет
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 5a33451da91fa0d837b51ded6bae51ce66eb07e4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231729"
---
# <a name="about-continue"></a>Сведения о продолжении

## <a name="short-description"></a>Краткое описание

Описывает, как `continue` инструкция немедленно возвращает поток программы в начало цикла программы, `switch` инструкции или `trap` инструкции.

## <a name="long-description"></a>Подробное описание

`continue`Оператор позволяет выйти из текущего блока управления, но продолжить выполнение, а не выйти полностью. Инструкция поддерживает метки.
Метка — это имя, назначаемое оператору в скрипте.

## <a name="using-continue-in-loops"></a>Использование циклов continue в

Оператор без метки `continue` немедленно возвращает поток программы в начало самого внутреннего цикла, управляемого `for` `foreach` `do` оператором,, или `while` . Текущая итерация цикла завершается, а цикл переходит к следующей итерации.

В следующем примере программный поток возвращается в начало `while` цикла, если `$ctr` переменная равна 5. В результате отображаются все числа от 1 до 10, за исключением 5:

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

При использовании `for` цикла выполнение продолжится в `<Repeat>` операторе, за которым следует `<Condition>` тест. В приведенном ниже примере бесконечный цикл не будет выполняться, поскольку уменьшение `$i` происходит после `continue` ключевого слова.

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a>Использование метки continue в цикле

Оператор с меткой `continue` завершает выполнение итерации и передает управление целевой включающей итерации или `switch` метке оператора.

В следующем примере внутренний `for` конец завершается, когда `$condition` имеет **значение true** , а итерация переходит во второй `for` цикл в `labelB` .

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a>Использование Continue в операторе switch

Оператор без метки в компоненте `continue` `switch` завершает выполнение текущей `switch` итерации и передает управление в начало, `switch` чтобы получить следующий входной элемент.

При наличии одного входного элемента `continue` завершается вся `switch` инструкция.
Если `switch` входные данные являются коллекцией, то `switch` проверяет каждый элемент коллекции. Выполняет `continue` выход из текущей итерации и `switch` переходит к следующему элементу.

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a>Использование Continue в операторе Trap

Если итоговая инструкция, выполненная в теле `trap` оператора, имеет значение `continue` , то перехваченная ошибка пропускается без уведомления, и выполнение переходит к выполнению инструкции, следующей за той причиной, в которой она `trap` возникла.

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a>Не используйте оператор continue вне цикла, переключателя или ловушки

Если `continue` используется вне конструкции, которая напрямую поддерживает эту функцию (циклы, `switch` , `trap` ), PowerShell ищет _Стек вызовов_ для включающей конструкции. Если не удается найти включающую конструкцию, текущее пространство выполнения беззвучно завершается.

Это означает, что функции и скрипты, которые непреднамеренно используют `continue` вне окружающей конструкции, поддерживающей эту функцию, могут случайно завершить свои _вызывающие объекты_ .

Использование `continue` внутри конвейера, такого как `ForEach-Object` блок скрипта, не только завершает работу конвейера, TT потенциально завершает все пространство выполнения.

## <a name="see-also"></a>См. также статью

[about_Break](about_Break.md)

[about_For](about_For.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
