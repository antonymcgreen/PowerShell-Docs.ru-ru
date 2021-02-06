---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: 6198964f01a4c0dc70584cdb3e5c0e13f3965934
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601497"
---
# <span data-ttu-id="51d03-102">Group-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-102">Group-Object</span></span>

## <span data-ttu-id="51d03-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51d03-103">SYNOPSIS</span></span>
<span data-ttu-id="51d03-104">Группирует объекты, в которых указанные свойства имеют одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="51d03-104">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="51d03-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51d03-105">SYNTAX</span></span>

### <span data-ttu-id="51d03-106">Хеш</span><span class="sxs-lookup"><span data-stu-id="51d03-106">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="51d03-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="51d03-107">DESCRIPTION</span></span>

<span data-ttu-id="51d03-108">`Group-Object`Командлет отображает объекты в группах на основе значения указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="51d03-108">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="51d03-109">`Group-Object` Возвращает таблицу с одной строкой для каждого значения свойства и столбец, в котором отображается количество элементов с этим значением.</span><span class="sxs-lookup"><span data-stu-id="51d03-109">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="51d03-110">Если указано более одного свойства, `Group-Object` сначала сгруппируйте их по значениям первого свойства, а затем в каждой группе свойств она группируется по значению свойства Next.</span><span class="sxs-lookup"><span data-stu-id="51d03-110">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

<span data-ttu-id="51d03-111">Начиная с PowerShell 7, `Group-Object` может сочетать параметры **CaseSensitive** и **AsHashtable** для создания хэш-таблицы с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="51d03-111">Beginning in PowerShell 7, `Group-Object` can combine the **CaseSensitive** and **AsHashtable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="51d03-112">В ключах хэш-таблицы используются сравнения с учетом регистра и вывод объекта **System. Collections. Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-112">The hash table keys use case-sensitive comparisons and output a **System.Collections.Hashtable** object.</span></span>

## <span data-ttu-id="51d03-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="51d03-113">EXAMPLES</span></span>

### <span data-ttu-id="51d03-114">Пример 1. Группировка файлов по расширению</span><span class="sxs-lookup"><span data-stu-id="51d03-114">Example 1: Group files by extension</span></span>

<span data-ttu-id="51d03-115">Этот пример рекурсивно получает файлы в `$PSHOME` и группирует их по расширению имени файла.</span><span class="sxs-lookup"><span data-stu-id="51d03-115">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="51d03-116">Выходные данные отправляются в `Sort-Object` командлет, который сортирует их по файлам счетчика, найденным для данного расширения.</span><span class="sxs-lookup"><span data-stu-id="51d03-116">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="51d03-117">Пустое **имя** представляет каталоги.</span><span class="sxs-lookup"><span data-stu-id="51d03-117">The empty **Name** represents directories.</span></span>

<span data-ttu-id="51d03-118">В этом примере используется параметр **элемента** , чтобы опустить члены группы.</span><span class="sxs-lookup"><span data-stu-id="51d03-118">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

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

### <span data-ttu-id="51d03-119">Пример 2. Группирование целых чисел с помощью вероятность и даже</span><span class="sxs-lookup"><span data-stu-id="51d03-119">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="51d03-120">В этом примере показано, как использовать блоки script в качестве значения параметра **Property** .</span><span class="sxs-lookup"><span data-stu-id="51d03-120">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="51d03-121">Эта команда отображает целые числа от 1 до 20, сгруппированные по значениям вероятность и даже.</span><span class="sxs-lookup"><span data-stu-id="51d03-121">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="51d03-122">Пример 3. Группировка событий журнала событий по EntryType</span><span class="sxs-lookup"><span data-stu-id="51d03-122">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="51d03-123">В этом примере отображаются 1 000 последних записей в журнале системных событий, сгруппированных по **EntryType**.</span><span class="sxs-lookup"><span data-stu-id="51d03-123">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType**.</span></span>

<span data-ttu-id="51d03-124">В выходных данных столбец **Count** представляет количество записей в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="51d03-124">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="51d03-125">Столбец **Name** представляет значения **EventType** , определяющие группу.</span><span class="sxs-lookup"><span data-stu-id="51d03-125">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="51d03-126">Столбец **Group** представляет объекты в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="51d03-126">The **Group** column represents the objects in each group.</span></span>

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

