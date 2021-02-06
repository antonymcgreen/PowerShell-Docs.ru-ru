---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 6e7fd1c6eb3551906b4dd9d947b5e551cd05d30a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599408"
---
# <span data-ttu-id="80918-102">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="80918-102">Set-TraceSource</span></span>

## <span data-ttu-id="80918-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="80918-103">SYNOPSIS</span></span>
<span data-ttu-id="80918-104">Настраивает, запускает и останавливает трассировку компонентов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-104">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="80918-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80918-105">SYNTAX</span></span>

### <span data-ttu-id="80918-106">заданный по умолчанию параметр</span><span class="sxs-lookup"><span data-stu-id="80918-106">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="80918-107">ремовеалллистенерссет</span><span class="sxs-lookup"><span data-stu-id="80918-107">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="80918-108">ремовефилелистенерссет</span><span class="sxs-lookup"><span data-stu-id="80918-108">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="80918-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80918-109">DESCRIPTION</span></span>

<span data-ttu-id="80918-110">Командлет **Set-TraceSource** настраивает, запускает и останавливает трассировку компонента PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-110">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="80918-111">С его помощью можно указать, какие компоненты следует трассировать и куда нужно отправить результат трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-111">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="80918-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="80918-112">EXAMPLES</span></span>

### <span data-ttu-id="80918-113">Пример 1. Трассировка компонента ParameterBinding оболочки</span><span class="sxs-lookup"><span data-stu-id="80918-113">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="80918-114">Эта команда запускает трассировку для компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-114">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="80918-115">Он использует параметр *Name* для указания источника трассировки, параметр *Option* для выбора событий трассировки ExecutionFlow, а параметр *PSHost* — для выбора прослушивателя узла PowerShell, который отправляет выходные данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="80918-115">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="80918-116">Параметр *листенероптион* добавляет значения ProcessID и timestamp к префиксу сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-116">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="80918-117">Пример 2. Завершение трассировки</span><span class="sxs-lookup"><span data-stu-id="80918-117">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="80918-118">Эта команда останавливает трассировку компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-118">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="80918-119">Он использует параметр *Name* для выявления отслеживаемого компонента и параметр *ремовелистенер* для обнаружения прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-119">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="80918-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80918-120">PARAMETERS</span></span>

### <span data-ttu-id="80918-121">-Отладчик</span><span class="sxs-lookup"><span data-stu-id="80918-121">-Debugger</span></span>

<span data-ttu-id="80918-122">Указывает, что командлет отправляет выходные данные трассировки в отладчик.</span><span class="sxs-lookup"><span data-stu-id="80918-122">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="80918-123">Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80918-123">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="80918-124">Данный параметр также определяет прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="80918-124">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-125">-FilePath</span><span class="sxs-lookup"><span data-stu-id="80918-125">-FilePath</span></span>

<span data-ttu-id="80918-126">Указывает файл, в который этот командлет отправляет выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-126">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="80918-127">Данный параметр также определяет прослушиватель трассировки файла.</span><span class="sxs-lookup"><span data-stu-id="80918-127">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="80918-128">При использовании этого параметра для запуска трассировки используйте параметр *RemoveFileListener* , чтобы прерывать трассировку.</span><span class="sxs-lookup"><span data-stu-id="80918-128">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-129">-Force</span><span class="sxs-lookup"><span data-stu-id="80918-129">-Force</span></span>

<span data-ttu-id="80918-130">Указывает, что командлет перезаписывает файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="80918-130">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="80918-131">Используйте с параметром *FilePath* .</span><span class="sxs-lookup"><span data-stu-id="80918-131">Use with the *FilePath* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-132">-Листенероптион</span><span class="sxs-lookup"><span data-stu-id="80918-132">-ListenerOption</span></span>

<span data-ttu-id="80918-133">Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80918-133">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="80918-134">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="80918-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80918-135">None</span><span class="sxs-lookup"><span data-stu-id="80918-135">None</span></span>
- <span data-ttu-id="80918-136">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="80918-136">LogicalOperationStack</span></span>
- <span data-ttu-id="80918-137">Дата и время</span><span class="sxs-lookup"><span data-stu-id="80918-137">DateTime</span></span>
- <span data-ttu-id="80918-138">Отметка времени</span><span class="sxs-lookup"><span data-stu-id="80918-138">Timestamp</span></span>
- <span data-ttu-id="80918-139">ProcessId</span><span class="sxs-lookup"><span data-stu-id="80918-139">ProcessId</span></span>
- <span data-ttu-id="80918-140"> ThreadId</span><span class="sxs-lookup"><span data-stu-id="80918-140">ThreadId</span></span>
- <span data-ttu-id="80918-141">Части</span><span class="sxs-lookup"><span data-stu-id="80918-141">Callstack</span></span>

<span data-ttu-id="80918-142">По умолчанию используется значение Нет.</span><span class="sxs-lookup"><span data-stu-id="80918-142">None is the default.</span></span>

