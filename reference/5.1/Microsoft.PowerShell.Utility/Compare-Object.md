---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 994bed44d9632ad836f204ceafd6c7493591b91a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "93233265"
---
# <span data-ttu-id="2df9f-103">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-103">Compare-Object</span></span>

## <span data-ttu-id="2df9f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2df9f-104">Synopsis</span></span>
<span data-ttu-id="2df9f-105">Сравнивает два набора объектов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-105">Compares two sets of objects.</span></span>

## <span data-ttu-id="2df9f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2df9f-106">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="2df9f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2df9f-107">Description</span></span>

<span data-ttu-id="2df9f-108">`Compare-Object`Командлет сравнивает два набора объектов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-108">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="2df9f-109">Одним набором объектов является **ссылка** , а другой набор объектов — это **разница**.</span><span class="sxs-lookup"><span data-stu-id="2df9f-109">One set of objects is the **reference** , and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="2df9f-110">`Compare-Object` проверяет наличие доступных методов сравнения целого объекта.</span><span class="sxs-lookup"><span data-stu-id="2df9f-110">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="2df9f-111">Если не удается найти подходящий метод, он вызывает методы **ToString ()** входных объектов и сравнивает результаты строки.</span><span class="sxs-lookup"><span data-stu-id="2df9f-111">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="2df9f-112">Можно указать одно или несколько свойств, которые будут использоваться для сравнения.</span><span class="sxs-lookup"><span data-stu-id="2df9f-112">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="2df9f-113">При указании свойств командлет сравнивает значения только этих свойств.</span><span class="sxs-lookup"><span data-stu-id="2df9f-113">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="2df9f-114">Результат сравнения указывает, отображается ли значение свойства только в объекте **Reference** ( `<=` ) или только в объекте **Difference** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="2df9f-114">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="2df9f-115">Если используется параметр **инклудикуал** , ( `==` ) указывает, что значение находится в обоих объектах.</span><span class="sxs-lookup"><span data-stu-id="2df9f-115">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="2df9f-116">Если **ссылка** или объекты **различий** имеют значение null ( `$null` ), `Compare-Object` создает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="2df9f-116">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="2df9f-117">В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода.</span><span class="sxs-lookup"><span data-stu-id="2df9f-117">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="2df9f-118">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="2df9f-118">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="2df9f-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="2df9f-119">Examples</span></span>

### <span data-ttu-id="2df9f-120">Пример 1. Сравнение содержимого двух текстовых файлов</span><span class="sxs-lookup"><span data-stu-id="2df9f-120">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="2df9f-121">В этом примере сравнивается содержимое двух текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-121">This example compares the contents of two text files.</span></span> <span data-ttu-id="2df9f-122">В примере используются два текстовых файла, каждый из которых имеет значение в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="2df9f-122">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="2df9f-123">`Testfile1.txt` содержит значения: Dog, squirrel и высоты.</span><span class="sxs-lookup"><span data-stu-id="2df9f-123">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="2df9f-124">`Testfile2.txt` содержит значения: Cat, высоты и Ракун.</span><span class="sxs-lookup"><span data-stu-id="2df9f-124">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="2df9f-125">В выходных данных отображаются только те строки, которые отличаются от файлов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-125">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="2df9f-126">`Testfile1.txt` Объект **Reference** ( `<=` ) и `Testfile2.txt` является объектом **Difference** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="2df9f-126">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="2df9f-127">Строки с содержимым, которое отображается в обоих файлах, не отображаются.</span><span class="sxs-lookup"><span data-stu-id="2df9f-127">Lines with content that appear in both files aren't displayed.</span></span>

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

### <span data-ttu-id="2df9f-128">Пример 2. сравнение каждой строки содержимого и исключение различий</span><span class="sxs-lookup"><span data-stu-id="2df9f-128">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="2df9f-129">В этом примере используются параметры **инклудикуал** и **ексклудедифферент** для сравнения каждой строки содержимого в двух текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="2df9f-129">This example uses the **IncludeEqual** and **ExcludeDifferent** parameters to compare each line of content in two text files.</span></span>

<span data-ttu-id="2df9f-130">Поскольку команда использует параметр **ексклудедифферент** , выходные данные содержат только строки, содержащиеся в обоих файлах, как показано в **сидеиндикатор** ( `==` ).</span><span class="sxs-lookup"><span data-stu-id="2df9f-130">Because the command uses the **ExcludeDifferent** parameter, the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

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

### <span data-ttu-id="2df9f-131">Пример 3. Отображение разницы при использовании параметра PassThru</span><span class="sxs-lookup"><span data-stu-id="2df9f-131">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="2df9f-132">Обычно `Compare-Object` возвращает тип **PSCustomObject** со следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="2df9f-132">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="2df9f-133">Сравниваемый объект **InputObject**</span><span class="sxs-lookup"><span data-stu-id="2df9f-133">The **InputObject** being compared</span></span>
- <span data-ttu-id="2df9f-134">Свойство **сидеиндикатор** , показывающее входной объект, которому принадлежат выходные данные</span><span class="sxs-lookup"><span data-stu-id="2df9f-134">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="2df9f-135">При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**.</span><span class="sxs-lookup"><span data-stu-id="2df9f-135">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="2df9f-136">**Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.</span><span class="sxs-lookup"><span data-stu-id="2df9f-136">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="2df9f-137">В следующих примерах показаны различные типы выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2df9f-137">The following examples shows the different output types.</span></span>

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

