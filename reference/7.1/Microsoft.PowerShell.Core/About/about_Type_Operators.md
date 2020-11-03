---
description: Описывает операторы, работающие с типами Microsoft .NET.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 829dfbbf2cd02c1bf4f1616b49f01f8f079d7d0e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232878"
---
# <a name="about-type-operators"></a>Об операторах типов

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает операторы, работающие с типами Microsoft .NET.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Операторы логического типа ( `-is` и `-isNot` ) сообщают, является ли объект экземпляром указанного типа .NET. `-is`Оператор возвращает значение **true** , если тип соответствует, и значение **false** в противном случае. `-isNot`Оператор возвращает значение **false** , если тип соответствует, и значение **true** в противном случае.

`-as`Оператор пытается преобразовать входной объект в указанный тип .NET. Если он завершается, возвращается преобразованный объект. В противном случае возвращается `$null`. Он не возвращает ошибку.

В следующей таблице перечислены операторы типа в PowerShell.

|Оператор|Описание                |Пример                          |
|--------|---------------------------|---------------------------------|
|`-is`   |Возвращает значение TRUE, если входные данные|`(get-date) -is [DateTime]`      |
|        |является экземпляром класса      |`True`                           |
|        |указанный тип .NET.       |                                 |
|`-isNot`|Возвращает значение TRUE, если входные данные|`(get-date) -isNot [DateTime]`   |
|        |не является экземпляром     |`False`                          |
|        |Тип specified.NET.        |                                 |
|`-as`   |Преобразует входные данные в  |`"5/7/07" -as [DateTime]`        |
|        |указанный тип .NET.       |`Monday, May 7, 2007 12:00:00 AM`|

Синтаксис операторов типа выглядит следующим образом:

```powershell
<input> <operator> [.NET type]
```

Можно также использовать следующий синтаксис:

```powershell
<input> <operator> ".NET type"
```

Тип .NET можно записать в виде имени типа в квадратных скобках или в виде строки, например `[DateTime]` или `"DateTime"` для **System. DateTime**. Если тип не находится в корне пространства имен System, укажите полное имя типа объекта. Можно опустить "System.". Например, чтобы указать **System. Diagnostics. Process** , введите `[System.Diagnostics.Process]` , `[Diagnostics.Process]` или `"Diagnostics.Process"` .

Операторы типа всегда работают с входным объектом в целом. То есть, если входной объект является коллекцией, то это проверяемый тип _коллекции_ , а не типы _элементов_ коллекции.

### <a name="-isisnot-operators"></a>операторы-OR/isNot

Операторы **логического** типа ( `-is` и `-isNot` ) всегда возвращают **логическое** значение, даже если входные данные являются коллекцией объектов.

Если `<input>` — это тип, который совпадает с типом или является _производным_ от типа .NET, `-is` оператор возвращает `$True` .

Например, тип **DirectoryInfo** является производным от типа **филесистеминфо** . Поэтому оба этих примера возвращают **значение true**.

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

`-is`Оператор также может сопоставлять интерфейсы, если объект `<input>` реализует интерфейс в сравнении. В этом примере входными данными является массив. Массивы реализуют интерфейс **System. Collections. IList** .

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a>Оператор-as

`-as`Оператор пытается преобразовать входной объект в указанный тип .NET. Если он завершается, возвращается преобразованный объект. При сбое он возвращает `$null` . Он не возвращает ошибку.

Если `<input>` — это тип, _производный_ от типа .NET, `-as` _передается посредством_ возвращения входного объекта без изменений. Например, тип **DirectoryInfo** является производным от типа **филесистеминфо** . Таким образом, тип объекта не изменяется в следующем примере:

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a>Преобразование типа DateTime зависит от языка и региональных параметров

В отличие от приведения типов, преобразование в `[DateTime]` тип с помощью `-as` оператора работает только со строками, отформатированными в соответствии с правилами текущего языка и региональных параметров.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

Чтобы найти тип .NET объекта, используйте `Get-Member` командлет. Или используйте метод **GetType** всех объектов вместе со свойством **FullName** этого метода. Например, следующая инструкция возвращает тип возвращаемого значения `Get-Culture` команды:

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a>Примеры

В следующих примерах показаны некоторые способы использования операторов типов:

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

В следующем примере показано, что если входные данные представляют собой коллекцию объектов, соответствующий тип является типом .NET коллекции, а не типом отдельных объектов в коллекции.

В этом примере несмотря на то, `Get-Culture` что `Get-UICulture` командлеты и возвращают объекты **System. Globalization. CultureInfo** , коллекция этих объектов является массивом System. Object.

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

В следующих примерах показано, как использовать `-as` оператор.

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

В следующем примере показано, что если `-as` оператор не может преобразовать входной объект в тип .NET, возвращается значение `$null` .

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Operators](about_Operators.md)
