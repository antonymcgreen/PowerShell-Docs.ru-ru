---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: afc08b263d75f8a728ce6d64cc7ede0a639df196
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604281"
---
# <span data-ttu-id="fcb06-102">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="fcb06-102">Trace-Command</span></span>

## <span data-ttu-id="fcb06-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fcb06-103">SYNOPSIS</span></span>
<span data-ttu-id="fcb06-104">Настраивает и запускает трассировку указанного выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="fcb06-104">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="fcb06-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fcb06-105">SYNTAX</span></span>

### <span data-ttu-id="fcb06-106">"выражение" (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fcb06-106">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="fcb06-107">commandSet</span><span class="sxs-lookup"><span data-stu-id="fcb06-107">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="fcb06-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fcb06-108">DESCRIPTION</span></span>
<span data-ttu-id="fcb06-109">`Trace-Command`Командлет настраивает и запускает трассировку указанного выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="fcb06-109">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="fcb06-110">Он аналогичен командлету Set-TraceSource за тем исключением, что его действие распространяется только на указанную команду.</span><span class="sxs-lookup"><span data-stu-id="fcb06-110">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="fcb06-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="fcb06-111">EXAMPLES</span></span>

### <span data-ttu-id="fcb06-112">Пример 1. Обработка метаданных трассировки, привязка параметров и выражение</span><span class="sxs-lookup"><span data-stu-id="fcb06-112">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="fcb06-113">В этом примере запускается трассировка обработки метаданных, привязки параметров и создания и уничтожения `Get-Process Notepad` выражения.</span><span class="sxs-lookup"><span data-stu-id="fcb06-113">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="fcb06-114">Он использует параметр **Name** для указания источников трассировки, параметр **Expression** для указания команды и параметр **PSHost** для отправки выходных данных в консоль.</span><span class="sxs-lookup"><span data-stu-id="fcb06-114">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="fcb06-115">Поскольку параметры трассировки и параметры прослушивателя не указаны, команда использует значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="fcb06-115">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="fcb06-116">Все для параметров трассировки</span><span class="sxs-lookup"><span data-stu-id="fcb06-116">All for the tracing options</span></span>
- <span data-ttu-id="fcb06-117">Нет для параметров прослушивателя</span><span class="sxs-lookup"><span data-stu-id="fcb06-117">None for the listener options</span></span>

### <span data-ttu-id="fcb06-118">Пример 2. трассировка действий операций ParameterBinding оболочки</span><span class="sxs-lookup"><span data-stu-id="fcb06-118">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="fcb06-119">В этом примере отслеживаются действия **ParameterBinding оболочки** операций PowerShell во время обработки `Get-Alias` выражения, принимающего входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="fcb06-119">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="fcb06-120">В `Trace-Command` параметр **InputObject** передает объект в выражение, обрабатываемое во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-120">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="fcb06-121">Первая команда сохраняет строку `i*` в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="fcb06-121">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="fcb06-122">Вторая команда использует `Trace-Command` командлет с источником трассировки ParameterBinding оболочки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-122">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="fcb06-123">Параметр **PSHost** отправляет выходные данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="fcb06-123">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="fcb06-124">Обрабатываемое выражение имеет значение `Get-Alias $Input` , где `$Input` переменная связана с параметром **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="fcb06-124">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="fcb06-125">Параметр **InputObject** передает переменную в `$A` выражение.</span><span class="sxs-lookup"><span data-stu-id="fcb06-125">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="fcb06-126">По сути, команда, обрабатываемая во время трассировки, имеет значение `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="fcb06-126">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="fcb06-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fcb06-127">PARAMETERS</span></span>

### <span data-ttu-id="fcb06-128">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="fcb06-128">-ArgumentList</span></span>

