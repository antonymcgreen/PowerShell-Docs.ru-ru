---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: f430dd1f9d9f820dda88ba5ad40023650204604d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230362"
---
# <span data-ttu-id="f57b8-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-103">Group-Object</span></span>

## <span data-ttu-id="f57b8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f57b8-104">SYNOPSIS</span></span>
<span data-ttu-id="f57b8-105">Группирует объекты, в которых указанные свойства имеют одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="f57b8-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="f57b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f57b8-106">SYNTAX</span></span>

### <span data-ttu-id="f57b8-107">Хеш</span><span class="sxs-lookup"><span data-stu-id="f57b8-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="f57b8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f57b8-108">DESCRIPTION</span></span>

<span data-ttu-id="f57b8-109">`Group-Object`Командлет отображает объекты в группах на основе значения указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="f57b8-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="f57b8-110">`Group-Object` Возвращает таблицу с одной строкой для каждого значения свойства и столбец, в котором отображается количество элементов с этим значением.</span><span class="sxs-lookup"><span data-stu-id="f57b8-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="f57b8-111">Если указано более одного свойства, `Group-Object` сначала сгруппируйте их по значениям первого свойства, а затем в каждой группе свойств она группируется по значению свойства Next.</span><span class="sxs-lookup"><span data-stu-id="f57b8-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

## <span data-ttu-id="f57b8-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="f57b8-112">EXAMPLES</span></span>

### <span data-ttu-id="f57b8-113">Пример 1. Группировка файлов по расширению</span><span class="sxs-lookup"><span data-stu-id="f57b8-113">Example 1: Group files by extension</span></span>

<span data-ttu-id="f57b8-114">Этот пример рекурсивно получает файлы в `$PSHOME` и группирует их по расширению имени файла.</span><span class="sxs-lookup"><span data-stu-id="f57b8-114">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="f57b8-115">Выходные данные отправляются в `Sort-Object` командлет, который сортирует их по файлам счетчика, найденным для данного расширения.</span><span class="sxs-lookup"><span data-stu-id="f57b8-115">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="f57b8-116">Пустое **имя** представляет каталоги.</span><span class="sxs-lookup"><span data-stu-id="f57b8-116">The empty **Name** represents directories.</span></span>

<span data-ttu-id="f57b8-117">В этом примере используется параметр **элемента** , чтобы опустить члены группы.</span><span class="sxs-lookup"><span data-stu-id="f57b8-117">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### <span data-ttu-id="f57b8-118">Пример 2. Группирование целых чисел с помощью вероятность и даже</span><span class="sxs-lookup"><span data-stu-id="f57b8-118">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="f57b8-119">В этом примере показано, как использовать блоки script в качестве значения параметра **Property** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-119">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="f57b8-120">Эта команда отображает целые числа от 1 до 20, сгруппированные по значениям вероятность и даже.</span><span class="sxs-lookup"><span data-stu-id="f57b8-120">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="f57b8-121">Пример 3. Группировка событий журнала событий по EntryType</span><span class="sxs-lookup"><span data-stu-id="f57b8-121">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="f57b8-122">В этом примере отображаются 1 000 последних записей в журнале системных событий, сгруппированных по **EntryType** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-122">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType** .</span></span>

<span data-ttu-id="f57b8-123">В выходных данных столбец **Count** представляет количество записей в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="f57b8-123">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="f57b8-124">Столбец **Name** представляет значения **EventType** , определяющие группу.</span><span class="sxs-lookup"><span data-stu-id="f57b8-124">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="f57b8-125">Столбец **Group** представляет объекты в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="f57b8-125">The **Group** column represents the objects in each group.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### <span data-ttu-id="f57b8-126">Пример 4. Группирование процессов по классу приоритета</span><span class="sxs-lookup"><span data-stu-id="f57b8-126">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="f57b8-127">В этом примере демонстрируется действие параметра **элемента** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-127">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="f57b8-128">Эти команды группируют процессы на компьютере по классу приоритета.</span><span class="sxs-lookup"><span data-stu-id="f57b8-128">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="f57b8-129">Первая команда использует `Get-Process` командлет для получения процессов на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f57b8-129">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="f57b8-130">`Group-Object`Группирует объекты по значению свойства **PriorityClass значение** процесса.</span><span class="sxs-lookup"><span data-stu-id="f57b8-130">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="f57b8-131">Во втором примере используется параметр **элемента** , чтобы исключить члены группы из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f57b8-131">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="f57b8-132">Результатом является таблица с только значением свойства **Count** и **Name** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-132">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="f57b8-133">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="f57b8-133">The results are shown in the following sample output.</span></span>

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### <span data-ttu-id="f57b8-134">Пример 5. Группирование процессов по имени</span><span class="sxs-lookup"><span data-stu-id="f57b8-134">Example 5: Group processes by name</span></span>

