---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: a025432e8aed93f6668c676161c21377d0ba225c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230401"
---
# <span data-ttu-id="b9dc0-103">Format-List</span><span class="sxs-lookup"><span data-stu-id="b9dc0-103">Format-List</span></span>

## <span data-ttu-id="b9dc0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b9dc0-104">SYNOPSIS</span></span>
<span data-ttu-id="b9dc0-105">Форматирует вывод как список свойств, в котором каждое свойство отображается на новой строке.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-105">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="b9dc0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9dc0-106">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="b9dc0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9dc0-107">DESCRIPTION</span></span>

<span data-ttu-id="b9dc0-108">`Format-List`Командлет форматирует выходные данные команды в виде списка свойств, в которых каждое свойство отображается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-108">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="b9dc0-109">Можно использовать `Format-List` для форматирования и вывода всех или выбранных свойств объекта в виде списка (Format-List \*).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-109">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="b9dc0-110">Так как для каждого элемента в списке доступно больше места, чем в таблице, PowerShell отображает больше свойств объекта в списке, и значения свойств менее вероятно будут обрезаны.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-110">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="b9dc0-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="b9dc0-111">EXAMPLES</span></span>

### <span data-ttu-id="b9dc0-112">Пример 1. форматирование компьютерных служб</span><span class="sxs-lookup"><span data-stu-id="b9dc0-112">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="b9dc0-113">Эта команда форматирует сведения о службах на компьютере в виде списка.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-113">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="b9dc0-114">По умолчанию сведения о службах форматируются в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-114">By default, the services are formatted as a table.</span></span> <span data-ttu-id="b9dc0-115">`Get-Service`Командлет возвращает объекты, представляющие службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-115">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="b9dc0-116">Оператор конвейера (|) передает результаты по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-116">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="b9dc0-117">Затем `Format-List` команда форматирует сведения о службе в списке и отправляет их в выходной командлет по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-117">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="b9dc0-118">Пример 2. форматирование файлов PS1XML</span><span class="sxs-lookup"><span data-stu-id="b9dc0-118">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="b9dc0-119">Эти команды отображают сведения о файлах PS1XML в каталоге PowerShell в виде списка.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-119">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="b9dc0-120">Первая команда получает объекты, представляющие файлы, и сохраняет их в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-120">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="b9dc0-121">Вторая команда использует `Format-List` для форматирования сведений об объектах, хранящихся в `$A` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-121">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="b9dc0-122">Эта команда использует параметр **InputObject** для передачи переменной в `Format-List` , который затем отправляет форматированные выходные данные в выходной командлет по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-122">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="b9dc0-123">Пример 3. форматирование свойств процесса по имени</span><span class="sxs-lookup"><span data-stu-id="b9dc0-123">Example 3: Format process properties by name</span></span>

<span data-ttu-id="b9dc0-124">Эта команда отображает имя, базовый приоритет и класс приоритета каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-124">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="b9dc0-125">Он использует `Get-Process` командлет для получения объекта, представляющего каждый процесс.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-125">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="b9dc0-126">Оператор конвейера (|) передает объекты процесса через конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-126">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="b9dc0-127">`Format-List` Форматирует процессы в виде списка указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-127">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="b9dc0-128">Имя параметра *Свойства* является необязательным, поэтому его можно опустить.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-128">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="b9dc0-129">Пример 4. форматирование всех свойств процесса</span><span class="sxs-lookup"><span data-stu-id="b9dc0-129">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="b9dc0-130">Эта команда отображает все свойства процесса Winlogon.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-130">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="b9dc0-131">Для получения объекта, представляющего процесс Winlogon, используется командлет Get-Process.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-131">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="b9dc0-132">Оператор конвейера (|) передает объект процесса Winlogon через конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-132">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="b9dc0-133">Команда использует параметр *Property* для указания свойств и \* для указания всех свойств.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-133">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="b9dc0-134">Поскольку имя параметра *Свойства* является необязательным, его можно опустить и ввести команду как `Format-List *` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-134">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="b9dc0-135">`Format-List` автоматически отправляет результаты в командлет вывода по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-135">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="b9dc0-136">Пример 5. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="b9dc0-136">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="b9dc0-137">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-137">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="b9dc0-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9dc0-138">PARAMETERS</span></span>

### <span data-ttu-id="b9dc0-139">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="b9dc0-139">-DisplayError</span></span>

<span data-ttu-id="b9dc0-140">Указывает, что этот командлет отображает ошибки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-140">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="b9dc0-141">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-141">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9dc0-142">-Expand</span><span class="sxs-lookup"><span data-stu-id="b9dc0-142">-Expand</span></span>

<span data-ttu-id="b9dc0-143">Задает отформатированный объект коллекции, а также объекты в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-143">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="b9dc0-144">Этот параметр служит для форматирования объектов, поддерживающих интерфейс ICollection (System.Collections).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-144">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="b9dc0-145">По умолчанию используется значение EnumOnly.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-145">The default value is EnumOnly.</span></span> <span data-ttu-id="b9dc0-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b9dc0-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b9dc0-147">Енумонли.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-147">EnumOnly.</span></span> <span data-ttu-id="b9dc0-148">отображаются свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-148">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="b9dc0-149">Кореонли.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-149">CoreOnly.</span></span> <span data-ttu-id="b9dc0-150">отображаются свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-150">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="b9dc0-151">Both.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-151">Both.</span></span> <span data-ttu-id="b9dc0-152">отображаются свойства объекта коллекции и свойства объектов, содержащихся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-152">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9dc0-153">-Force</span><span class="sxs-lookup"><span data-stu-id="b9dc0-153">-Force</span></span>