<span data-ttu-id="fcb06-129">Указывает параметры и значения параметров для трассируемой команды.</span><span class="sxs-lookup"><span data-stu-id="fcb06-129">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="fcb06-130">Псевдоним для **ArgumentList** — **Args**.</span><span class="sxs-lookup"><span data-stu-id="fcb06-130">The alias for **ArgumentList** is **Args**.</span></span> <span data-ttu-id="fcb06-131">Эта функция особенно полезна для отладки динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="fcb06-131">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="fcb06-132">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="fcb06-132">For more information about the behavior of **ArgumentList**, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-133">-Command</span><span class="sxs-lookup"><span data-stu-id="fcb06-133">-Command</span></span>

<span data-ttu-id="fcb06-134">Указывает команду, обрабатываемую во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-134">Specifies a command that is being processed during the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-135">-Отладчик</span><span class="sxs-lookup"><span data-stu-id="fcb06-135">-Debugger</span></span>

<span data-ttu-id="fcb06-136">Указывает, что командлет отправляет выходные данные трассировки в отладчик.</span><span class="sxs-lookup"><span data-stu-id="fcb06-136">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="fcb06-137">Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fcb06-137">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="fcb06-138">Данный параметр также определяет прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fcb06-138">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="fcb06-139">-Expression</span><span class="sxs-lookup"><span data-stu-id="fcb06-139">-Expression</span></span>

<span data-ttu-id="fcb06-140">Указывает выражение, обрабатываемое во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-140">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="fcb06-141">Заключите выражение в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="fcb06-141">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-142">-FilePath</span><span class="sxs-lookup"><span data-stu-id="fcb06-142">-FilePath</span></span>

<span data-ttu-id="fcb06-143">Указывает файл, в который командлет отправляет выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-143">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="fcb06-144">Данный параметр также определяет прослушиватель трассировки файла.</span><span class="sxs-lookup"><span data-stu-id="fcb06-144">This parameter also selects the file trace listener.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-145">-Force</span><span class="sxs-lookup"><span data-stu-id="fcb06-145">-Force</span></span>

<span data-ttu-id="fcb06-146">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="fcb06-146">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="fcb06-147">Используется с параметром **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="fcb06-147">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="fcb06-148">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="fcb06-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="fcb06-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fcb06-149">-InputObject</span></span>

<span data-ttu-id="fcb06-150">Задает входные данные для выражения, обрабатываемого во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-150">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="fcb06-151">Можно ввести переменную, которая представляет выходные данные, принимаемые этим выражением, или передать объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fcb06-151">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="fcb06-152">-Листенероптион</span><span class="sxs-lookup"><span data-stu-id="fcb06-152">-ListenerOption</span></span>

<span data-ttu-id="fcb06-153">Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fcb06-153">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="fcb06-154">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fcb06-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fcb06-155">None</span><span class="sxs-lookup"><span data-stu-id="fcb06-155">None</span></span>
- <span data-ttu-id="fcb06-156">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="fcb06-156">LogicalOperationStack</span></span>
- <span data-ttu-id="fcb06-157">Дата и время</span><span class="sxs-lookup"><span data-stu-id="fcb06-157">DateTime</span></span>
- <span data-ttu-id="fcb06-158">Отметка времени</span><span class="sxs-lookup"><span data-stu-id="fcb06-158">Timestamp</span></span>
- <span data-ttu-id="fcb06-159">ProcessId</span><span class="sxs-lookup"><span data-stu-id="fcb06-159">ProcessId</span></span>
- <span data-ttu-id="fcb06-160"> ThreadId</span><span class="sxs-lookup"><span data-stu-id="fcb06-160">ThreadId</span></span>
- <span data-ttu-id="fcb06-161">Части</span><span class="sxs-lookup"><span data-stu-id="fcb06-161">Callstack</span></span>

<span data-ttu-id="fcb06-162">По умолчанию используется значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="fcb06-162">**None** is the default.</span></span>

<span data-ttu-id="fcb06-163">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="fcb06-163">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-164">-Name</span><span class="sxs-lookup"><span data-stu-id="fcb06-164">-Name</span></span>