<span data-ttu-id="2df9f-138">При использовании функции **PassThru** возвращается исходный тип объекта ( **System. Boolean** ).</span><span class="sxs-lookup"><span data-stu-id="2df9f-138">When using **PassThru** , the original object type ( **System.Boolean** ) is returned.</span></span> <span data-ttu-id="2df9f-139">Обратите внимание, что в выходных данных, отображаемых в формате по умолчанию для объектов **System. Boolean** , не отображалось свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-139">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="2df9f-140">Однако возвращенный объект **System. Boolean** имеет добавленный **NoteProperty**.</span><span class="sxs-lookup"><span data-stu-id="2df9f-140">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="2df9f-141">Пример 4. Сравнение двух простых объектов с помощью свойств</span><span class="sxs-lookup"><span data-stu-id="2df9f-141">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="2df9f-142">В этом примере мы сравниваем две различные строки, имеющие одинаковую длину.</span><span class="sxs-lookup"><span data-stu-id="2df9f-142">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="2df9f-143">Пример 5. Сравнение сложных объектов с помощью свойств</span><span class="sxs-lookup"><span data-stu-id="2df9f-143">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="2df9f-144">В этом примере показано поведение при сравнении сложных объектов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-144">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="2df9f-145">В этом примере мы сохраняем два различных объекта процесса для разных экземпляров PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2df9f-145">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="2df9f-146">Обе переменные содержат объекты Process с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="2df9f-146">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="2df9f-147">При сравнении объектов без указания параметра **Свойства** командлет считает объекты одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="2df9f-147">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="2df9f-148">Обратите внимание, что значение **InputObject** совпадает с результатом метода **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-148">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="2df9f-149">Поскольку класс **System. Diagnostics. Process** не имеет интерфейса **IComparable** , командлет преобразует объекты в строки, а затем сравнивает результаты.</span><span class="sxs-lookup"><span data-stu-id="2df9f-149">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

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

<span data-ttu-id="2df9f-150">При указании сравниваемых свойств командлет показывает различия.</span><span class="sxs-lookup"><span data-stu-id="2df9f-150">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="2df9f-151">Пример 6. Сравнение сложных объектов, реализующих интерфейс IComparable</span><span class="sxs-lookup"><span data-stu-id="2df9f-151">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="2df9f-152">Если объект реализует интерфейс **IComparable** , командлет ищет способы сравнения объектов. Если объекты имеют разные типы, то объект **различий** преобразуется в тип **референцеобжект** , который затем сравнивается.</span><span class="sxs-lookup"><span data-stu-id="2df9f-152">If the object implements **IComparable** , the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="2df9f-153">В этом примере выполняется сравнение строки с объектом **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-153">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="2df9f-154">В первом случае строка преобразуется в **интервал** времени, поэтому объекты равны.</span><span class="sxs-lookup"><span data-stu-id="2df9f-154">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

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

<span data-ttu-id="2df9f-155">Во втором случае **TimeSpan** преобразуется в строку, чтобы объект отличался.</span><span class="sxs-lookup"><span data-stu-id="2df9f-155">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="2df9f-156">Параметры</span><span class="sxs-lookup"><span data-stu-id="2df9f-156">Parameters</span></span>

### <span data-ttu-id="2df9f-157">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="2df9f-157">-CaseSensitive</span></span>

<span data-ttu-id="2df9f-158">Указывает, что сравнение выполняется с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="2df9f-158">Indicates that comparisons should be case-sensitive.</span></span>

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

### <span data-ttu-id="2df9f-159">-Culture</span><span class="sxs-lookup"><span data-stu-id="2df9f-159">-Culture</span></span>

<span data-ttu-id="2df9f-160">Указывает язык, используемый для сравнения.</span><span class="sxs-lookup"><span data-stu-id="2df9f-160">Specifies the culture to use for comparisons.</span></span>

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

### <span data-ttu-id="2df9f-161">-Дифференцеобжект</span><span class="sxs-lookup"><span data-stu-id="2df9f-161">-DifferenceObject</span></span>

<span data-ttu-id="2df9f-162">Указывает объекты, сравниваемые с **ссылочными** объектами.</span><span class="sxs-lookup"><span data-stu-id="2df9f-162">Specifies the objects that are compared to the **reference** objects.</span></span>

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

### <span data-ttu-id="2df9f-163">-Ексклудедифферент</span><span class="sxs-lookup"><span data-stu-id="2df9f-163">-ExcludeDifferent</span></span>

<span data-ttu-id="2df9f-164">Указывает, что этот командлет отображает только характеристики сравниваемых объектов, которые равны.</span><span class="sxs-lookup"><span data-stu-id="2df9f-164">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="2df9f-165">Различия между объектами отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="2df9f-165">The differences between the objects are discarded.</span></span>