<span data-ttu-id="f57b8-135">В следующем примере используется `Group-Object` для группирования нескольких экземпляров процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f57b8-135">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="f57b8-136">`Where-Object` Отображает процессы с более чем одним экземпляром.</span><span class="sxs-lookup"><span data-stu-id="f57b8-136">`Where-Object` displays processes with more than one instance.</span></span>

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### <span data-ttu-id="f57b8-137">Пример 6. Группирование объектов в хэш-таблице</span><span class="sxs-lookup"><span data-stu-id="f57b8-137">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="f57b8-138">В этом примере используются параметры **AsHashTable** и **AsString** для возврата групп в хэш-таблице в виде коллекции пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="f57b8-138">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="f57b8-139">В полученной хэш-таблице каждое значение свойства является ключом, а элементы группы — значениями.</span><span class="sxs-lookup"><span data-stu-id="f57b8-139">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="f57b8-140">Поскольку каждый ключ является свойством объекта хэш-таблицы, для отображения значений можно использовать точечную нотацию.</span><span class="sxs-lookup"><span data-stu-id="f57b8-140">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="f57b8-141">Первая команда получает `Get` `Set` командлеты и в сеансе, группирует их по команде, возвращает группы в виде хэш-таблицы и сохраняет хэш-таблицу в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="f57b8-141">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="f57b8-142">Вторая команда отображает хэш-таблицу в `$A` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-142">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="f57b8-143">Существует две пары «ключ-значение»: одна для `Get` командлетов и одна для `Set` командлетов.</span><span class="sxs-lookup"><span data-stu-id="f57b8-143">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="f57b8-144">Третья команда использует точечную нотацию `$A.Get` для вывода значений ключа **Get** в `$A` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-144">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="f57b8-145">Значения — **CmdletInfo** Object.</span><span class="sxs-lookup"><span data-stu-id="f57b8-145">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="f57b8-146">Параметр **AsString** не преобразует объекты в группах в строки.</span><span class="sxs-lookup"><span data-stu-id="f57b8-146">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AuthenticodeSignature          6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-ChildItem                      6.1.0.0    Microsoft.PowerShell.Management
...
```

## <span data-ttu-id="f57b8-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f57b8-147">PARAMETERS</span></span>

### <span data-ttu-id="f57b8-148">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="f57b8-148">-AsHashTable</span></span>

<span data-ttu-id="f57b8-149">Указывает, что этот командлет возвращает группу в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="f57b8-149">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="f57b8-150">Ключами хэш-таблицы являются значения свойств, по которым группируются объекты.</span><span class="sxs-lookup"><span data-stu-id="f57b8-150">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="f57b8-151">Значениями хэш-таблицы являются объекты, имеющие это значение свойства.</span><span class="sxs-lookup"><span data-stu-id="f57b8-151">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="f57b8-152">Сам по себе параметр **AsHashTable** возвращает каждую хэш-таблицу, в которой каждый ключ является экземпляром сгруппированного объекта.</span><span class="sxs-lookup"><span data-stu-id="f57b8-152">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="f57b8-153">При использовании с параметром **AsString** ключи в хэш-таблице являются строками.</span><span class="sxs-lookup"><span data-stu-id="f57b8-153">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f57b8-154">-AsString</span><span class="sxs-lookup"><span data-stu-id="f57b8-154">-AsString</span></span>

<span data-ttu-id="f57b8-155">Указывает, что этот командлет преобразует ключи хэш-таблицы в строки.</span><span class="sxs-lookup"><span data-stu-id="f57b8-155">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="f57b8-156">По умолчанию ключами хэш-таблицы являются экземпляры группируемых объектов.</span><span class="sxs-lookup"><span data-stu-id="f57b8-156">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="f57b8-157">Этот параметр допустим только при использовании с параметром **AsHashTable** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-157">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="f57b8-158">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="f57b8-158">-CaseSensitive</span></span>

<span data-ttu-id="f57b8-159">Указывает, что этот командлет делает группирование с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="f57b8-159">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="f57b8-160">Без этого параметра в группу будут включаться значения свойств в разных регистрах.</span><span class="sxs-lookup"><span data-stu-id="f57b8-160">Without this parameter, the property values of objects in a group might have different cases.</span></span>

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

### <span data-ttu-id="f57b8-161">-Culture</span><span class="sxs-lookup"><span data-stu-id="f57b8-161">-Culture</span></span>

<span data-ttu-id="f57b8-162">Задает язык и региональные параметры. которые будут использоваться при сравнении строк.</span><span class="sxs-lookup"><span data-stu-id="f57b8-162">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="f57b8-163">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f57b8-163">-InputObject</span></span>

<span data-ttu-id="f57b8-164">Задает объекты, которые будут включаться в группу.</span><span class="sxs-lookup"><span data-stu-id="f57b8-164">Specifies the objects to group.</span></span> <span data-ttu-id="f57b8-165">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="f57b8-165">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="f57b8-166">При использовании параметра **InputObject** для отправки коллекции объектов в `Group-Object` `Group-Object` получается один объект, представляющий коллекцию.</span><span class="sxs-lookup"><span data-stu-id="f57b8-166">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="f57b8-167">В результате командлет создает одну группу, в которую входит этот объект.</span><span class="sxs-lookup"><span data-stu-id="f57b8-167">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="f57b8-168">Чтобы сгруппировать объекты в коллекции, передаем объекты в `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-168">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f57b8-169">-NoElement</span><span class="sxs-lookup"><span data-stu-id="f57b8-169">-NoElement</span></span>