### <span data-ttu-id="51d03-127">Пример 4. Группирование процессов по классу приоритета</span><span class="sxs-lookup"><span data-stu-id="51d03-127">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="51d03-128">В этом примере демонстрируется действие параметра **элемента** .</span><span class="sxs-lookup"><span data-stu-id="51d03-128">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="51d03-129">Эти команды группируют процессы на компьютере по классу приоритета.</span><span class="sxs-lookup"><span data-stu-id="51d03-129">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="51d03-130">Первая команда использует `Get-Process` командлет для получения процессов на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="51d03-130">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="51d03-131">`Group-Object`Группирует объекты по значению свойства **PriorityClass значение** процесса.</span><span class="sxs-lookup"><span data-stu-id="51d03-131">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="51d03-132">Во втором примере используется параметр **элемента** , чтобы исключить члены группы из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="51d03-132">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="51d03-133">Результатом является таблица с только значением свойства **Count** и **Name** .</span><span class="sxs-lookup"><span data-stu-id="51d03-133">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="51d03-134">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="51d03-134">The results are shown in the following sample output.</span></span>

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

### <span data-ttu-id="51d03-135">Пример 5. Группирование процессов по имени</span><span class="sxs-lookup"><span data-stu-id="51d03-135">Example 5: Group processes by name</span></span>

<span data-ttu-id="51d03-136">В следующем примере используется `Group-Object` для группирования нескольких экземпляров процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="51d03-136">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="51d03-137">`Where-Object` Отображает процессы с более чем одним экземпляром.</span><span class="sxs-lookup"><span data-stu-id="51d03-137">`Where-Object` displays processes with more than one instance.</span></span>

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

### <span data-ttu-id="51d03-138">Пример 6. Группирование объектов в хэш-таблице</span><span class="sxs-lookup"><span data-stu-id="51d03-138">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="51d03-139">В этом примере используются параметры **AsHashTable** и **AsString** для возврата групп в хэш-таблице в виде коллекции пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="51d03-139">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="51d03-140">В полученной хэш-таблице каждое значение свойства является ключом, а элементы группы — значениями.</span><span class="sxs-lookup"><span data-stu-id="51d03-140">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="51d03-141">Поскольку каждый ключ является свойством объекта хэш-таблицы, для отображения значений можно использовать точечную нотацию.</span><span class="sxs-lookup"><span data-stu-id="51d03-141">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="51d03-142">Первая команда получает `Get` `Set` командлеты и в сеансе, группирует их по команде, возвращает группы в виде хэш-таблицы и сохраняет хэш-таблицу в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="51d03-142">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="51d03-143">Вторая команда отображает хэш-таблицу в `$A` .</span><span class="sxs-lookup"><span data-stu-id="51d03-143">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="51d03-144">Существует две пары «ключ-значение»: одна для `Get` командлетов и одна для `Set` командлетов.</span><span class="sxs-lookup"><span data-stu-id="51d03-144">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="51d03-145">Третья команда использует точечную нотацию `$A.Get` для вывода значений ключа **Get** в `$A` .</span><span class="sxs-lookup"><span data-stu-id="51d03-145">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="51d03-146">Значения — **CmdletInfo** Object.</span><span class="sxs-lookup"><span data-stu-id="51d03-146">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="51d03-147">Параметр **AsString** не преобразует объекты в группах в строки.</span><span class="sxs-lookup"><span data-stu-id="51d03-147">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

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
CommandType     Name                                Version    Source
-----------     ----                                -------    ------
Cmdlet          Get-Acl                             7.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                           7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation        2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                 2.0.0.0    AppLocker
...
```

### <span data-ttu-id="51d03-148">Пример 7. Создание хэш-таблицы с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="51d03-148">Example 7: Create a case-sensitive hash table</span></span>

<span data-ttu-id="51d03-149">В этом примере объединяются параметры **CaseSensitive** и **AsHashTable** для создания хэш-таблицы с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="51d03-149">This example combines the **CaseSensitive** and **AsHashTable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="51d03-150">Файлы в примере имеют расширения `.txt` и `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="51d03-150">The files in the example have extensions of `.txt` and `.TXT`.</span></span>

```powershell
$hash = Get-ChildItem -Path C:\Files | Group-Object -Property Extension -CaseSensitive -AsHashTable
$hash
```

```Output
Name           Value
----           -----
.TXT           {C:\Files\File7.TXT, C:\Files\File8.TXT, C:\Files\File9.TXT}
.txt           {C:\Files\file1.txt, C:\Files\file2.txt, C:\Files\file3.txt}
```

