---
description: Описывает создание, использование и сортировку хэш-таблиц в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: 3becc982ac49868dca3b0c7ca20707307298547d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387079"
---
# <a name="about-hash-tables"></a>О хэш-таблицах

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает создание, использование и сортировку хэш-таблиц в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Хэш-таблица, также называемая словарем или ассоциативным массивом, представляет собой компактную структуру данных, в которой хранится одна или несколько пар "ключ-значение". Например, хэш-таблица может содержать ряд IP-адресов и имен компьютеров, где IP-адреса являются ключами, а имена компьютеров — значениями, и наоборот.

В PowerShell каждая хэш-таблица является объектом Hashtable (System. Collections. Hashtable). В PowerShell можно использовать свойства и методы объектов Hashtable.

Начиная с PowerShell 3,0, можно использовать атрибут [ordered] для создания упорядоченного словаря (System. Collections. специализированные. Ордереддиктионари) в PowerShell.

Упорядоченные словари отличаются от хэш-таблиц тем, что ключи всегда отображаются в порядке их перечисления. Порядок ключей в хэш-таблице не определен.

Ключи и значение в хэш-таблицах также являются объектами .NET. Чаще всего это строки или целые числа, но они могут иметь любой тип объекта. Также можно создать вложенные хэш-таблицы, в которых значение ключа является другой хэш-таблицей.

Хэш-таблицы часто используются, так как они очень эффективны для поиска и извлечения данных. Хэш-таблицы можно использовать для хранения списков и создания вычисляемых свойств в PowerShell. И PowerShell имеет командлет ConvertFrom-StringData, который преобразует строки в хэш-таблицу.

### <a name="syntax"></a>Синтаксис

Синтаксис хэш-таблицы выглядит следующим образом:

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

Синтаксис упорядоченного словаря выглядит следующим образом:

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

Атрибут [ordered] появился в PowerShell 3,0.

### <a name="creating-hash-tables"></a>Создание хэш-таблиц

Чтобы создать хэш-таблицу, следуйте приведенным ниже рекомендациям.

- Начните хэш-таблицу со знака @.
- Заключите хэш-таблицу в фигурные скобки ( {} ).
- Введите одну или несколько пар "ключ-значение" для содержимого хэш-таблицы.
- Используйте знак равенства (=) для отделения каждого ключа от его значения.
- Используйте точку с запятой (;) или разрыв строки для разделения пар «ключ-значение».
- Ключ, содержащий пробелы, должен быть заключен в кавычки. Значения должны быть допустимыми выражениями PowerShell. Строки должны быть заключены в кавычки, даже если они не содержат пробелов.
- Чтобы управлять хэш-таблицей, сохраните ее в переменной.
- При назначении упорядоченной хэш-таблицы переменной поместите атрибут [ordered] перед символом "@". Если поместить его перед именем переменной, команда завершится ошибкой.

Чтобы создать пустую хэш-таблицу в значении $hash, введите:

```powershell
$hash = @{}
```

При создании хэш-таблицы можно также добавить в нее ключи и значения. Например, следующая инструкция создает хэш-таблицу с тремя ключами.

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a>Создание упорядоченных словарей

Можно создать упорядоченный словарь, добавив объект типа Ордереддиктионари, но самый простой способ создать упорядоченный словарь — использовать атрибут [ordered].

Атрибут [ordered] представлен в PowerShell 3,0.

Поместите атрибут непосредственно перед символом "@".

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

Упорядоченные словари можно использовать так же, как и хэш-таблицы.
Любой из этих типов можно использовать в качестве значения параметров, которые принимают хэш-таблицу или словарь (iDictionary).

Нельзя использовать атрибут [ordered] для преобразования или приведения хэш-таблицы. Если поместить упорядоченный атрибут перед именем переменной, команда завершится со следующим сообщением об ошибке.

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

Чтобы исправить выражение, переместите атрибут [ordered].

```powershell
PS C:\> $hash = [ordered]@{}
```

Можно привести упорядоченный словарь к хэш-таблице, но нельзя восстановить упорядоченный атрибут, даже если очистить переменную и ввести новые значения. Для повторного создания заказа необходимо удалить и повторно создать переменную.

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a>Отображение хэш-таблиц

Чтобы отобразить хэш-таблицу, сохраненную в переменной, введите имя переменной.
По умолчанию хэш-таблицы отображаются в виде таблицы с одним столбцом для ключей и одной для значений.

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

Хэш-таблицы имеют свойства "ключи" и "значения". Используйте точечную нотацию для вывода всех ключей или всех значений.

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

Каждое имя ключа является также свойством хэш-таблицы, а его значением является значение свойства Key-Name. Используйте следующий формат для вывода значений свойств.

```powershell
$hashtable.<key>
<value>
```

Пример:

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

Если имя ключа конфликтует с одним из имен свойств типа HashTable, можно использовать `PSBase` для доступа к этим свойствам. Например, если имя ключа равно и необходимо `keys` вернуть коллекцию ключей, используйте следующий синтаксис:

```powershell
$hashtable.PSBase.Keys
```

Хэш-таблицы имеют свойство Count, которое указывает количество пар "ключ-значение" в хэш-таблице.

```powershell
C:\PS> $hash.count
3
```

Таблицы хэш-таблиц не являются массивами, поэтому нельзя использовать целое число в качестве индекса в хэш-таблице, но можно использовать имя ключа для индексации в хэш-таблице.
Если ключ является строковым значением, заключите имя ключа в кавычки.