<span data-ttu-id="fcb06-165">Указывает массив отслеживаемых компонентов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcb06-165">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="fcb06-166">Введите имя источника трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="fcb06-166">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="fcb06-167">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-167">Wildcards are permitted.</span></span> <span data-ttu-id="fcb06-168">Чтобы найти источники трассировки на компьютере, введите `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="fcb06-168">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-169">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="fcb06-169">-Option</span></span>

<span data-ttu-id="fcb06-170">Определяет тип трассируемых событий.</span><span class="sxs-lookup"><span data-stu-id="fcb06-170">Determines the type of events that are traced.</span></span> <span data-ttu-id="fcb06-171">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fcb06-171">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fcb06-172">None</span><span class="sxs-lookup"><span data-stu-id="fcb06-172">None</span></span>
- <span data-ttu-id="fcb06-173">Конструктор</span><span class="sxs-lookup"><span data-stu-id="fcb06-173">Constructor</span></span>
- <span data-ttu-id="fcb06-174">Dispose</span><span class="sxs-lookup"><span data-stu-id="fcb06-174">Dispose</span></span>
- <span data-ttu-id="fcb06-175">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="fcb06-175">Finalizer</span></span>
- <span data-ttu-id="fcb06-176">Метод</span><span class="sxs-lookup"><span data-stu-id="fcb06-176">Method</span></span>
- <span data-ttu-id="fcb06-177">Свойство</span><span class="sxs-lookup"><span data-stu-id="fcb06-177">Property</span></span>
- <span data-ttu-id="fcb06-178">Делегаты</span><span class="sxs-lookup"><span data-stu-id="fcb06-178">Delegates</span></span>
- <span data-ttu-id="fcb06-179">События</span><span class="sxs-lookup"><span data-stu-id="fcb06-179">Events</span></span>
- <span data-ttu-id="fcb06-180">Исключение</span><span class="sxs-lookup"><span data-stu-id="fcb06-180">Exception</span></span>
- <span data-ttu-id="fcb06-181">Блокировка</span><span class="sxs-lookup"><span data-stu-id="fcb06-181">Lock</span></span>
- <span data-ttu-id="fcb06-182">Ошибка</span><span class="sxs-lookup"><span data-stu-id="fcb06-182">Error</span></span>
- <span data-ttu-id="fcb06-183">Ошибки</span><span class="sxs-lookup"><span data-stu-id="fcb06-183">Errors</span></span>
- <span data-ttu-id="fcb06-184">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fcb06-184">Warning</span></span>
- <span data-ttu-id="fcb06-185">Подробный</span><span class="sxs-lookup"><span data-stu-id="fcb06-185">Verbose</span></span>
- <span data-ttu-id="fcb06-186">WriteLine</span><span class="sxs-lookup"><span data-stu-id="fcb06-186">WriteLine</span></span>
- <span data-ttu-id="fcb06-187">Данные</span><span class="sxs-lookup"><span data-stu-id="fcb06-187">Data</span></span>
- <span data-ttu-id="fcb06-188">Область</span><span class="sxs-lookup"><span data-stu-id="fcb06-188">Scope</span></span>
- <span data-ttu-id="fcb06-189">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="fcb06-189">ExecutionFlow</span></span>
- <span data-ttu-id="fcb06-190">Assert</span><span class="sxs-lookup"><span data-stu-id="fcb06-190">Assert</span></span>
- <span data-ttu-id="fcb06-191">Все</span><span class="sxs-lookup"><span data-stu-id="fcb06-191">All</span></span>

<span data-ttu-id="fcb06-192">По умолчанию используется значение All.</span><span class="sxs-lookup"><span data-stu-id="fcb06-192">All is the default.</span></span>

<span data-ttu-id="fcb06-193">Следующие значения являются комбинацией других значений:</span><span class="sxs-lookup"><span data-stu-id="fcb06-193">The following values are combinations of other values:</span></span>

- <span data-ttu-id="fcb06-194">ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)</span><span class="sxs-lookup"><span data-stu-id="fcb06-194">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="fcb06-195">Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)</span><span class="sxs-lookup"><span data-stu-id="fcb06-195">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="fcb06-196">Ошибки: (ошибка и исключение).</span><span class="sxs-lookup"><span data-stu-id="fcb06-196">Errors: (Error and Exception).</span></span>

<span data-ttu-id="fcb06-197">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="fcb06-197">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fcb06-198">-PSHost</span><span class="sxs-lookup"><span data-stu-id="fcb06-198">-PSHost</span></span>

<span data-ttu-id="fcb06-199">Указывает, что командлет отправляет выходные данные трассировки на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcb06-199">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="fcb06-200">Данный параметр также определяет прослушиватель трассировки PSHost.</span><span class="sxs-lookup"><span data-stu-id="fcb06-200">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="fcb06-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fcb06-201">CommonParameters</span></span>

<span data-ttu-id="fcb06-202">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fcb06-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fcb06-203">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fcb06-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fcb06-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fcb06-204">INPUTS</span></span>

### <span data-ttu-id="fcb06-205">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="fcb06-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fcb06-206">Объекты, представляющие входные данные для выражения, можно передать в `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="fcb06-206">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="fcb06-207">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fcb06-207">OUTPUTS</span></span>