<span data-ttu-id="80918-143">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="80918-143">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-144">-Name</span><span class="sxs-lookup"><span data-stu-id="80918-144">-Name</span></span>

<span data-ttu-id="80918-145">Указывает, какие компоненты будут трассироваться.</span><span class="sxs-lookup"><span data-stu-id="80918-145">Specifies which components are traced.</span></span>
<span data-ttu-id="80918-146">Введите имя источника трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="80918-146">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="80918-147">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80918-147">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="80918-148">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="80918-148">-Option</span></span>

<span data-ttu-id="80918-149">Указывает тип отслеживаемых событий.</span><span class="sxs-lookup"><span data-stu-id="80918-149">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="80918-150">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="80918-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80918-151">None</span><span class="sxs-lookup"><span data-stu-id="80918-151">None</span></span>
- <span data-ttu-id="80918-152">Конструктор</span><span class="sxs-lookup"><span data-stu-id="80918-152">Constructor</span></span>
- <span data-ttu-id="80918-153">Dispose</span><span class="sxs-lookup"><span data-stu-id="80918-153">Dispose</span></span>
- <span data-ttu-id="80918-154">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="80918-154">Finalizer</span></span>
- <span data-ttu-id="80918-155">Метод</span><span class="sxs-lookup"><span data-stu-id="80918-155">Method</span></span>
- <span data-ttu-id="80918-156">Свойство</span><span class="sxs-lookup"><span data-stu-id="80918-156">Property</span></span>
- <span data-ttu-id="80918-157">Делегаты</span><span class="sxs-lookup"><span data-stu-id="80918-157">Delegates</span></span>
- <span data-ttu-id="80918-158">События</span><span class="sxs-lookup"><span data-stu-id="80918-158">Events</span></span>
- <span data-ttu-id="80918-159">Исключение</span><span class="sxs-lookup"><span data-stu-id="80918-159">Exception</span></span>
- <span data-ttu-id="80918-160">Блокировка</span><span class="sxs-lookup"><span data-stu-id="80918-160">Lock</span></span>
- <span data-ttu-id="80918-161">Ошибка</span><span class="sxs-lookup"><span data-stu-id="80918-161">Error</span></span>
- <span data-ttu-id="80918-162">Ошибки</span><span class="sxs-lookup"><span data-stu-id="80918-162">Errors</span></span>
- <span data-ttu-id="80918-163">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="80918-163">Warning</span></span>
- <span data-ttu-id="80918-164">Подробный</span><span class="sxs-lookup"><span data-stu-id="80918-164">Verbose</span></span>
- <span data-ttu-id="80918-165">WriteLine</span><span class="sxs-lookup"><span data-stu-id="80918-165">WriteLine</span></span>
- <span data-ttu-id="80918-166">Данные</span><span class="sxs-lookup"><span data-stu-id="80918-166">Data</span></span>
- <span data-ttu-id="80918-167">Область</span><span class="sxs-lookup"><span data-stu-id="80918-167">Scope</span></span>
- <span data-ttu-id="80918-168">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="80918-168">ExecutionFlow</span></span>
- <span data-ttu-id="80918-169">Assert</span><span class="sxs-lookup"><span data-stu-id="80918-169">Assert</span></span>
- <span data-ttu-id="80918-170">Все</span><span class="sxs-lookup"><span data-stu-id="80918-170">All</span></span>

<span data-ttu-id="80918-171">По умолчанию используется значение All.</span><span class="sxs-lookup"><span data-stu-id="80918-171">All is the default.</span></span>

<span data-ttu-id="80918-172">Следующие значения являются комбинацией других значений:</span><span class="sxs-lookup"><span data-stu-id="80918-172">The following values are combinations of other values:</span></span>

- <span data-ttu-id="80918-173">ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)</span><span class="sxs-lookup"><span data-stu-id="80918-173">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="80918-174">Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)</span><span class="sxs-lookup"><span data-stu-id="80918-174">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="80918-175">Ошибки: (ошибка и исключение).</span><span class="sxs-lookup"><span data-stu-id="80918-175">Errors: (Error and Exception).</span></span>

<span data-ttu-id="80918-176">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="80918-176">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="80918-177">-PassThru</span><span class="sxs-lookup"><span data-stu-id="80918-177">-PassThru</span></span>

<span data-ttu-id="80918-178">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="80918-178">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="80918-179">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="80918-179">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-180">-PSHost</span><span class="sxs-lookup"><span data-stu-id="80918-180">-PSHost</span></span>

<span data-ttu-id="80918-181">ндикатес, что этот командлет отправляет выходные данные трассировки на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-181">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="80918-182">Данный параметр также определяет прослушиватель трассировки PSHost.</span><span class="sxs-lookup"><span data-stu-id="80918-182">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-183">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="80918-183">-RemoveFileListener</span></span>

