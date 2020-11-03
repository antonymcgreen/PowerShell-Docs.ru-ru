---
description: Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: 578d12461a1e915e699970ca17c6f8220eb7fef1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232473"
---
# <a name="about-join"></a>О соединении

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает, как оператор объединения (-join) объединяет несколько строк в одну строку.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Оператор Join объединяет набор строк в одну строку. Строки добавляются к результирующей строке в том порядке, в котором они отображаются в команде.

### <a name="syntax"></a>Синтаксис

На следующей схеме показан синтаксис оператора Join.

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a>Параметры

String [] — указывает одну или несколько строк для объединения.

Разделитель — указывает один или несколько символов между объединенными строками. Значение по умолчанию — без разделителя ("").

Remarks

Оператор унарного объединения (-Join <строка [] >) имеет более высокий приоритет, чем запятая. В результате при отправке разделенного запятыми списка строк в оператор унарного объединения в оператор Join передается только первая строка (перед первой запятой).

Чтобы использовать оператор унарного объединения, заключите строки в круглые скобки или сохраните строки в переменной, а затем отправьте переменную в соединение.

Пример:

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a>Примеры

Следующая инструкция соединяет три строки:

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

Следующая инструкция соединяет три строки, разделенные пробелом:

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

Следующие инструкции используют разделитель из нескольких символов для объединения трех строк:

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

Следующая инструкция соединяет строки в строке ниже в одной строке. Так как строка Here является одной строкой, строки в этой строке должны быть разделены, прежде чем их можно будет соединить. Этот метод можно использовать для повторного объединения строк в XML-файл, сохраненный в строке ниже:

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Split](about_Split.md)

