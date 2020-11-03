---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: 9147be62c881e81a4ff1352a1b9fe7a34d2610cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228769"
---
# <span data-ttu-id="8e727-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="8e727-103">Trace-Command</span></span>

## <span data-ttu-id="8e727-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8e727-104">SYNOPSIS</span></span>
<span data-ttu-id="8e727-105">Настраивает и запускает трассировку указанного выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="8e727-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="8e727-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8e727-106">SYNTAX</span></span>

### <span data-ttu-id="8e727-107">"выражение" (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8e727-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="8e727-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="8e727-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="8e727-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8e727-109">DESCRIPTION</span></span>
<span data-ttu-id="8e727-110">`Trace-Command`Командлет настраивает и запускает трассировку указанного выражения или команды.</span><span class="sxs-lookup"><span data-stu-id="8e727-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="8e727-111">Он аналогичен командлету Set-TraceSource за тем исключением, что его действие распространяется только на указанную команду.</span><span class="sxs-lookup"><span data-stu-id="8e727-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="8e727-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="8e727-112">EXAMPLES</span></span>

### <span data-ttu-id="8e727-113">Пример 1. Обработка метаданных трассировки, привязка параметров и выражение</span><span class="sxs-lookup"><span data-stu-id="8e727-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="8e727-114">В этом примере запускается трассировка обработки метаданных, привязки параметров и создания и уничтожения `Get-Process Notepad` выражения.</span><span class="sxs-lookup"><span data-stu-id="8e727-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="8e727-115">Он использует параметр **Name** для указания источников трассировки, параметр **Expression** для указания команды и параметр **PSHost** для отправки выходных данных в консоль.</span><span class="sxs-lookup"><span data-stu-id="8e727-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="8e727-116">Поскольку параметры трассировки и параметры прослушивателя не указаны, команда использует значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="8e727-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="8e727-117">Все для параметров трассировки</span><span class="sxs-lookup"><span data-stu-id="8e727-117">All for the tracing options</span></span>
- <span data-ttu-id="8e727-118">Нет для параметров прослушивателя</span><span class="sxs-lookup"><span data-stu-id="8e727-118">None for the listener options</span></span>

### <span data-ttu-id="8e727-119">Пример 2. трассировка действий операций ParameterBinding оболочки</span><span class="sxs-lookup"><span data-stu-id="8e727-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="8e727-120">В этом примере отслеживаются действия **ParameterBinding оболочки** операций PowerShell во время обработки `Get-Alias` выражения, принимающего входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="8e727-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="8e727-121">В `Trace-Command` параметр **InputObject** передает объект в выражение, обрабатываемое во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="8e727-122">Первая команда сохраняет строку `i*` в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="8e727-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="8e727-123">Вторая команда использует `Trace-Command` командлет с источником трассировки ParameterBinding оболочки.</span><span class="sxs-lookup"><span data-stu-id="8e727-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="8e727-124">Параметр **PSHost** отправляет выходные данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="8e727-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="8e727-125">Обрабатываемое выражение имеет значение `Get-Alias $Input` , где `$Input` переменная связана с параметром **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="8e727-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="8e727-126">Параметр **InputObject** передает переменную в `$A` выражение.</span><span class="sxs-lookup"><span data-stu-id="8e727-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="8e727-127">По сути, команда, обрабатываемая во время трассировки, имеет значение `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="8e727-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="8e727-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8e727-128">PARAMETERS</span></span>

### <span data-ttu-id="8e727-129">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="8e727-129">-ArgumentList</span></span>

<span data-ttu-id="8e727-130">Указывает параметры и значения параметров для трассируемой команды.</span><span class="sxs-lookup"><span data-stu-id="8e727-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="8e727-131">Псевдоним для **ArgumentList** — **Args** .</span><span class="sxs-lookup"><span data-stu-id="8e727-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="8e727-132">Эта функция особенно полезна для отладки динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="8e727-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="8e727-133">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="8e727-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="8e727-134">-Command</span><span class="sxs-lookup"><span data-stu-id="8e727-134">-Command</span></span>

<span data-ttu-id="8e727-135">Указывает команду, обрабатываемую во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-135">Specifies a command that is being processed during the trace.</span></span>

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

### <span data-ttu-id="8e727-136">-Отладчик</span><span class="sxs-lookup"><span data-stu-id="8e727-136">-Debugger</span></span>

<span data-ttu-id="8e727-137">Указывает, что командлет отправляет выходные данные трассировки в отладчик.</span><span class="sxs-lookup"><span data-stu-id="8e727-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="8e727-138">Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e727-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="8e727-139">Данный параметр также определяет прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e727-139">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="8e727-140">-Expression</span><span class="sxs-lookup"><span data-stu-id="8e727-140">-Expression</span></span>