<span data-ttu-id="2df9f-166">Используйте **ексклудедифферент** с **инклудикуал** , чтобы отобразить только те строки, которые соответствуют объектам **ссылки** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-166">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="2df9f-167">Если **ексклудедифферент** указан без **инклудикуал** , выходные данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2df9f-167">If **ExcludeDifferent** is specified without **IncludeEqual** , there's no output.</span></span>

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

### <span data-ttu-id="2df9f-168">-Инклудикуал</span><span class="sxs-lookup"><span data-stu-id="2df9f-168">-IncludeEqual</span></span>

<span data-ttu-id="2df9f-169">**Инклудикуал** отображает совпадения между объектами **ссылки** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-169">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="2df9f-170">По умолчанию выходные данные также содержат различия между объектами **ссылок** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-170">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

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

### <span data-ttu-id="2df9f-171">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2df9f-171">-PassThru</span></span>

<span data-ttu-id="2df9f-172">При использовании параметра **PassThru** `Compare-Object` опускает оболочку **PSCustomObject** вокруг сравниваемых объектов и возвращает отличающиеся объекты без изменений.</span><span class="sxs-lookup"><span data-stu-id="2df9f-172">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

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

### <span data-ttu-id="2df9f-173">-Property</span><span class="sxs-lookup"><span data-stu-id="2df9f-173">-Property</span></span>

<span data-ttu-id="2df9f-174">Указывает массив свойств **ссылки** и сравниваемых объектов. **difference**</span><span class="sxs-lookup"><span data-stu-id="2df9f-174">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="2df9f-175">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="2df9f-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="2df9f-176">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="2df9f-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="2df9f-177">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="2df9f-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="2df9f-178">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="2df9f-178">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="2df9f-179">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="2df9f-179">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="2df9f-180">-Референцеобжект</span><span class="sxs-lookup"><span data-stu-id="2df9f-180">-ReferenceObject</span></span>

<span data-ttu-id="2df9f-181">Задает массив объектов, используемых в качестве ссылки для сравнения.</span><span class="sxs-lookup"><span data-stu-id="2df9f-181">Specifies an array of objects used as a reference for comparison.</span></span>

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

### <span data-ttu-id="2df9f-182">-Синквиндов</span><span class="sxs-lookup"><span data-stu-id="2df9f-182">-SyncWindow</span></span>

<span data-ttu-id="2df9f-183">Указывает количество смежных объектов, `Compare-Object` проверяемых при поиске совпадения в коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-183">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="2df9f-184">`Compare-Object` проверяет смежные объекты, если он не находит объект в том же положении в коллекции.</span><span class="sxs-lookup"><span data-stu-id="2df9f-184">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="2df9f-185">Значение по умолчанию — `[Int32]::MaxValue` , то есть `Compare-Object` проверяет всю коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="2df9f-185">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

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

### <span data-ttu-id="2df9f-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2df9f-186">CommonParameters</span></span>

<span data-ttu-id="2df9f-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2df9f-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2df9f-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2df9f-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2df9f-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2df9f-189">Inputs</span></span>

### <span data-ttu-id="2df9f-190">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="2df9f-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2df9f-191">Вы можете отправить объект по конвейеру в параметр **дифференцеобжект** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-191">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="2df9f-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2df9f-192">Outputs</span></span>

### <span data-ttu-id="2df9f-193">Нет</span><span class="sxs-lookup"><span data-stu-id="2df9f-193">None</span></span>

<span data-ttu-id="2df9f-194">Если **ссылочный** объект и объект **различий** одинаковы, выходные данные отсутствуют, если не используется параметр **инклудикуал** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-194">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="2df9f-195">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="2df9f-195">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="2df9f-196">Если объекты отличаются, заключает различные `Compare-Object` объекты в `PSCustomObject` оболочке со свойством **сидеиндикатор** для ссылки на различия.</span><span class="sxs-lookup"><span data-stu-id="2df9f-196">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="2df9f-197">При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**.</span><span class="sxs-lookup"><span data-stu-id="2df9f-197">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="2df9f-198">**Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.</span><span class="sxs-lookup"><span data-stu-id="2df9f-198">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="2df9f-199">Примечания</span><span class="sxs-lookup"><span data-stu-id="2df9f-199">Notes</span></span>

<span data-ttu-id="2df9f-200">При использовании параметра **PassThru** выходные данные, отображаемые в консоли, могут не включать свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-200">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="2df9f-201">Представление формата по умолчанию для типа выходных данных объекта не `Compare-Object` включает свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="2df9f-201">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="2df9f-202">Дополнительные сведения см. в [примере 3](#ex3) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2df9f-202">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="2df9f-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2df9f-203">Related links</span></span>

[<span data-ttu-id="2df9f-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="2df9f-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="2df9f-205">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-205">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="2df9f-206">Group-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-206">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="2df9f-207">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="2df9f-207">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="2df9f-208">New-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-208">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="2df9f-209">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-209">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="2df9f-210">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-210">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="2df9f-211">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-211">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="2df9f-212">Where-Object</span><span class="sxs-lookup"><span data-stu-id="2df9f-212">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="2df9f-213">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2df9f-213">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