<span data-ttu-id="f57b8-170">Указывает, что этот командлет опускает члены группы из результатов.</span><span class="sxs-lookup"><span data-stu-id="f57b8-170">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="f57b8-171">-Property</span><span class="sxs-lookup"><span data-stu-id="f57b8-171">-Property</span></span>

<span data-ttu-id="f57b8-172">Определяет свойства для группирования.</span><span class="sxs-lookup"><span data-stu-id="f57b8-172">Specifies the properties for grouping.</span></span> <span data-ttu-id="f57b8-173">Объекты объединяются в группы на основании значения заданного свойства.</span><span class="sxs-lookup"><span data-stu-id="f57b8-173">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="f57b8-174">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="f57b8-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="f57b8-175">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="f57b8-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="f57b8-176">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="f57b8-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="f57b8-177">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="f57b8-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="f57b8-178">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="f57b8-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f57b8-179">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f57b8-179">CommonParameters</span></span>

<span data-ttu-id="f57b8-180">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f57b8-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f57b8-181">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f57b8-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f57b8-182">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f57b8-182">INPUTS</span></span>

### <span data-ttu-id="f57b8-183">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="f57b8-183">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f57b8-184">Любой объект можно передать по конвейеру в `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-184">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="f57b8-185">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f57b8-185">OUTPUTS</span></span>

### <span data-ttu-id="f57b8-186">Microsoft.PowerShell.Commands.GroupInfo или System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="f57b8-186">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="f57b8-187">При использовании параметра **AsHashTable** `Group-Object` возвращает объект **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-187">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="f57b8-188">В противном случае возвращается объект **GroupInfo** .</span><span class="sxs-lookup"><span data-stu-id="f57b8-188">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="f57b8-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f57b8-189">NOTES</span></span>

<span data-ttu-id="f57b8-190">Для группирования объектов можно использовать параметр **GroupBy** командлетов форматирования, например `Format-Table` и `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-190">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="f57b8-191">В отличие от `Group-Object` , при котором создается одна таблица со строкой для каждого значения свойства, параметры **GroupBy** создают таблицу для каждого значения свойства со строкой для каждого элемента, имеющего значение свойства.</span><span class="sxs-lookup"><span data-stu-id="f57b8-191">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="f57b8-192">`Group-Object` не требует, чтобы сгруппированные объекты совпадали с типом Microsoft .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f57b8-192">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="f57b8-193">При группировании объектов различных типов .NET Core `Group-Object` использует следующие правила.</span><span class="sxs-lookup"><span data-stu-id="f57b8-193">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="f57b8-194">Одинаковые имена и типы свойств.</span><span class="sxs-lookup"><span data-stu-id="f57b8-194">Same Property Names and Types.</span></span>

  <span data-ttu-id="f57b8-195">Если у объектов есть свойство с указанным именем, а значения свойств имеют один и тот же тип .NET Core, то значения свойств группируются с использованием тех же правил, которые использовались для объектов того же типа.</span><span class="sxs-lookup"><span data-stu-id="f57b8-195">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="f57b8-196">Одинаковые имена свойств, различные типы.</span><span class="sxs-lookup"><span data-stu-id="f57b8-196">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="f57b8-197">Если у объектов есть свойство с указанным именем, но значения свойств имеют разные типы .NET Core в разных объектах, `Group-Object` использует тип .NET Core первого экземпляра свойства в качестве типа .NET Core для этой группы свойств.</span><span class="sxs-lookup"><span data-stu-id="f57b8-197">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="f57b8-198">Если у объекта имеется свойство другого типа, значение этого свойства преобразуется в тип данной группы.</span><span class="sxs-lookup"><span data-stu-id="f57b8-198">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="f57b8-199">Если преобразование типа завершается неудачей, объект не включается в группу.</span><span class="sxs-lookup"><span data-stu-id="f57b8-199">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="f57b8-200">Отсутствующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f57b8-200">Missing Properties.</span></span>

  <span data-ttu-id="f57b8-201">Объекты, у которых нет указанного свойства, не могут быть сгруппированы.</span><span class="sxs-lookup"><span data-stu-id="f57b8-201">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="f57b8-202">Объекты, которые не группируются, отображаются в конечном выводе объекта **GroupInfo** в группе с именем `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="f57b8-202">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="f57b8-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f57b8-203">RELATED LINKS</span></span>

[<span data-ttu-id="f57b8-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="f57b8-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="f57b8-205">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="f57b8-205">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="f57b8-206">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-206">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="f57b8-207">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-207">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="f57b8-208">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="f57b8-208">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="f57b8-209">New-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-209">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="f57b8-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-210">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="f57b8-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-211">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="f57b8-212">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-212">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="f57b8-213">Where-Object</span><span class="sxs-lookup"><span data-stu-id="f57b8-213">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