<span data-ttu-id="8e727-141">Указывает выражение, обрабатываемое во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="8e727-142">Заключите выражение в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="8e727-142">Enclose the expression in braces (`{}`).</span></span>

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

### <span data-ttu-id="8e727-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="8e727-143">-FilePath</span></span>

<span data-ttu-id="8e727-144">Указывает файл, в который командлет отправляет выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="8e727-145">Данный параметр также определяет прослушиватель трассировки файла.</span><span class="sxs-lookup"><span data-stu-id="8e727-145">This parameter also selects the file trace listener.</span></span>

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

### <span data-ttu-id="8e727-146">-Force</span><span class="sxs-lookup"><span data-stu-id="8e727-146">-Force</span></span>

<span data-ttu-id="8e727-147">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="8e727-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="8e727-148">Используется с параметром **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="8e727-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="8e727-149">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e727-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="8e727-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8e727-150">-InputObject</span></span>

<span data-ttu-id="8e727-151">Задает входные данные для выражения, обрабатываемого во время трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="8e727-152">Можно ввести переменную, которая представляет выходные данные, принимаемые этим выражением, или передать объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8e727-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="8e727-153">-Листенероптион</span><span class="sxs-lookup"><span data-stu-id="8e727-153">-ListenerOption</span></span>

<span data-ttu-id="8e727-154">Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8e727-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="8e727-155">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8e727-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8e727-156">Нет</span><span class="sxs-lookup"><span data-stu-id="8e727-156">None</span></span>
- <span data-ttu-id="8e727-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="8e727-157">LogicalOperationStack</span></span>
- <span data-ttu-id="8e727-158">Дата и время</span><span class="sxs-lookup"><span data-stu-id="8e727-158">DateTime</span></span>
- <span data-ttu-id="8e727-159">Отметка времени</span><span class="sxs-lookup"><span data-stu-id="8e727-159">Timestamp</span></span>
- <span data-ttu-id="8e727-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="8e727-160">ProcessId</span></span>
- <span data-ttu-id="8e727-161">Tидентификатор</span><span class="sxs-lookup"><span data-stu-id="8e727-161">ThreadId</span></span>
- <span data-ttu-id="8e727-162">Части</span><span class="sxs-lookup"><span data-stu-id="8e727-162">Callstack</span></span>

<span data-ttu-id="8e727-163">Значение по умолчанию — **None** .</span><span class="sxs-lookup"><span data-stu-id="8e727-163">**None** is the default.</span></span>

<span data-ttu-id="8e727-164">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="8e727-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="8e727-165">-Name</span><span class="sxs-lookup"><span data-stu-id="8e727-165">-Name</span></span>

