---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: d8410fbc2d3f29f0726f84ab151993a60ce95434
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600183"
---
# <span data-ttu-id="c2cf1-102">Format-List</span><span class="sxs-lookup"><span data-stu-id="c2cf1-102">Format-List</span></span>

## <span data-ttu-id="c2cf1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c2cf1-103">SYNOPSIS</span></span>
<span data-ttu-id="c2cf1-104">Форматирует вывод как список свойств, в котором каждое свойство отображается на новой строке.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-104">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="c2cf1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c2cf1-105">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="c2cf1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c2cf1-106">DESCRIPTION</span></span>

<span data-ttu-id="c2cf1-107">`Format-List`Командлет форматирует выходные данные команды в виде списка свойств, в которых каждое свойство отображается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-107">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="c2cf1-108">Можно использовать `Format-List` для форматирования и вывода всех или выбранных свойств объекта в виде списка (Format-List \*).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-108">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="c2cf1-109">Так как для каждого элемента в списке доступно больше места, чем в таблице, PowerShell отображает больше свойств объекта в списке, и значения свойств менее вероятно будут обрезаны.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-109">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="c2cf1-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="c2cf1-110">EXAMPLES</span></span>

### <span data-ttu-id="c2cf1-111">Пример 1. форматирование компьютерных служб</span><span class="sxs-lookup"><span data-stu-id="c2cf1-111">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="c2cf1-112">Эта команда форматирует сведения о службах на компьютере в виде списка.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-112">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="c2cf1-113">По умолчанию сведения о службах форматируются в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-113">By default, the services are formatted as a table.</span></span> <span data-ttu-id="c2cf1-114">`Get-Service`Командлет возвращает объекты, представляющие службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-114">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="c2cf1-115">Оператор конвейера (|) передает результаты по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-115">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="c2cf1-116">Затем `Format-List` команда форматирует сведения о службе в списке и отправляет их в выходной командлет по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-116">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c2cf1-117">Пример 2. форматирование файлов PS1XML</span><span class="sxs-lookup"><span data-stu-id="c2cf1-117">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="c2cf1-118">Эти команды отображают сведения о файлах PS1XML в каталоге PowerShell в виде списка.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-118">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="c2cf1-119">Первая команда получает объекты, представляющие файлы, и сохраняет их в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-119">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="c2cf1-120">Вторая команда использует `Format-List` для форматирования сведений об объектах, хранящихся в `$A` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-120">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="c2cf1-121">Эта команда использует параметр **InputObject** для передачи переменной в `Format-List` , который затем отправляет форматированные выходные данные в выходной командлет по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-121">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c2cf1-122">Пример 3. форматирование свойств процесса по имени</span><span class="sxs-lookup"><span data-stu-id="c2cf1-122">Example 3: Format process properties by name</span></span>

<span data-ttu-id="c2cf1-123">Эта команда отображает имя, базовый приоритет и класс приоритета каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-123">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="c2cf1-124">Он использует `Get-Process` командлет для получения объекта, представляющего каждый процесс.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-124">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="c2cf1-125">Оператор конвейера (|) передает объекты процесса через конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-125">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="c2cf1-126">`Format-List` Форматирует процессы в виде списка указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-126">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="c2cf1-127">Имя параметра *Свойства* является необязательным, поэтому его можно опустить.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-127">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="c2cf1-128">Пример 4. форматирование всех свойств процесса</span><span class="sxs-lookup"><span data-stu-id="c2cf1-128">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="c2cf1-129">Эта команда отображает все свойства процесса Winlogon.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-129">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="c2cf1-130">Для получения объекта, представляющего процесс Winlogon, используется командлет Get-Process.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-130">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="c2cf1-131">Оператор конвейера (|) передает объект процесса Winlogon через конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-131">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="c2cf1-132">Команда использует параметр *Property* для указания свойств и \* для указания всех свойств.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-132">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="c2cf1-133">Поскольку имя параметра *Свойства* является необязательным, его можно опустить и ввести команду как `Format-List *` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-133">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="c2cf1-134">`Format-List` автоматически отправляет результаты в командлет вывода по умолчанию для вывода.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-134">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="c2cf1-135">Пример 5. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="c2cf1-135">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="c2cf1-136">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-136">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

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

## <span data-ttu-id="c2cf1-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c2cf1-137">PARAMETERS</span></span>

### <span data-ttu-id="c2cf1-138">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="c2cf1-138">-DisplayError</span></span>

<span data-ttu-id="c2cf1-139">Указывает, что этот командлет отображает ошибки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-139">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="c2cf1-140">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-140">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="c2cf1-141">-Expand</span><span class="sxs-lookup"><span data-stu-id="c2cf1-141">-Expand</span></span>

<span data-ttu-id="c2cf1-142">Задает отформатированный объект коллекции, а также объекты в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-142">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="c2cf1-143">Этот параметр служит для форматирования объектов, поддерживающих интерфейс ICollection (System.Collections).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-143">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="c2cf1-144">По умолчанию используется значение EnumOnly.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-144">The default value is EnumOnly.</span></span> <span data-ttu-id="c2cf1-145">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c2cf1-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c2cf1-146">Енумонли.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-146">EnumOnly.</span></span> <span data-ttu-id="c2cf1-147">отображаются свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-147">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="c2cf1-148">Кореонли.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-148">CoreOnly.</span></span> <span data-ttu-id="c2cf1-149">отображаются свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-149">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="c2cf1-150">Both.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-150">Both.</span></span> <span data-ttu-id="c2cf1-151">отображаются свойства объекта коллекции и свойства объектов, содержащихся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-151">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

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