<span data-ttu-id="80918-184">Прекращает трассировку, удаляя прослушиватель трассировки, связанный с указанным файлом.</span><span class="sxs-lookup"><span data-stu-id="80918-184">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="80918-185">Введите путь и имя выходного файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-185">Enter the path and file name of the trace output file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-186">-Ремовелистенер</span><span class="sxs-lookup"><span data-stu-id="80918-186">-RemoveListener</span></span>

<span data-ttu-id="80918-187">Прекращает трассировку, удаляя прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-187">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="80918-188">Используйте следующие значения с *ремовелистенер*:</span><span class="sxs-lookup"><span data-stu-id="80918-188">Use the following values with *RemoveListener*:</span></span>

- <span data-ttu-id="80918-189">Чтобы удалить PSHost (Console), введите `Host` .</span><span class="sxs-lookup"><span data-stu-id="80918-189">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="80918-190">Чтобы удалить отладчик, введите `Debug` .</span><span class="sxs-lookup"><span data-stu-id="80918-190">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="80918-191">Чтобы удалить все прослушиватели трассировки, введите `*` .</span><span class="sxs-lookup"><span data-stu-id="80918-191">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="80918-192">Чтобы удалить прослушиватель трассировки файлов, используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="80918-192">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80918-193">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="80918-193">CommonParameters</span></span>

<span data-ttu-id="80918-194">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="80918-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80918-195">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="80918-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80918-196">Входные данные</span><span class="sxs-lookup"><span data-stu-id="80918-196">INPUTS</span></span>

### <span data-ttu-id="80918-197">System.String</span><span class="sxs-lookup"><span data-stu-id="80918-197">System.String</span></span>

<span data-ttu-id="80918-198">Строку, содержащую имя, можно передать в командлет **Set-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="80918-198">You can pipe a string that contains a name to **Set-TraceSource**.</span></span>

## <span data-ttu-id="80918-199">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="80918-199">OUTPUTS</span></span>

### <span data-ttu-id="80918-200">None или System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="80918-200">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="80918-201">При использовании параметра *PassThru* командлет **Set-TraceSource** создает объект **System. Management. Automation. пстрацесаурце** , представляющий сеанс трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-201">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="80918-202">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80918-202">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="80918-203">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="80918-203">NOTES</span></span>

* <span data-ttu-id="80918-204">Трассировка — это метод, применяемый разработчиками для отладки и изменения программы.</span><span class="sxs-lookup"><span data-stu-id="80918-204">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="80918-205">Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="80918-205">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="80918-206">Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="80918-206">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="80918-207">Они позволяют отслеживать практически все аспекты функциональности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80918-207">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="80918-208">Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.</span><span class="sxs-lookup"><span data-stu-id="80918-208">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="80918-209">Чтобы выполнить трассировку компонента, указать определить его источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-209">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="80918-210">Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.</span><span class="sxs-lookup"><span data-stu-id="80918-210">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="80918-211">Вы можете выбрать отправку данных трассировки в отладчике пользовательского режима или в режиме ядра в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="80918-211">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="80918-212">Чтобы запустить трассировку, используйте параметр *Name* , чтобы указать источник трассировки, а также параметры *FilePath*, *Debugger* или *PSHost* , чтобы указать прослушиватель (назначение для выходных данных).</span><span class="sxs-lookup"><span data-stu-id="80918-212">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath*, *Debugger*, or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="80918-213">Используйте параметр *Options* , чтобы определить типы отслеживаемых событий и параметр *листенероптион* для настройки выходных данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-213">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="80918-214">Чтобы изменить конфигурацию трассировки, введите команду **Set-TraceSource** , как при запуске трассировки.</span><span class="sxs-lookup"><span data-stu-id="80918-214">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="80918-215">PowerShell распознает, что источник трассировки уже отслеживается.</span><span class="sxs-lookup"><span data-stu-id="80918-215">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="80918-216">Она остановит трассировку, добавит новую конфигурацию и запустит или перезапустит трассировку.</span><span class="sxs-lookup"><span data-stu-id="80918-216">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="80918-217">Чтобы отключить трассировку, используйте параметр *ремовелистенер* .</span><span class="sxs-lookup"><span data-stu-id="80918-217">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="80918-218">Чтобы отключить трассировку, использующую прослушиватель файла (трассировка, запущенная с помощью параметра *FilePath* ), используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="80918-218">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="80918-219">При удалении прослушивателя трассировка останавливается.</span><span class="sxs-lookup"><span data-stu-id="80918-219">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="80918-220">Чтобы определить, какие компоненты можно трассировать, используйте командлет Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="80918-220">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="80918-221">Источники трассировки для каждого модуля загружаются автоматически при использовании компонента и отображаются в выходных данных **Get-TraceSource**.</span><span class="sxs-lookup"><span data-stu-id="80918-221">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource**.</span></span>

## <span data-ttu-id="80918-222">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="80918-222">RELATED LINKS</span></span>

[<span data-ttu-id="80918-223">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="80918-223">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="80918-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="80918-224">Trace-Command</span></span>](Trace-Command.md)

