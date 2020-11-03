---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "93230605"
---
# <span data-ttu-id="1ccc3-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-103">ForEach-Object</span></span>

## <span data-ttu-id="1ccc3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1ccc3-104">Synopsis</span></span>
<span data-ttu-id="1ccc3-105">Выполняет операцию для каждого элемента в коллекции входных объектов.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="1ccc3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ccc3-106">Syntax</span></span>

### <span data-ttu-id="1ccc3-107">Скриптблокксет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1ccc3-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1ccc3-108">пропертяндмесодсет</span><span class="sxs-lookup"><span data-stu-id="1ccc3-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1ccc3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1ccc3-109">Description</span></span>

<span data-ttu-id="1ccc3-110">`ForEach-Object`Командлет выполняет операцию над каждым элементом в коллекции входных объектов.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="1ccc3-111">Входные объекты можно передать в командлет или указать с помощью параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="1ccc3-112">Начиная с Windows PowerShell 3,0 существует два разных способа создания `ForEach-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="1ccc3-113">**Блок скрипта** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-113">**Script block** .</span></span> <span data-ttu-id="1ccc3-114">Можно использовать блок скрипта, чтобы указать операцию.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="1ccc3-115">В блоке скрипта используйте `$_` переменную для представления текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="1ccc3-116">Блок скрипта — это значение параметра **Process** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="1ccc3-117">Блок скрипта может содержать любой сценарий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="1ccc3-118">Например, следующая команда возвращает значение свойства **ProcessName** каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="1ccc3-119">`ForEach-Object` поддерживает `begin` блоки, `process` и, `end` как описано в разделе [about_functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1ccc3-120">Блоки скрипта выполняются в области действия вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="1ccc3-121">Поэтому блоки имеют доступ к переменным в этой области и могут создавать новые переменные, которые сохраняются в этой области после завершения выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="1ccc3-122">**Оператор Operation** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-122">**Operation statement** .</span></span> <span data-ttu-id="1ccc3-123">Можно также написать оператор операции, который гораздо более похож на естественный язык.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="1ccc3-124">С помощью инструкции операции можно указать значение свойства или вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="1ccc3-125">Инструкции операций появились в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="1ccc3-126">Например, следующая команда также возвращает значение свойства **ProcessName** каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

## <span data-ttu-id="1ccc3-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ccc3-127">Examples</span></span>

### <span data-ttu-id="1ccc3-128">Пример 1. деление целых чисел в массиве</span><span class="sxs-lookup"><span data-stu-id="1ccc3-128">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="1ccc3-129">Этот пример принимает массив из трех целых чисел и делит каждый из них на 1024.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-129">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="1ccc3-130">Пример 2. Получение длины всех файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="1ccc3-130">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="1ccc3-131">В этом примере выполняется обработка файлов и каталогов в каталоге установки PowerShell `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-131">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="1ccc3-132">Если объект не является каталогом, блок скрипта получает имя файла, делит значение его свойства **length** на 1024 и добавляет пробел (""), чтобы отделить его от следующей записи.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-132">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="1ccc3-133">Командлет использует свойство **PSISContainer** , чтобы определить, является ли объект каталогом.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-133">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="1ccc3-134">Пример 3. Эксплуатация с самыми последними системными событиями</span><span class="sxs-lookup"><span data-stu-id="1ccc3-134">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="1ccc3-135">Этот пример записывает 1000 последних событий из журнала системных событий в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-135">This example write the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="1ccc3-136">Текущее время отображается до и после обработки событий.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-136">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="1ccc3-137">`Get-EventLog` Возвращает 1000 последних событий из журнала системных событий и сохраняет их в `$Events` переменной.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-137">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="1ccc3-138">`$Events` затем передается в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-138">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="1ccc3-139">Параметр **Begin** используется для отображения текущей даты и времени.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-139">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="1ccc3-140">Затем параметр **Process** использует `Out-File` командлет для создания текстового файла с именем events.txt и сохраняет свойство Message каждого события в этом файле.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-140">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="1ccc3-141">Наконец, параметр **End** используется для отображения даты и времени после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-141">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="1ccc3-142">Пример 4. изменение значения раздела реестра</span><span class="sxs-lookup"><span data-stu-id="1ccc3-142">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="1ccc3-143">Этот пример изменяет значение записи реестра **RemotePath** во всех подразделах `HKCU:\Network` раздела на верхний.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-143">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="1ccc3-144">Этот формат можно использовать для изменения формы или содержимого раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-144">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="1ccc3-145">Каждый подраздел **Network** представляет сопоставленный сетевой диск, который будет подключаться при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-145">Each subkey in the **Network** key represents a mapped network drive that will reconnect at logon.</span></span>
<span data-ttu-id="1ccc3-146">Запись **RemotePath** содержит UNC-путь подключенного диска.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-146">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="1ccc3-147">Например, если подключить диск E: к `\\Server\Share` , будет указан подраздел **e** , `HKCU:\Network` а в подразделе **e** — значение параметра реестра **RemotePath** `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-147">For example, if you map the E: drive to `\\Server\Share`, there will be an **E** subkey of `HKCU:\Network` and the value of the **RemotePath** registry entry in the **E** subkey is `\\Server\Share`.</span></span>