<span data-ttu-id="51d03-151">`$hash`Переменная хранит объект **System. Collections. Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-151">The `$hash` variable stores the **System.Collections.Hashtable** object.</span></span> <span data-ttu-id="51d03-152">`Get-ChildItem` Получает имена файлов из `C:\Files` каталога и отправляет объекты **System. IO. FileInfo** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="51d03-152">`Get-ChildItem` gets the file names from the `C:\Files` directory and sends the **System.IO.FileInfo** objects down the pipeline.</span></span> <span data-ttu-id="51d03-153">`Group-Object`Группирует объекты с помощью **расширения** значения **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="51d03-153">`Group-Object` groups the objects using the **Property** value **Extension**.</span></span> <span data-ttu-id="51d03-154">Параметры **CaseSensitive** и **AsHashTable** создают хэш-таблицу, а ключи группируются с использованием ключей с учетом регистра `.txt` и `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="51d03-154">The **CaseSensitive** and **AsHashTable** parameters create the hash table and the keys are grouped using the case-sensitive keys `.txt` and `.TXT`.</span></span>

## <span data-ttu-id="51d03-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51d03-155">PARAMETERS</span></span>

### <span data-ttu-id="51d03-156">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="51d03-156">-AsHashTable</span></span>

<span data-ttu-id="51d03-157">Указывает, что этот командлет возвращает группу в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="51d03-157">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="51d03-158">Ключами хэш-таблицы являются значения свойств, по которым группируются объекты.</span><span class="sxs-lookup"><span data-stu-id="51d03-158">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="51d03-159">Значениями хэш-таблицы являются объекты, имеющие это значение свойства.</span><span class="sxs-lookup"><span data-stu-id="51d03-159">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="51d03-160">Сам по себе параметр **AsHashTable** возвращает каждую хэш-таблицу, в которой каждый ключ является экземпляром сгруппированного объекта.</span><span class="sxs-lookup"><span data-stu-id="51d03-160">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="51d03-161">При использовании с параметром **AsString** ключи в хэш-таблице являются строками.</span><span class="sxs-lookup"><span data-stu-id="51d03-161">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

<span data-ttu-id="51d03-162">Начиная с PowerShell 7, чтобы создавать хэш-таблицы с учетом регистра, в команде следует включать **CaseSensitive** и **AsHashtable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-162">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

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

### <span data-ttu-id="51d03-163">-AsString</span><span class="sxs-lookup"><span data-stu-id="51d03-163">-AsString</span></span>

<span data-ttu-id="51d03-164">Указывает, что этот командлет преобразует ключи хэш-таблицы в строки.</span><span class="sxs-lookup"><span data-stu-id="51d03-164">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="51d03-165">По умолчанию ключами хэш-таблицы являются экземпляры группируемых объектов.</span><span class="sxs-lookup"><span data-stu-id="51d03-165">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="51d03-166">Этот параметр допустим только при использовании с параметром **AsHashTable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-166">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="51d03-167">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="51d03-167">-CaseSensitive</span></span>

<span data-ttu-id="51d03-168">Указывает, что этот командлет делает группирование с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="51d03-168">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="51d03-169">Без этого параметра в группу будут включаться значения свойств в разных регистрах.</span><span class="sxs-lookup"><span data-stu-id="51d03-169">Without this parameter, the property values of objects in a group might have different cases.</span></span>

<span data-ttu-id="51d03-170">Начиная с PowerShell 7, чтобы создавать хэш-таблицы с учетом регистра, в команде следует включать **CaseSensitive** и **AsHashtable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-170">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

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

### <span data-ttu-id="51d03-171">-Culture</span><span class="sxs-lookup"><span data-stu-id="51d03-171">-Culture</span></span>

<span data-ttu-id="51d03-172">Задает язык и региональные параметры. которые будут использоваться при сравнении строк.</span><span class="sxs-lookup"><span data-stu-id="51d03-172">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="51d03-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="51d03-173">-InputObject</span></span>