<span data-ttu-id="8e727-166">Указывает массив отслеживаемых компонентов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e727-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="8e727-167">Введите имя источника трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="8e727-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="8e727-168">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8e727-168">Wildcards are permitted.</span></span> <span data-ttu-id="8e727-169">Чтобы найти источники трассировки на компьютере, введите `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="8e727-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

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

### <span data-ttu-id="8e727-170">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="8e727-170">-Option</span></span>

<span data-ttu-id="8e727-171">Определяет тип трассируемых событий.</span><span class="sxs-lookup"><span data-stu-id="8e727-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="8e727-172">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8e727-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8e727-173">Нет</span><span class="sxs-lookup"><span data-stu-id="8e727-173">None</span></span>
- <span data-ttu-id="8e727-174">Конструктор</span><span class="sxs-lookup"><span data-stu-id="8e727-174">Constructor</span></span>
- <span data-ttu-id="8e727-175">Dispose</span><span class="sxs-lookup"><span data-stu-id="8e727-175">Dispose</span></span>
- <span data-ttu-id="8e727-176">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="8e727-176">Finalizer</span></span>
- <span data-ttu-id="8e727-177">Метод</span><span class="sxs-lookup"><span data-stu-id="8e727-177">Method</span></span>
- <span data-ttu-id="8e727-178">Свойство</span><span class="sxs-lookup"><span data-stu-id="8e727-178">Property</span></span>
- <span data-ttu-id="8e727-179">Делегаты</span><span class="sxs-lookup"><span data-stu-id="8e727-179">Delegates</span></span>
- <span data-ttu-id="8e727-180">События</span><span class="sxs-lookup"><span data-stu-id="8e727-180">Events</span></span>
- <span data-ttu-id="8e727-181">Исключение</span><span class="sxs-lookup"><span data-stu-id="8e727-181">Exception</span></span>
- <span data-ttu-id="8e727-182">Блокировка</span><span class="sxs-lookup"><span data-stu-id="8e727-182">Lock</span></span>
- <span data-ttu-id="8e727-183">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8e727-183">Error</span></span>
- <span data-ttu-id="8e727-184">ошибки</span><span class="sxs-lookup"><span data-stu-id="8e727-184">Errors</span></span>
- <span data-ttu-id="8e727-185">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="8e727-185">Warning</span></span>
- <span data-ttu-id="8e727-186">Подробный</span><span class="sxs-lookup"><span data-stu-id="8e727-186">Verbose</span></span>
- <span data-ttu-id="8e727-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="8e727-187">WriteLine</span></span>
- <span data-ttu-id="8e727-188">Данные</span><span class="sxs-lookup"><span data-stu-id="8e727-188">Data</span></span>
- <span data-ttu-id="8e727-189">Область</span><span class="sxs-lookup"><span data-stu-id="8e727-189">Scope</span></span>
- <span data-ttu-id="8e727-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="8e727-190">ExecutionFlow</span></span>
- <span data-ttu-id="8e727-191">Assert</span><span class="sxs-lookup"><span data-stu-id="8e727-191">Assert</span></span>
- <span data-ttu-id="8e727-192">Все</span><span class="sxs-lookup"><span data-stu-id="8e727-192">All</span></span>

<span data-ttu-id="8e727-193">По умолчанию используется значение All.</span><span class="sxs-lookup"><span data-stu-id="8e727-193">All is the default.</span></span>

<span data-ttu-id="8e727-194">Следующие значения являются комбинацией других значений:</span><span class="sxs-lookup"><span data-stu-id="8e727-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="8e727-195">ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)</span><span class="sxs-lookup"><span data-stu-id="8e727-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="8e727-196">Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)</span><span class="sxs-lookup"><span data-stu-id="8e727-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="8e727-197">Ошибки: (ошибка и исключение).</span><span class="sxs-lookup"><span data-stu-id="8e727-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="8e727-198">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="8e727-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="8e727-199">-PSHost</span><span class="sxs-lookup"><span data-stu-id="8e727-199">-PSHost</span></span>

<span data-ttu-id="8e727-200">Указывает, что командлет отправляет выходные данные трассировки на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e727-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="8e727-201">Данный параметр также определяет прослушиватель трассировки PSHost.</span><span class="sxs-lookup"><span data-stu-id="8e727-201">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="8e727-202">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8e727-202">CommonParameters</span></span>

<span data-ttu-id="8e727-203">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8e727-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8e727-204">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8e727-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8e727-205">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8e727-205">INPUTS</span></span>

### <span data-ttu-id="8e727-206">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="8e727-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="8e727-207">Объекты, представляющие входные данные для выражения, можно передать в `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="8e727-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="8e727-208">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8e727-208">OUTPUTS</span></span>

### <span data-ttu-id="8e727-209">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="8e727-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="8e727-210">Возвращает выходные данные трассировки в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="8e727-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="8e727-211">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8e727-211">NOTES</span></span>

- <span data-ttu-id="8e727-212">Трассировка — это метод, применяемый разработчиками для отладки и изменения программы.</span><span class="sxs-lookup"><span data-stu-id="8e727-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="8e727-213">Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="8e727-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="8e727-214">Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="8e727-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="8e727-215">Они позволяют отслеживать практически все аспекты функциональных возможностей оболочки.</span><span class="sxs-lookup"><span data-stu-id="8e727-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="8e727-216">Чтобы найти компоненты PowerShell, для которых включена трассировка, введите `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="8e727-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="8e727-217">Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.</span><span class="sxs-lookup"><span data-stu-id="8e727-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="8e727-218">Чтобы выполнить трассировку компонента, указать определить его источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="8e727-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="8e727-219">Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.</span><span class="sxs-lookup"><span data-stu-id="8e727-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="8e727-220">Вы можете выбрать отправку данных трассировки в отладчик в пользовательском режиме или в режиме ядра, на узел или в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="8e727-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="8e727-221">Если используется набор параметров набора команд, PowerShell обрабатывает команду так же, как она будет обработана в конвейере.</span><span class="sxs-lookup"><span data-stu-id="8e727-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="8e727-222">Например, обнаружение команды не повторяется для каждого поступающего объект</span><span class="sxs-lookup"><span data-stu-id="8e727-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="8e727-223">**Имена,** **выражения** **, параметры и** **команды** не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="8e727-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="8e727-224">Если имена параметров не заданы, то значения неименованных параметров должны отображаться в следующем порядке: **имя** , **выражение** , **параметр** или **имя** , **команда** , **параметр** .</span><span class="sxs-lookup"><span data-stu-id="8e727-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="8e727-225">При указании имен параметры могут следовать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="8e727-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="8e727-226">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8e727-226">RELATED LINKS</span></span>

[<span data-ttu-id="8e727-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="8e727-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="8e727-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="8e727-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="8e727-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="8e727-229">Set-TraceSource</span></span>](Set-TraceSource.md)