<span data-ttu-id="1ccc3-148">Команда использует командлет, `Get-ItemProperty` чтобы получить все подразделы **сетевого** ключа и `Set-ItemProperty` командлета, чтобы изменить значение записи реестра **RemotePath** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-148">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="1ccc3-149">В `Set-ItemProperty` команде путь является значением свойства **PSPath** раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-149">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="1ccc3-150">Это свойство объекта Microsoft .NET Framework, представляющего раздел реестра, а не запись реестра.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-150">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="1ccc3-151">Команда использует метод **ToUpper ()** значения **RemotePath** , который является строкой (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-151">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="1ccc3-152">Поскольку `Set-ItemProperty` изменяет свойство каждого ключа, `ForEach-Object` для доступа к свойству необходим командлет.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-152">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="1ccc3-153">Пример 5. Использование автоматической переменной $Null</span><span class="sxs-lookup"><span data-stu-id="1ccc3-153">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="1ccc3-154">В этом примере показан результат передачи `$Null` автоматической переменной в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-154">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="1ccc3-155">Так как PowerShell обрабатывает значение null как явный заполнитель, `ForEach-Object` командлет создает значение для `$Null` , точно так же, как и для других объектов, которые вы выполняете по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-155">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="1ccc3-156">Пример 6. Получение значений свойств</span><span class="sxs-lookup"><span data-stu-id="1ccc3-156">Example 6: Get property values</span></span>