<span data-ttu-id="51d03-174">Задает объекты, которые будут включаться в группу.</span><span class="sxs-lookup"><span data-stu-id="51d03-174">Specifies the objects to group.</span></span> <span data-ttu-id="51d03-175">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="51d03-175">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="51d03-176">При использовании параметра **InputObject** для отправки коллекции объектов в `Group-Object` `Group-Object` получается один объект, представляющий коллекцию.</span><span class="sxs-lookup"><span data-stu-id="51d03-176">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="51d03-177">В результате командлет создает одну группу, в которую входит этот объект.</span><span class="sxs-lookup"><span data-stu-id="51d03-177">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="51d03-178">Чтобы сгруппировать объекты в коллекции, передаем объекты в `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="51d03-178">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="51d03-179">-NoElement</span><span class="sxs-lookup"><span data-stu-id="51d03-179">-NoElement</span></span>

<span data-ttu-id="51d03-180">Указывает, что этот командлет опускает члены группы из результатов.</span><span class="sxs-lookup"><span data-stu-id="51d03-180">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="51d03-181">-Property</span><span class="sxs-lookup"><span data-stu-id="51d03-181">-Property</span></span>

<span data-ttu-id="51d03-182">Определяет свойства для группирования.</span><span class="sxs-lookup"><span data-stu-id="51d03-182">Specifies the properties for grouping.</span></span> <span data-ttu-id="51d03-183">Объекты объединяются в группы на основании значения заданного свойства.</span><span class="sxs-lookup"><span data-stu-id="51d03-183">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="51d03-184">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="51d03-184">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="51d03-185">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="51d03-185">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="51d03-186">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="51d03-186">Valid key-value pairs are:</span></span>

- <span data-ttu-id="51d03-187">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="51d03-187">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="51d03-188">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="51d03-188">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="51d03-189">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="51d03-189">CommonParameters</span></span>

<span data-ttu-id="51d03-190">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="51d03-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51d03-191">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="51d03-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="51d03-192">Входные данные</span><span class="sxs-lookup"><span data-stu-id="51d03-192">INPUTS</span></span>

### <span data-ttu-id="51d03-193">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="51d03-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="51d03-194">Любой объект можно передать по конвейеру в `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="51d03-194">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="51d03-195">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="51d03-195">OUTPUTS</span></span>

### <span data-ttu-id="51d03-196">Microsoft.PowerShell.Commands.GroupInfo или System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="51d03-196">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="51d03-197">При использовании параметра **AsHashTable** `Group-Object` возвращает объект **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="51d03-197">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="51d03-198">В противном случае возвращается объект **GroupInfo** .</span><span class="sxs-lookup"><span data-stu-id="51d03-198">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="51d03-199">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="51d03-199">NOTES</span></span>

<span data-ttu-id="51d03-200">Для группирования объектов можно использовать параметр **GroupBy** командлетов форматирования, например `Format-Table` и `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="51d03-200">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="51d03-201">В отличие от `Group-Object` , при котором создается одна таблица со строкой для каждого значения свойства, параметры **GroupBy** создают таблицу для каждого значения свойства со строкой для каждого элемента, имеющего значение свойства.</span><span class="sxs-lookup"><span data-stu-id="51d03-201">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="51d03-202">`Group-Object` не требует, чтобы сгруппированные объекты совпадали с типом Microsoft .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51d03-202">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="51d03-203">При группировании объектов различных типов .NET Core `Group-Object` использует следующие правила.</span><span class="sxs-lookup"><span data-stu-id="51d03-203">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="51d03-204">Одинаковые имена и типы свойств.</span><span class="sxs-lookup"><span data-stu-id="51d03-204">Same Property Names and Types.</span></span>

  <span data-ttu-id="51d03-205">Если у объектов есть свойство с указанным именем, а значения свойств имеют один и тот же тип .NET Core, то значения свойств группируются с использованием тех же правил, которые использовались для объектов того же типа.</span><span class="sxs-lookup"><span data-stu-id="51d03-205">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="51d03-206">Одинаковые имена свойств, различные типы.</span><span class="sxs-lookup"><span data-stu-id="51d03-206">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="51d03-207">Если у объектов есть свойство с указанным именем, но значения свойств имеют разные типы .NET Core в разных объектах, `Group-Object` использует тип .NET Core первого экземпляра свойства в качестве типа .NET Core для этой группы свойств.</span><span class="sxs-lookup"><span data-stu-id="51d03-207">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="51d03-208">Если у объекта имеется свойство другого типа, значение этого свойства преобразуется в тип данной группы.</span><span class="sxs-lookup"><span data-stu-id="51d03-208">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="51d03-209">Если преобразование типа завершается неудачей, объект не включается в группу.</span><span class="sxs-lookup"><span data-stu-id="51d03-209">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="51d03-210">Отсутствующие свойства.</span><span class="sxs-lookup"><span data-stu-id="51d03-210">Missing Properties.</span></span>

  <span data-ttu-id="51d03-211">Объекты, у которых нет указанного свойства, не могут быть сгруппированы.</span><span class="sxs-lookup"><span data-stu-id="51d03-211">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="51d03-212">Объекты, которые не группируются, отображаются в конечном выводе объекта **GroupInfo** в группе с именем `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="51d03-212">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="51d03-213">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="51d03-213">RELATED LINKS</span></span>

[<span data-ttu-id="51d03-214">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="51d03-214">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="51d03-215">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="51d03-215">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="51d03-216">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-216">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="51d03-217">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-217">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="51d03-218">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="51d03-218">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="51d03-219">New-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-219">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="51d03-220">Select-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-220">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="51d03-221">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-221">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="51d03-222">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-222">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="51d03-223">Where-Object</span><span class="sxs-lookup"><span data-stu-id="51d03-223">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