### <span data-ttu-id="c2cf1-152">-Force</span><span class="sxs-lookup"><span data-stu-id="c2cf1-152">-Force</span></span>

<span data-ttu-id="c2cf1-153">Указывает, что этот командлет отображает все сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-153">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="c2cf1-154">Используйте с параметром **DisplayError** или **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-154">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="c2cf1-155">По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-155">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="c2cf1-156">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="c2cf1-156">-GroupBy</span></span>

<span data-ttu-id="c2cf1-157">Задает выходные данные в группах на основе общего свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-157">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="c2cf1-158">Введите выражение или свойство вывода.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-158">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="c2cf1-159">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-159">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="c2cf1-160">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-160">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="c2cf1-161">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="c2cf1-161">Valid key-value pairs are:</span></span>

- <span data-ttu-id="c2cf1-162">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-162">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="c2cf1-163">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-163">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="c2cf1-164">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-164">FormatString - `<string>`</span></span>

<span data-ttu-id="c2cf1-165">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-165">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="c2cf1-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c2cf1-166">-InputObject</span></span>

<span data-ttu-id="c2cf1-167">Задает объекты, подлежащие форматированию.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-167">Specifies the objects to be formatted.</span></span> <span data-ttu-id="c2cf1-168">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-168">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="c2cf1-169">-Property</span><span class="sxs-lookup"><span data-stu-id="c2cf1-169">-Property</span></span>

<span data-ttu-id="c2cf1-170">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-170">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="c2cf1-171">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-171">Wildcards are permitted.</span></span>

<span data-ttu-id="c2cf1-172">Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-172">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="c2cf1-173">Имя параметра "свойство" является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-173">The parameter name "Property" is optional.</span></span> <span data-ttu-id="c2cf1-174">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-174">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="c2cf1-175">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="c2cf1-176">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="c2cf1-177">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="c2cf1-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="c2cf1-178">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-178">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="c2cf1-179">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-179">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="c2cf1-180">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="c2cf1-180">FormatString - `<string>`</span></span>

<span data-ttu-id="c2cf1-181">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-181">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="c2cf1-182">-ShowError</span><span class="sxs-lookup"><span data-stu-id="c2cf1-182">-ShowError</span></span>

<span data-ttu-id="c2cf1-183">Указывает, что командлет отправляет ошибки через конвейер.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-183">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="c2cf1-184">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-184">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="c2cf1-185">-View</span><span class="sxs-lookup"><span data-stu-id="c2cf1-185">-View</span></span>

<span data-ttu-id="c2cf1-186">Указывает имя альтернативного формата или представления списка.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-186">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="c2cf1-187">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-187">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="c2cf1-188">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c2cf1-188">CommonParameters</span></span>

<span data-ttu-id="c2cf1-189">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c2cf1-190">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c2cf1-191">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c2cf1-191">INPUTS</span></span>

### <span data-ttu-id="c2cf1-192">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="c2cf1-192">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c2cf1-193">Любой объект можно передать по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-193">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="c2cf1-194">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c2cf1-194">OUTPUTS</span></span>

### <span data-ttu-id="c2cf1-195">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="c2cf1-195">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="c2cf1-196">`Format-List` Возвращает объекты формата, представляющие список.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-196">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="c2cf1-197">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c2cf1-197">NOTES</span></span>

<span data-ttu-id="c2cf1-198">Вы также можете ссылаться на Format-List по его встроенному псевдониму FL.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-198">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="c2cf1-199">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf1-199">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="c2cf1-200">Командлеты формата, такие как `Format-List` , упорядочивают отображаемые данные, но не отображают их.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-200">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="c2cf1-201">Данные отображаются выходными функциями PowerShell и командлетами, содержащими команду Out (командлеты Out), например `Out-Host` или `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-201">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="c2cf1-202">Если командлет format не используется, PowerShell применяет этот формат по умолчанию для каждого отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-202">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="c2cf1-203">Параметр **GroupBy** предполагает, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-203">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="c2cf1-204">Используйте Sort-Object перед использованием `Format-List` для группирования объектов.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-204">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="c2cf1-205">Параметр **View** позволяет указать альтернативный формат для таблицы.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-205">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="c2cf1-206">Можно использовать представления, определенные в `*.format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать командлет Update-FormatData, чтобы включить их в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-206">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="c2cf1-207">Альтернативное представление для параметра **представления** должно использовать формат списка, в противном случае команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c2cf1-207">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="c2cf1-208">Если альтернативное представление является таблицей, используйте `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-208">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="c2cf1-209">Если альтернативное представление не является списком или таблицей, используйте `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="c2cf1-209">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="c2cf1-210">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c2cf1-210">RELATED LINKS</span></span>

[<span data-ttu-id="c2cf1-211">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="c2cf1-211">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="c2cf1-212">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="c2cf1-212">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="c2cf1-213">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="c2cf1-213">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="c2cf1-214">Format-Table</span><span class="sxs-lookup"><span data-stu-id="c2cf1-214">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="c2cf1-215">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="c2cf1-215">Format-Wide</span></span>](Format-Wide.md)