<span data-ttu-id="1ccc3-157">Этот пример возвращает значение свойства **path** для всех установленных модулей PowerShell с помощью параметра **MemberName** `ForEach-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-157">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="1ccc3-158">Вторая команда эквивалента первой.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-158">The second command is equivalent to the first.</span></span> <span data-ttu-id="1ccc3-159">Он использует `Foreach` псевдоним `ForEach-Object` командлета и опускает имя параметра **MemberName** , которое является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-159">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="1ccc3-160">`ForEach-Object`Командлет очень полезен для получения значений свойств, так как он получает значение без изменения типа, в отличие от командлетов **Format** или `Select-Object` командлетов, которые изменяют тип значения свойства.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-160">The `ForEach-Object` cmdlet is very useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="1ccc3-161">Пример 7. разбиение имен модулей по именам компонентов</span><span class="sxs-lookup"><span data-stu-id="1ccc3-161">Example 7: Split module names into component names</span></span>

<span data-ttu-id="1ccc3-162">В этом примере показано три способа разбиения двух разделенных точками имен модулей в имена их компонентов.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-162">This examples shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="1ccc3-163">Команда вызывает метод **Split** строк.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-163">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="1ccc3-164">Три команды используют различный синтаксис, но они эквивалентны и являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-164">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="1ccc3-165">Первая команда использует традиционный синтаксис, который включает блок сценария и текущий оператор Object `$_` .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-165">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="1ccc3-166">Точечный синтаксис применяется для указания метода, а аргумент разделителя заключается в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-166">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="1ccc3-167">Вторая команда использует параметр **MemberName** , чтобы указать метод **Split** , и параметр **ArgumentName** для определения точки (".") в качестве разделителя разбиения.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-167">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="1ccc3-168">Третья команда использует псевдоним **foreach** `ForEach-Object` командлета и опускает имена параметров **MemberName** и **ArgumentList** , которые являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-168">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="1ccc3-169">Пример 8. Использование ForEach-Object с двумя блоками сценариев</span><span class="sxs-lookup"><span data-stu-id="1ccc3-169">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="1ccc3-170">В этом примере мы передаем два блока сценариев по положению.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-170">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="1ccc3-171">Все блоки скрипта привязываются к параметру **Process** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-171">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="1ccc3-172">Однако они обрабатываются так, как будто они были переданы в параметры **Begin** и **Process** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-172">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="1ccc3-173">Пример 9. Использование ForEach-Object с более чем двумя блоками сценариев</span><span class="sxs-lookup"><span data-stu-id="1ccc3-173">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="1ccc3-174">В этом примере мы передаем два блока сценариев по положению.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-174">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="1ccc3-175">Все блоки скрипта привязываются к параметру **Process** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-175">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="1ccc3-176">Однако они обрабатываются так, как будто они были переданы в параметры **Begin** , **Process** и **End** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-176">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="1ccc3-177">Первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-177">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="1ccc3-178">Пример 10. Запуск нескольких блоков скрипта для каждого элемента конвейера</span><span class="sxs-lookup"><span data-stu-id="1ccc3-178">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="1ccc3-179">Как показано в предыдущем примере, несколько блоков скрипта, переданных с помощью параметра **Process** , сопоставляются с параметрами **Begin** и **End** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-179">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="1ccc3-180">Чтобы избежать этого сопоставления, необходимо предоставить явные значения для параметров **Begin** и **End** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-180">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

## <span data-ttu-id="1ccc3-181">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ccc3-181">Parameters</span></span>

### <span data-ttu-id="1ccc3-182">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="1ccc3-182">-ArgumentList</span></span>

<span data-ttu-id="1ccc3-183">Задает массив аргументов для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-183">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="1ccc3-184">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-184">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="1ccc3-185">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-185">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-186">-Begin</span><span class="sxs-lookup"><span data-stu-id="1ccc3-186">-Begin</span></span>

<span data-ttu-id="1ccc3-187">Задает блок скрипта, который выполняется перед тем, как этот командлет обрабатывает все входные объекты.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-187">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="1ccc3-188">Этот блок сценария выполняется только один раз для всего конвейера.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-188">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="1ccc3-189">Дополнительные сведения о `begin` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-189">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-190">-End</span><span class="sxs-lookup"><span data-stu-id="1ccc3-190">-End</span></span>

<span data-ttu-id="1ccc3-191">Задает блок скрипта, который запускается после того, как этот командлет обрабатывает все входные объекты.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-191">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="1ccc3-192">Этот блок сценария выполняется только один раз для всего конвейера.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-192">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="1ccc3-193">Дополнительные сведения о `end` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-193">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1ccc3-194">-InputObject</span></span>

<span data-ttu-id="1ccc3-195">Задает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-195">Specifies the input objects.</span></span> <span data-ttu-id="1ccc3-196">`ForEach-Object` выполняет блок скрипта или инструкцию Operation для каждого входного объекта.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-196">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="1ccc3-197">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-197">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="1ccc3-198">При использовании параметра **InputObject** с параметром `ForEach-Object` , а не с результатами команды трубопроводов в `ForEach-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-198">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="1ccc3-199">Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-199">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="1ccc3-200">Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `ForEach-Object` использовать для выполнения операций с коллекцией объектов для объектов, имеющих определенные значения в определенных свойствах, `ForEach-Object` в конвейере, как показано в примерах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-200">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="1ccc3-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="1ccc3-201">-MemberName</span></span>

