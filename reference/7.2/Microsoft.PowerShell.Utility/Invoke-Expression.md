---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: 65ccc37b1c9122d54f3caf85f4546e1381558ca9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602486"
---
# <span data-ttu-id="1cff1-102">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="1cff1-102">Invoke-Expression</span></span>

## <span data-ttu-id="1cff1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1cff1-103">SYNOPSIS</span></span>
<span data-ttu-id="1cff1-104">Выполняет команды или выражения на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cff1-104">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="1cff1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1cff1-105">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="1cff1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1cff1-106">DESCRIPTION</span></span>

<span data-ttu-id="1cff1-107">`Invoke-Expression`Командлет вычисляет или выполняет указанную строку в качестве команды и возвращает результаты выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="1cff1-107">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="1cff1-108">Без `Invoke-Expression` изменений строка, отправленная в командной строке, возвращается (вывод) не изменяется.</span><span class="sxs-lookup"><span data-stu-id="1cff1-108">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="1cff1-109">Выражения вычисляются и выполняются в текущей области.</span><span class="sxs-lookup"><span data-stu-id="1cff1-109">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="1cff1-110">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="1cff1-110">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="1cff1-111">При использовании `Invoke-Expression` командлета в скриптах примите меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="1cff1-111">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="1cff1-112">При использовании `Invoke-Expression` для выполнения команды, введенной пользователем, убедитесь, что команда является надежной для запуска перед ее запуском.</span><span class="sxs-lookup"><span data-stu-id="1cff1-112">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="1cff1-113">Как правило, при создании сценариев лучше предусматривать предварительно определенные варианты входных данных, не допуская ввода данных в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="1cff1-113">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="1cff1-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="1cff1-114">EXAMPLES</span></span>

### <span data-ttu-id="1cff1-115">Пример 1. Вычисление выражения</span><span class="sxs-lookup"><span data-stu-id="1cff1-115">Example 1: Evaluate an expression</span></span>

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

<span data-ttu-id="1cff1-116">В этом примере демонстрируется использование `Invoke-Expression` для вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="1cff1-116">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="1cff1-117">Без `Invoke-Expression` выражение печатается, но не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="1cff1-117">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="1cff1-118">Первая команда присваивает `Get-Process` переменной значение (String) `$Command` .</span><span class="sxs-lookup"><span data-stu-id="1cff1-118">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="1cff1-119">Вторая команда демонстрирует результат ввода имени переменной в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1cff1-119">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="1cff1-120">PowerShell возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="1cff1-120">PowerShell echoes the string.</span></span>

<span data-ttu-id="1cff1-121">Третья команда использует `Invoke-Expression` для вычисления строки.</span><span class="sxs-lookup"><span data-stu-id="1cff1-121">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="1cff1-122">Пример 2. Запуск скрипта на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="1cff1-122">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="1cff1-123">Эти команды используют `Invoke-Expression` для запуска скрипта, TestScript.ps1 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cff1-123">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="1cff1-124">Команды эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="1cff1-124">The two commands are equivalent.</span></span> <span data-ttu-id="1cff1-125">Первый использует параметр **Command** для указания выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="1cff1-125">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="1cff1-126">Во втором используется оператор конвейера ( `|` ) для отправки строки команды `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="1cff1-126">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="1cff1-127">Пример 3. выполнение команды в переменной</span><span class="sxs-lookup"><span data-stu-id="1cff1-127">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="1cff1-128">В этом примере выполняется Командная строка, сохраненная в `$Command` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cff1-128">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="1cff1-129">Командная строка заключается в одинарные кавычки, так как включает переменную, `$_` которая представляет текущий объект.</span><span class="sxs-lookup"><span data-stu-id="1cff1-129">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="1cff1-130">Если он заключен в двойные кавычки, `$_` переменная будет заменена ее значением до сохранения в `$Command` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cff1-130">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="1cff1-131">Пример 4. получение и запуск примера справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="1cff1-131">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="1cff1-132">Эта команда извлекает и выполняет первый пример в `Get-EventLog` разделе справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="1cff1-132">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="1cff1-133">Чтобы выполнить пример другого командлета, измените значение `$Cmdlet_name` переменной на имя командлета.</span><span class="sxs-lookup"><span data-stu-id="1cff1-133">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="1cff1-134">И измените `$Example_number` переменную на номер примера, который требуется запустить.</span><span class="sxs-lookup"><span data-stu-id="1cff1-134">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="1cff1-135">Команда завершается ошибкой, если номер примера недопустим.</span><span class="sxs-lookup"><span data-stu-id="1cff1-135">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="1cff1-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1cff1-136">PARAMETERS</span></span>

### <span data-ttu-id="1cff1-137">-Command</span><span class="sxs-lookup"><span data-stu-id="1cff1-137">-Command</span></span>

<span data-ttu-id="1cff1-138">Указывает команду или выражение для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1cff1-138">Specifies the command or expression to run.</span></span> <span data-ttu-id="1cff1-139">Введите команду или выражение либо укажите переменную, которая содержит команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="1cff1-139">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="1cff1-140">Параметр **команды** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1cff1-140">The **Command** parameter is required.</span></span>

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

### <span data-ttu-id="1cff1-141">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1cff1-141">CommonParameters</span></span>

<span data-ttu-id="1cff1-142">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1cff1-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1cff1-143">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="1cff1-143">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1cff1-144">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1cff1-144">INPUTS</span></span>

### <span data-ttu-id="1cff1-145">System. String или PSObject</span><span class="sxs-lookup"><span data-stu-id="1cff1-145">System.String or PSObject</span></span>

<span data-ttu-id="1cff1-146">Объект, представляющий команду, можно передать по конвейеру `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="1cff1-146">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="1cff1-147">Используйте `$Input` автоматическую переменную для представления входных объектов в команде.</span><span class="sxs-lookup"><span data-stu-id="1cff1-147">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="1cff1-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1cff1-148">OUTPUTS</span></span>

### <span data-ttu-id="1cff1-149">PSObject</span><span class="sxs-lookup"><span data-stu-id="1cff1-149">PSObject</span></span>

<span data-ttu-id="1cff1-150">Возвращает выходные данные, формируемые вызванной командой (значение параметра **команды** ).</span><span class="sxs-lookup"><span data-stu-id="1cff1-150">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="1cff1-151">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1cff1-151">NOTES</span></span>

<span data-ttu-id="1cff1-152">В большинстве случаев вы вызываете выражения с помощью оператора Call PowerShell и достигаете тех же результатов.</span><span class="sxs-lookup"><span data-stu-id="1cff1-152">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="1cff1-153">Оператор Call является более безопасным методом.</span><span class="sxs-lookup"><span data-stu-id="1cff1-153">The call operator is a safer method.</span></span> <span data-ttu-id="1cff1-154">Дополнительные сведения см. в разделе [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="1cff1-154">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="1cff1-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1cff1-155">RELATED LINKS</span></span>

[<span data-ttu-id="1cff1-156">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="1cff1-156">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="1cff1-157">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="1cff1-157">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

