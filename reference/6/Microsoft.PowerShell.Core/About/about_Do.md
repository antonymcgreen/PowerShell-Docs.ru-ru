---
description: Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231513"
---
# <a name="about-do"></a>О Do

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Выполняет список инструкций один или несколько раз, поддерживая условие while или Until.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Ключевое слово do работает с ключевым словом While или ключевым словом Until для выполнения инструкций в блоке скрипта в соответствии с условием. В отличие от связанного цикла while, блок сценария в цикле Do всегда выполняется по крайней мере один раз.

Цикл **do-while** — это множество циклов while. В цикле **do-while** условие вычисляется после выполнения блока script. Как и в цикле while, блок скрипта повторяется, пока условие принимает значение true.

Как и цикл **do-while** , цикл **Do-Until** всегда запускается по крайней мере один раз перед вычислением условия. Однако блок скрипта выполняется только тогда, когда условие имеет значение false.

Ключевые слова *Continue* и *break* управления потоком можно использовать в цикле **do-while** или в цикле **Do-Until** .

### <a name="syntax"></a>Синтаксис

Ниже приведен синтаксис инструкции **do-while** :

```powershell
do {<statement list>} while (<condition>)
```

Ниже приведен синтаксис инструкции **Do-Until** :

```powershell
do {<statement list>} until (<condition>)
```

Список инструкций содержит одну или несколько инструкций, выполняемых при каждом входе или повторении цикла.

Часть условия инструкции разрешается в true или false.

### <a name="example"></a>Пример

Следующий пример инструкции Do подсчитывает количество элементов в массиве до тех пор, пока не достигнет элемента со значением 0.

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

В следующем примере используется ключевое слово Until. Обратите внимание, что оператор «не равно» ( `-ne` ) заменяется оператором «равно» ( `-eq` ).

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

В следующем примере записываются все значения массива, пропуская все значения меньше нуля.

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_While](about_While.md)

[about_Operators](about_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)