<span data-ttu-id="1ccc3-202">Указывает свойство, которое необходимо получить, или метод, который требуется вызвать.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-202">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="1ccc3-203">Подстановочные знаки разрешены, но работают только в том случае, если результирующая строка разрешается в уникальное значение.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-203">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="1ccc3-204">Если, например, выполняется `Get-Process | ForEach -MemberName *Name` несколько элементов с именем, содержащим имя строки, например свойства **processName** и **Name** , команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-204">If, for example, you run `Get-Process | ForEach -MemberName *Name`, and more than one member exists with a name that contains the string Name, such as the **ProcessName** and **Name** properties, the command fails.</span></span>

<span data-ttu-id="1ccc3-205">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1ccc3-206">-Process</span><span class="sxs-lookup"><span data-stu-id="1ccc3-206">-Process</span></span>

<span data-ttu-id="1ccc3-207">Указывает операцию, которая выполняется с каждым входным объектом.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-207">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="1ccc3-208">Этот блок скрипта выполняется для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-208">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="1ccc3-209">Дополнительные сведения о `process` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-209">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="1ccc3-210">Если параметру **Process** предоставлено несколько блоков скрипта, первый блок сценария всегда сопоставляется с `begin` блоком.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-210">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="1ccc3-211">При наличии только двух блоков сценариев второй блок сопоставляется с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-211">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="1ccc3-212">При наличии трех или более блоков сценариев первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-212">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-213">-Ремаинингскриптс</span><span class="sxs-lookup"><span data-stu-id="1ccc3-213">-RemainingScripts</span></span>

<span data-ttu-id="1ccc3-214">Задает все блоки скриптов, которые не выполняются параметром **Process** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-214">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="1ccc3-215">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1ccc3-216">-Confirm</span></span>

<span data-ttu-id="1ccc3-217">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-217">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1ccc3-218">-WhatIf</span></span>

<span data-ttu-id="1ccc3-219">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-219">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1ccc3-220">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-220">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ccc3-221">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1ccc3-221">CommonParameters</span></span>

<span data-ttu-id="1ccc3-222">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ccc3-223">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ccc3-224">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1ccc3-224">Inputs</span></span>

### <span data-ttu-id="1ccc3-225">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1ccc3-225">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1ccc3-226">В этот командлет можно передать по конвейеру любой объект.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-226">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="1ccc3-227">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1ccc3-227">Outputs</span></span>

### <span data-ttu-id="1ccc3-228">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1ccc3-228">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1ccc3-229">Этот командлет возвращает объекты, определяемые входными данными.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-229">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="1ccc3-230">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ccc3-230">Notes</span></span>

- <span data-ttu-id="1ccc3-231">`ForEach-Object`Командлет работает во многом подобно оператору **foreach** , за исключением того, что нельзя передавать входные данные оператору **foreach** .</span><span class="sxs-lookup"><span data-stu-id="1ccc3-231">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="1ccc3-232">Дополнительные сведения об операторе **foreach** см. в разделе [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-232">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="1ccc3-233">Начиная с PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-233">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="1ccc3-234">Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="1ccc3-234">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="1ccc3-235">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1ccc3-235">Related links</span></span>

[<span data-ttu-id="1ccc3-236">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-236">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="1ccc3-237">Where-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-237">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="1ccc3-238">Group-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-238">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="1ccc3-239">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="1ccc3-239">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="1ccc3-240">New-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-240">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="1ccc3-241">Select-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-241">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="1ccc3-242">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-242">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="1ccc3-243">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="1ccc3-243">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
