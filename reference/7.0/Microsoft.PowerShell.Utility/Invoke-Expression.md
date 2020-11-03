---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: d8f7df3a4c7197b6cf62eecc0b0b314d9668de90
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225514"
---
# <span data-ttu-id="6580c-103">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="6580c-103">Invoke-Expression</span></span>

## <span data-ttu-id="6580c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6580c-104">SYNOPSIS</span></span>
<span data-ttu-id="6580c-105">Выполняет команды или выражения на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6580c-105">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="6580c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6580c-106">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="6580c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6580c-107">DESCRIPTION</span></span>

<span data-ttu-id="6580c-108">`Invoke-Expression`Командлет вычисляет или выполняет указанную строку в качестве команды и возвращает результаты выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="6580c-108">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="6580c-109">Без `Invoke-Expression` изменений строка, отправленная в командной строке, возвращается (вывод) не изменяется.</span><span class="sxs-lookup"><span data-stu-id="6580c-109">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="6580c-110">Выражения вычисляются и выполняются в текущей области.</span><span class="sxs-lookup"><span data-stu-id="6580c-110">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="6580c-111">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="6580c-111">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="6580c-112">При использовании `Invoke-Expression` командлета в скриптах примите меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="6580c-112">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="6580c-113">При использовании `Invoke-Expression` для выполнения команды, введенной пользователем, убедитесь, что команда является надежной для запуска перед ее запуском.</span><span class="sxs-lookup"><span data-stu-id="6580c-113">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="6580c-114">Как правило, при создании сценариев лучше предусматривать предварительно определенные варианты входных данных, не допуская ввода данных в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="6580c-114">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="6580c-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="6580c-115">EXAMPLES</span></span>

### <span data-ttu-id="6580c-116">Пример 1. Вычисление выражения</span><span class="sxs-lookup"><span data-stu-id="6580c-116">Example 1: Evaluate an expression</span></span>

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

<span data-ttu-id="6580c-117">В этом примере демонстрируется использование `Invoke-Expression` для вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="6580c-117">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="6580c-118">Без `Invoke-Expression` выражение печатается, но не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="6580c-118">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="6580c-119">Первая команда присваивает `Get-Process` переменной значение (String) `$Command` .</span><span class="sxs-lookup"><span data-stu-id="6580c-119">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="6580c-120">Вторая команда демонстрирует результат ввода имени переменной в командной строке.</span><span class="sxs-lookup"><span data-stu-id="6580c-120">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="6580c-121">PowerShell возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="6580c-121">PowerShell echoes the string.</span></span>

<span data-ttu-id="6580c-122">Третья команда использует `Invoke-Expression` для вычисления строки.</span><span class="sxs-lookup"><span data-stu-id="6580c-122">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="6580c-123">Пример 2. Запуск скрипта на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="6580c-123">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="6580c-124">Эти команды используют `Invoke-Expression` для запуска скрипта, TestScript.ps1 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6580c-124">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="6580c-125">Команды эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="6580c-125">The two commands are equivalent.</span></span> <span data-ttu-id="6580c-126">Первый использует параметр **Command** для указания выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="6580c-126">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="6580c-127">Во втором используется оператор конвейера ( `|` ) для отправки строки команды `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="6580c-127">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="6580c-128">Пример 3. выполнение команды в переменной</span><span class="sxs-lookup"><span data-stu-id="6580c-128">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="6580c-129">В этом примере выполняется Командная строка, сохраненная в `$Command` переменной.</span><span class="sxs-lookup"><span data-stu-id="6580c-129">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="6580c-130">Командная строка заключается в одинарные кавычки, так как включает переменную, `$_` которая представляет текущий объект.</span><span class="sxs-lookup"><span data-stu-id="6580c-130">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="6580c-131">Если он заключен в двойные кавычки, `$_` переменная будет заменена ее значением до сохранения в `$Command` переменной.</span><span class="sxs-lookup"><span data-stu-id="6580c-131">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="6580c-132">Пример 4. получение и запуск примера справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="6580c-132">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="6580c-133">Эта команда извлекает и выполняет первый пример в `Get-EventLog` разделе справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="6580c-133">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="6580c-134">Чтобы выполнить пример другого командлета, измените значение `$Cmdlet_name` переменной на имя командлета.</span><span class="sxs-lookup"><span data-stu-id="6580c-134">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="6580c-135">И измените `$Example_number` переменную на номер примера, который требуется запустить.</span><span class="sxs-lookup"><span data-stu-id="6580c-135">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="6580c-136">Команда завершается ошибкой, если номер примера недопустим.</span><span class="sxs-lookup"><span data-stu-id="6580c-136">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="6580c-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6580c-137">PARAMETERS</span></span>

### <span data-ttu-id="6580c-138">-Command</span><span class="sxs-lookup"><span data-stu-id="6580c-138">-Command</span></span>

<span data-ttu-id="6580c-139">Указывает команду или выражение для выполнения.</span><span class="sxs-lookup"><span data-stu-id="6580c-139">Specifies the command or expression to run.</span></span> <span data-ttu-id="6580c-140">Введите команду или выражение либо укажите переменную, которая содержит команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="6580c-140">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="6580c-141">Параметр **команды** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6580c-141">The **Command** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6580c-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6580c-142">CommonParameters</span></span>

<span data-ttu-id="6580c-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6580c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6580c-144">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6580c-144">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6580c-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6580c-145">INPUTS</span></span>

### <span data-ttu-id="6580c-146">System. String или PSObject</span><span class="sxs-lookup"><span data-stu-id="6580c-146">System.String or PSObject</span></span>

<span data-ttu-id="6580c-147">Объект, представляющий команду, можно передать по конвейеру `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="6580c-147">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="6580c-148">Используйте `$Input` автоматическую переменную для представления входных объектов в команде.</span><span class="sxs-lookup"><span data-stu-id="6580c-148">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="6580c-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6580c-149">OUTPUTS</span></span>

### <span data-ttu-id="6580c-150">PSObject</span><span class="sxs-lookup"><span data-stu-id="6580c-150">PSObject</span></span>

<span data-ttu-id="6580c-151">Возвращает выходные данные, формируемые вызванной командой (значение параметра **команды** ).</span><span class="sxs-lookup"><span data-stu-id="6580c-151">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="6580c-152">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6580c-152">NOTES</span></span>

<span data-ttu-id="6580c-153">В большинстве случаев вы вызываете выражения с помощью оператора Call PowerShell и достигаете тех же результатов.</span><span class="sxs-lookup"><span data-stu-id="6580c-153">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="6580c-154">Оператор Call является более безопасным методом.</span><span class="sxs-lookup"><span data-stu-id="6580c-154">The call operator is a safer method.</span></span> <span data-ttu-id="6580c-155">Дополнительные сведения см. в разделе [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="6580c-155">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="6580c-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6580c-156">RELATED LINKS</span></span>

[<span data-ttu-id="6580c-157">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="6580c-157">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="6580c-158">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="6580c-158">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)