<span data-ttu-id="b9dc0-154">Указывает, что этот командлет отображает все сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-154">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="b9dc0-155">Используйте с параметром **DisplayError** или **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-155">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="b9dc0-156">По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-156">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9dc0-157">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="b9dc0-157">-GroupBy</span></span>

<span data-ttu-id="b9dc0-158">Задает выходные данные в группах на основе общего свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-158">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="b9dc0-159">Введите выражение или свойство вывода.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-159">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="b9dc0-160">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-160">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="b9dc0-161">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-161">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b9dc0-162">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="b9dc0-162">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b9dc0-163">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-163">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b9dc0-164">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-164">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b9dc0-165">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-165">FormatString - `<string>`</span></span>

<span data-ttu-id="b9dc0-166">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-166">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9dc0-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9dc0-167">-InputObject</span></span>

<span data-ttu-id="b9dc0-168">Задает объекты, подлежащие форматированию.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-168">Specifies the objects to be formatted.</span></span> <span data-ttu-id="b9dc0-169">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-169">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b9dc0-170">-Property</span><span class="sxs-lookup"><span data-stu-id="b9dc0-170">-Property</span></span>

<span data-ttu-id="b9dc0-171">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-171">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="b9dc0-172">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-172">Wildcards are permitted.</span></span>

<span data-ttu-id="b9dc0-173">Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-173">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="b9dc0-174">Имя параметра "свойство" является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-174">The parameter name "Property" is optional.</span></span> <span data-ttu-id="b9dc0-175">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="b9dc0-176">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-176">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="b9dc0-177">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-177">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b9dc0-178">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="b9dc0-178">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b9dc0-179">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-179">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b9dc0-180">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-180">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b9dc0-181">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9dc0-181">FormatString - `<string>`</span></span>

<span data-ttu-id="b9dc0-182">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-182">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b9dc0-183">-ShowError</span><span class="sxs-lookup"><span data-stu-id="b9dc0-183">-ShowError</span></span>

<span data-ttu-id="b9dc0-184">Указывает, что командлет отправляет ошибки через конвейер.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-184">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="b9dc0-185">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-185">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9dc0-186">-View</span><span class="sxs-lookup"><span data-stu-id="b9dc0-186">-View</span></span>

<span data-ttu-id="b9dc0-187">Указывает имя альтернативного формата или представления списка.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-187">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="b9dc0-188">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-188">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="b9dc0-189">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b9dc0-189">CommonParameters</span></span>

<span data-ttu-id="b9dc0-190">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9dc0-191">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9dc0-192">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b9dc0-192">INPUTS</span></span>

### <span data-ttu-id="b9dc0-193">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b9dc0-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b9dc0-194">Любой объект можно передать по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-194">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="b9dc0-195">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b9dc0-195">OUTPUTS</span></span>

### <span data-ttu-id="b9dc0-196">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="b9dc0-196">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="b9dc0-197">`Format-List` Возвращает объекты формата, представляющие список.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-197">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="b9dc0-198">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b9dc0-198">NOTES</span></span>

<span data-ttu-id="b9dc0-199">Вы также можете ссылаться на Format-List по его встроенному псевдониму FL.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-199">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="b9dc0-200">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b9dc0-200">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="b9dc0-201">Командлеты формата, такие как `Format-List` , упорядочивают отображаемые данные, но не отображают их.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-201">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="b9dc0-202">Данные отображаются выходными функциями PowerShell и командлетами, содержащими команду Out (командлеты Out), например `Out-Host` или `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-202">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="b9dc0-203">Если командлет format не используется, PowerShell применяет этот формат по умолчанию для каждого отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-203">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="b9dc0-204">Параметр **GroupBy** предполагает, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-204">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="b9dc0-205">Используйте Sort-Object перед использованием `Format-List` для группирования объектов.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-205">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="b9dc0-206">Параметр **View** позволяет указать альтернативный формат для таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-206">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="b9dc0-207">Можно использовать представления, определенные в `*.format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать командлет Update-FormatData, чтобы включить их в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-207">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="b9dc0-208">Альтернативное представление для параметра **представления** должно использовать формат списка, в противном случае команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b9dc0-208">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="b9dc0-209">Если альтернативное представление является таблицей, используйте `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-209">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="b9dc0-210">Если альтернативное представление не является списком или таблицей, используйте `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="b9dc0-210">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="b9dc0-211">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b9dc0-211">RELATED LINKS</span></span>

[<span data-ttu-id="b9dc0-212">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="b9dc0-212">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="b9dc0-213">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b9dc0-213">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="b9dc0-214">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b9dc0-214">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="b9dc0-215">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b9dc0-215">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="b9dc0-216">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b9dc0-216">Format-Wide</span></span>](Format-Wide.md)