### <span data-ttu-id="fcb06-208">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="fcb06-208">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fcb06-209">Возвращает выходные данные трассировки в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-209">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="fcb06-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fcb06-210">NOTES</span></span>

- <span data-ttu-id="fcb06-211">Трассировка — это метод, применяемый разработчиками для отладки и изменения программы.</span><span class="sxs-lookup"><span data-stu-id="fcb06-211">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="fcb06-212">Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-212">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="fcb06-213">Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="fcb06-213">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="fcb06-214">Они позволяют отслеживать практически все аспекты функциональных возможностей оболочки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-214">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="fcb06-215">Чтобы найти компоненты PowerShell, для которых включена трассировка, введите `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="fcb06-215">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="fcb06-216">Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.</span><span class="sxs-lookup"><span data-stu-id="fcb06-216">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="fcb06-217">Чтобы выполнить трассировку компонента, указать определить его источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="fcb06-217">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="fcb06-218">Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.</span><span class="sxs-lookup"><span data-stu-id="fcb06-218">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="fcb06-219">Вы можете выбрать отправку данных трассировки в отладчик в пользовательском режиме или в режиме ядра, на узел или в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="fcb06-219">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="fcb06-220">Если используется набор параметров набора команд, PowerShell обрабатывает команду так же, как она будет обработана в конвейере.</span><span class="sxs-lookup"><span data-stu-id="fcb06-220">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="fcb06-221">Например, обнаружение команды не повторяется для каждого поступающего объект</span><span class="sxs-lookup"><span data-stu-id="fcb06-221">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="fcb06-222">**Имена,** **выражения** **, параметры и** **команды** не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="fcb06-222">The names of the **Name**, **Expression**, **Option**, and **Command** parameters are optional.</span></span> <span data-ttu-id="fcb06-223">Если имена параметров не заданы, то значения неименованных параметров должны отображаться в следующем порядке: **имя**, **выражение**, **параметр** или **имя**, **команда**, **параметр**.</span><span class="sxs-lookup"><span data-stu-id="fcb06-223">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name**, **Expression**, **Option** or **Name**, **Command**, **Option**.</span></span> <span data-ttu-id="fcb06-224">При указании имен параметры могут следовать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="fcb06-224">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="fcb06-225">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fcb06-225">RELATED LINKS</span></span>

[<span data-ttu-id="fcb06-226">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="fcb06-226">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="fcb06-227">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="fcb06-227">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="fcb06-228">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="fcb06-228">Set-TraceSource</span></span>](Set-TraceSource.md)

