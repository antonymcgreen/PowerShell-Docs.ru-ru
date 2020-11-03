---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: c72cde8e626993726ae1a52206c88e20c3a7c588
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "93233281"
---
# Compare-Object

## Краткий обзор
Сравнивает два набора объектов.

## Синтаксис

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## Описание

`Compare-Object`Командлет сравнивает два набора объектов. Одним набором объектов является **ссылка** , а другой набор объектов — это **разница**.

`Compare-Object` проверяет наличие доступных методов сравнения целого объекта. Если не удается найти подходящий метод, он вызывает методы **ToString ()** входных объектов и сравнивает результаты строки. Можно указать одно или несколько свойств, которые будут использоваться для сравнения. При указании свойств командлет сравнивает значения только этих свойств.

Результат сравнения указывает, отображается ли значение свойства только в объекте **Reference** ( `<=` ) или только в объекте **Difference** ( `=>` ). Если используется параметр **инклудикуал** , ( `==` ) указывает, что значение находится в обоих объектах.

Если **ссылка** или объекты **различий** имеют значение null ( `$null` ), `Compare-Object` создает завершающую ошибку.

В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода. Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## Примеры

### Пример 1. Сравнение содержимого двух текстовых файлов

В этом примере сравнивается содержимое двух текстовых файлов. В примере используются два текстовых файла, каждый из которых имеет значение в отдельной строке.

- `Testfile1.txt` содержит значения: Dog, squirrel и высоты.
- `Testfile2.txt` содержит значения: Cat, высоты и Ракун.

В выходных данных отображаются только те строки, которые отличаются от файлов. `Testfile1.txt` Объект **Reference** ( `<=` ) и `Testfile2.txt` является объектом **Difference** ( `=>` ). Строки с содержимым, которое отображается в обоих файлах, не отображаются.

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### Пример 2. сравнение каждой строки содержимого и исключение различий

В этом примере используются параметры **инклудикуал** и **ексклудедифферент** для сравнения каждой строки содержимого в двух текстовых файлах.

Поскольку команда использует параметр **ексклудедифферент** , выходные данные содержат только строки, содержащиеся в обоих файлах, как показано в **сидеиндикатор** ( `==` ).

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### Пример 3. Отображение разницы при использовании параметра PassThru

Обычно `Compare-Object` возвращает тип **PSCustomObject** со следующими свойствами:

- Сравниваемый объект **InputObject**
- Свойство **сидеиндикатор** , показывающее входной объект, которому принадлежат выходные данные

При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**. **Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.

В следующих примерах показаны различные типы выходных данных.

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

При использовании функции **PassThru** возвращается исходный тип объекта ( **System. Boolean** ). Обратите внимание, что в выходных данных, отображаемых в формате по умолчанию для объектов **System. Boolean** , не отображалось свойство **сидеиндикатор** . Однако возвращенный объект **System. Boolean** имеет добавленный **NoteProperty**.

### Пример 4. Сравнение двух простых объектов с помощью свойств

В этом примере мы сравниваем две различные строки, имеющие одинаковую длину.

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### Пример 5. Сравнение сложных объектов с помощью свойств

В этом примере показано поведение при сравнении сложных объектов. В этом примере мы сохраняем два различных объекта процесса для разных экземпляров PowerShell. Обе переменные содержат объекты Process с одинаковыми именами. При сравнении объектов без указания параметра **Свойства** командлет считает объекты одинаковыми. Обратите внимание, что значение **InputObject** совпадает с результатом метода **ToString ()** . Поскольку класс **System. Diagnostics. Process** не имеет интерфейса **IComparable** , командлет преобразует объекты в строки, а затем сравнивает результаты.

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

При указании сравниваемых свойств командлет показывает различия.

### Пример 6. Сравнение сложных объектов, реализующих интерфейс IComparable

Если объект реализует интерфейс **IComparable** , командлет ищет способы сравнения объектов. Если объекты имеют разные типы, то объект **различий** преобразуется в тип **референцеобжект** , который затем сравнивается.

В этом примере выполняется сравнение строки с объектом **TimeSpan** . В первом случае строка преобразуется в **интервал** времени, поэтому объекты равны.

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

Во втором случае **TimeSpan** преобразуется в строку, чтобы объект отличался.

## Параметры

### -CaseSensitive

Указывает, что сравнение выполняется с учетом регистра.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Указывает язык, используемый для сравнения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Дифференцеобжект

Указывает объекты, сравниваемые с **ссылочными** объектами.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Ексклудедифферент

Указывает, что этот командлет отображает только характеристики сравниваемых объектов, которые равны. Различия между объектами отбрасываются.

Используйте **ексклудедифферент** с **инклудикуал** , чтобы отобразить только те строки, которые соответствуют объектам **ссылки** и **различий** .

Если **ексклудедифферент** указан без **инклудикуал** , выходные данные отсутствуют.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инклудикуал

**Инклудикуал** отображает совпадения между объектами **ссылки** и **различий** .

По умолчанию выходные данные также содержат различия между объектами **ссылок** и **различий** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

При использовании параметра **PassThru** `Compare-Object` опускает оболочку **PSCustomObject** вокруг сравниваемых объектов и возвращает отличающиеся объекты без изменений.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Указывает массив свойств **ссылки** и сравниваемых объектов. **difference**

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Выражение — `<string>` или `<script block>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Референцеобжект

Задает массив объектов, используемых в качестве ссылки для сравнения.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Синквиндов

Указывает количество смежных объектов, `Compare-Object` проверяемых при поиске совпадения в коллекции объектов. `Compare-Object` проверяет смежные объекты, если он не находит объект в том же положении в коллекции. Значение по умолчанию — `[Int32]::MaxValue` , то есть `Compare-Object` проверяет всю коллекцию объектов.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Вы можете отправить объект по конвейеру в параметр **дифференцеобжект** .

## Выходные данные

### Нет

Если **ссылочный** объект и объект **различий** одинаковы, выходные данные отсутствуют, если не используется параметр **инклудикуал** .

### System. Management. Automation. PSCustomObject

Если объекты отличаются, заключает различные `Compare-Object` объекты в `PSCustomObject` оболочке со свойством **сидеиндикатор** для ссылки на различия.

При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**. **Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.

## Примечания

При использовании параметра **PassThru** выходные данные, отображаемые в консоли, могут не включать свойство **сидеиндикатор** . Представление формата по умолчанию для типа выходных данных объекта не `Compare-Object` включает свойство **сидеиндикатор** . Дополнительные сведения см. в [примере 3](#ex3) в этой статье.

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object;](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