Пример:

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a>Добавление и удаление ключей и значений

Чтобы добавить ключи и значения в хэш-таблицу, используйте следующий формат команды:

```powershell
$hash["<key>"] = "<value>"
```

Например, чтобы добавить в хэш-таблицу ключ "Time" со значением "Now", используйте следующий формат инструкции.

```powershell
$hash["Time"] = "Now"
```

Также можно добавить ключи и значения в хэш-таблицу с помощью метода Add объекта System. Collections. Hashtable. Метод Add имеет следующий синтаксис:

```powershell
Add(Key, Value)
```

Например, чтобы добавить в хэш-таблицу ключ "Time" со значением "Now", используйте следующий формат инструкции.

```powershell
$hash.Add("Time", "Now")
```

Кроме того, можно добавить ключи и значения в хэш-таблицу с помощью оператора сложения (+), чтобы добавить хэш-таблицу в существующую хэш-таблицу. Например, следующая инструкция добавляет ключ "Time" со значением "Now" в хэш-таблицу в переменной $hash.

```powershell
$hash = $hash + @{Time="Now"}
```

Можно также добавлять значения, хранящиеся в переменных.

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

Оператор вычитания нельзя использовать для удаления пары "ключ-значение" из хэш-таблицы, но можно использовать метод Remove объекта Hashtable. Метод Remove принимает ключ в качестве значения.

Метод Remove имеет следующий синтаксис:

```
Remove(Key)
```

Например, чтобы удалить пару "время = теперь ключ — значение" из хэш-таблицы в значении переменной $hash, введите:

```powershell
$hash.Remove("Time")
```

Вы можете использовать все свойства и методы объектов Hashtable в PowerShell, включая Contains, Clear, Clone и CopyTo. Дополнительные сведения об объектах Hashtable см. в разделе [System. Collections. Hashtable](/dotnet/api/system.collections.hashtable).

### <a name="object-types-in-hashtables"></a>Типы объектов в хэш-таблицах

Ключи и значения в хэш-таблице могут иметь любой тип объекта .NET, а одна хэш-таблица может иметь ключи и значения нескольких типов.

Следующая инструкция создает хэш-таблицу строк имени процесса и значения объекта Process и сохраняет их в `$p` переменной.

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

Можно отобразить хэш-таблицу в `$p` и использовать свойства Key-Name для вывода значений.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

Ключи в хэш-таблице могут также иметь любой тип .NET. Следующая инструкция добавляет пару "ключ-значение" в хэш-таблицу в `$p` переменной. Ключ — это объект службы, представляющий службу WinRM, а значение — Текущее состояние службы.

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

Вы можете отобразить новую пару "ключ-значение" и получить к ней доступ с помощью тех же методов, которые используются для других пар в хэш-таблице.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

Ключи и значения в хэш-таблице также могут быть объектами Hashtable. Следующая инструкция добавляет пару "ключ-значение" в хэш-таблицу в `$p` переменной, в которой ключ является строкой, Hash2, а значение — хэш-таблицей с тремя парами "ключ-значение".

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

Вы можете отображать новые значения и получать к ним доступ с помощью тех же методов.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a>Сортировка ключей и значений

Элементы в хэш-таблице неупорядочены по отдельности. Пары "ключ-значение" могут отображаться в отдельном порядке при каждом их отображении.

Хотя хэш-таблицу нельзя отсортировать, можно использовать метод GetEnumerator хэш-таблиц для перечисления ключей и значений, а затем использовать командлет Sort-Object для сортировки перечисленных значений для вывода.

Например, следующие команды перечисляют ключи и значения в хэш-таблице в `$p` переменной, а затем сортируют эти ключи в алфавитном порядке.

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

Следующая команда использует ту же процедуру для сортировки хэш-значений в порядке убывания.

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a>Создание объектов из хэш-таблиц

Начиная с PowerShell 3,0, можно создать объект из хэш-таблицы свойств и значений свойств.

Синтаксис выглядит следующим образом:

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Этот метод работает только для классов, имеющих конструктор со значением NULL, то есть конструктор, не имеющий параметров. Свойства объекта должны быть общедоступными и настраиваемыми.

Дополнительные сведения см. в разделе [about_Object_Creation](about_Object_Creation.md).

### <a name="convertfrom-stringdata"></a>ConvertFrom-StringData

`ConvertFrom-StringData`Командлет преобразует строку или строку в паре "ключ-значение" в хэш-таблицу. Командлет можно безопасно использовать `ConvertFrom-StringData` в разделе данных скрипта. его можно использовать с `Import-LocalizedData` командлетом для вывода сообщений пользователя в языке и региональных параметрах пользовательского интерфейса текущего пользователя.

Здесь строки особенно полезны, если значения в хэш-таблице содержат кавычки. Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).

В следующем примере показано, как создать строку с сообщениями пользователя в предыдущем примере и как использовать `ConvertFrom-StringData` для преобразования их из строки в хэш-таблицу.

Следующая команда создает строку "ключ-значение", а затем сохраняет ее в \$ строковой переменной.

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

Эта команда использует командлет ConvertFrom-StringData для преобразования строки Here в хэш-таблицу.

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Arrays](about_Arrays.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[System.Collections.Hashtable](/dotnet/api/system.collections.hashtable)
