---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 7a1f7e2879b0eeefe8771a5e5a8bf763e48ff106
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225613"
---
# <span data-ttu-id="c5ccf-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="c5ccf-103">Set-TraceSource</span></span>

## <span data-ttu-id="c5ccf-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c5ccf-104">SYNOPSIS</span></span>
<span data-ttu-id="c5ccf-105">Настраивает, запускает и останавливает трассировку компонентов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="c5ccf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5ccf-106">SYNTAX</span></span>

### <span data-ttu-id="c5ccf-107">заданный по умолчанию параметр</span><span class="sxs-lookup"><span data-stu-id="c5ccf-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="c5ccf-108">ремовеалллистенерссет</span><span class="sxs-lookup"><span data-stu-id="c5ccf-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="c5ccf-109">ремовефилелистенерссет</span><span class="sxs-lookup"><span data-stu-id="c5ccf-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="c5ccf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5ccf-110">DESCRIPTION</span></span>

<span data-ttu-id="c5ccf-111">Командлет **Set-TraceSource** настраивает, запускает и останавливает трассировку компонента PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="c5ccf-112">С его помощью можно указать, какие компоненты следует трассировать и куда нужно отправить результат трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="c5ccf-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c5ccf-113">EXAMPLES</span></span>

### <span data-ttu-id="c5ccf-114">Пример 1. Трассировка компонента ParameterBinding оболочки</span><span class="sxs-lookup"><span data-stu-id="c5ccf-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="c5ccf-115">Эта команда запускает трассировку для компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="c5ccf-116">Он использует параметр *Name* для указания источника трассировки, параметр *Option* для выбора событий трассировки ExecutionFlow, а параметр *PSHost* — для выбора прослушивателя узла PowerShell, который отправляет выходные данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="c5ccf-117">Параметр *листенероптион* добавляет значения ProcessID и timestamp к префиксу сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="c5ccf-118">Пример 2. Завершение трассировки</span><span class="sxs-lookup"><span data-stu-id="c5ccf-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="c5ccf-119">Эта команда останавливает трассировку компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="c5ccf-120">Он использует параметр *Name* для выявления отслеживаемого компонента и параметр *ремовелистенер* для обнаружения прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="c5ccf-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5ccf-121">PARAMETERS</span></span>

### <span data-ttu-id="c5ccf-122">-Отладчик</span><span class="sxs-lookup"><span data-stu-id="c5ccf-122">-Debugger</span></span>

<span data-ttu-id="c5ccf-123">Указывает, что командлет отправляет выходные данные трассировки в отладчик.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="c5ccf-124">Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="c5ccf-125">Данный параметр также определяет прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-125">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="c5ccf-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="c5ccf-126">-FilePath</span></span>

<span data-ttu-id="c5ccf-127">Указывает файл, в который этот командлет отправляет выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="c5ccf-128">Данный параметр также определяет прослушиватель трассировки файла.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="c5ccf-129">При использовании этого параметра для запуска трассировки используйте параметр *RemoveFileListener* , чтобы прерывать трассировку.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

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

### <span data-ttu-id="c5ccf-130">-Force</span><span class="sxs-lookup"><span data-stu-id="c5ccf-130">-Force</span></span>

<span data-ttu-id="c5ccf-131">Указывает, что командлет перезаписывает файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="c5ccf-132">Используйте с параметром *FilePath* .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-132">Use with the *FilePath* parameter.</span></span>

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

### <span data-ttu-id="c5ccf-133">-Листенероптион</span><span class="sxs-lookup"><span data-stu-id="c5ccf-133">-ListenerOption</span></span>

<span data-ttu-id="c5ccf-134">Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="c5ccf-135">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c5ccf-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c5ccf-136">Нет</span><span class="sxs-lookup"><span data-stu-id="c5ccf-136">None</span></span>
- <span data-ttu-id="c5ccf-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="c5ccf-137">LogicalOperationStack</span></span>
- <span data-ttu-id="c5ccf-138">Дата и время</span><span class="sxs-lookup"><span data-stu-id="c5ccf-138">DateTime</span></span>
- <span data-ttu-id="c5ccf-139">Отметка времени</span><span class="sxs-lookup"><span data-stu-id="c5ccf-139">Timestamp</span></span>
- <span data-ttu-id="c5ccf-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c5ccf-140">ProcessId</span></span>
- <span data-ttu-id="c5ccf-141">Tидентификатор</span><span class="sxs-lookup"><span data-stu-id="c5ccf-141">ThreadId</span></span>
- <span data-ttu-id="c5ccf-142">Части</span><span class="sxs-lookup"><span data-stu-id="c5ccf-142">Callstack</span></span>

<span data-ttu-id="c5ccf-143">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-143">None is the default.</span></span>

<span data-ttu-id="c5ccf-144">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="c5ccf-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="c5ccf-145">-Name</span><span class="sxs-lookup"><span data-stu-id="c5ccf-145">-Name</span></span>

<span data-ttu-id="c5ccf-146">Указывает, какие компоненты будут трассироваться.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-146">Specifies which components are traced.</span></span>
<span data-ttu-id="c5ccf-147">Введите имя источника трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="c5ccf-148">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-148">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c5ccf-149">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="c5ccf-149">-Option</span></span>

<span data-ttu-id="c5ccf-150">Указывает тип отслеживаемых событий.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="c5ccf-151">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c5ccf-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c5ccf-152">Нет</span><span class="sxs-lookup"><span data-stu-id="c5ccf-152">None</span></span>
- <span data-ttu-id="c5ccf-153">Конструктор</span><span class="sxs-lookup"><span data-stu-id="c5ccf-153">Constructor</span></span>
- <span data-ttu-id="c5ccf-154">Dispose</span><span class="sxs-lookup"><span data-stu-id="c5ccf-154">Dispose</span></span>
- <span data-ttu-id="c5ccf-155">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="c5ccf-155">Finalizer</span></span>
- <span data-ttu-id="c5ccf-156">Метод</span><span class="sxs-lookup"><span data-stu-id="c5ccf-156">Method</span></span>
- <span data-ttu-id="c5ccf-157">Свойство</span><span class="sxs-lookup"><span data-stu-id="c5ccf-157">Property</span></span>
- <span data-ttu-id="c5ccf-158">Делегаты</span><span class="sxs-lookup"><span data-stu-id="c5ccf-158">Delegates</span></span>
- <span data-ttu-id="c5ccf-159">События</span><span class="sxs-lookup"><span data-stu-id="c5ccf-159">Events</span></span>
- <span data-ttu-id="c5ccf-160">Исключение</span><span class="sxs-lookup"><span data-stu-id="c5ccf-160">Exception</span></span>
- <span data-ttu-id="c5ccf-161">Блокировка</span><span class="sxs-lookup"><span data-stu-id="c5ccf-161">Lock</span></span>
- <span data-ttu-id="c5ccf-162">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c5ccf-162">Error</span></span>
- <span data-ttu-id="c5ccf-163">ошибки</span><span class="sxs-lookup"><span data-stu-id="c5ccf-163">Errors</span></span>
- <span data-ttu-id="c5ccf-164">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="c5ccf-164">Warning</span></span>
- <span data-ttu-id="c5ccf-165">Подробный</span><span class="sxs-lookup"><span data-stu-id="c5ccf-165">Verbose</span></span>
- <span data-ttu-id="c5ccf-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="c5ccf-166">WriteLine</span></span>
- <span data-ttu-id="c5ccf-167">Данные</span><span class="sxs-lookup"><span data-stu-id="c5ccf-167">Data</span></span>
- <span data-ttu-id="c5ccf-168">Область</span><span class="sxs-lookup"><span data-stu-id="c5ccf-168">Scope</span></span>
- <span data-ttu-id="c5ccf-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="c5ccf-169">ExecutionFlow</span></span>
- <span data-ttu-id="c5ccf-170">Assert</span><span class="sxs-lookup"><span data-stu-id="c5ccf-170">Assert</span></span>
- <span data-ttu-id="c5ccf-171">Все</span><span class="sxs-lookup"><span data-stu-id="c5ccf-171">All</span></span>

<span data-ttu-id="c5ccf-172">По умолчанию используется значение All.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-172">All is the default.</span></span>

<span data-ttu-id="c5ccf-173">Следующие значения являются комбинацией других значений:</span><span class="sxs-lookup"><span data-stu-id="c5ccf-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="c5ccf-174">ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)</span><span class="sxs-lookup"><span data-stu-id="c5ccf-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="c5ccf-175">Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)</span><span class="sxs-lookup"><span data-stu-id="c5ccf-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="c5ccf-176">Ошибки: (ошибка и исключение).</span><span class="sxs-lookup"><span data-stu-id="c5ccf-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="c5ccf-177">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="c5ccf-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="c5ccf-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c5ccf-178">-PassThru</span></span>

<span data-ttu-id="c5ccf-179">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="c5ccf-180">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c5ccf-181">-PSHost</span><span class="sxs-lookup"><span data-stu-id="c5ccf-181">-PSHost</span></span>

<span data-ttu-id="c5ccf-182">ндикатес, что этот командлет отправляет выходные данные трассировки на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="c5ccf-183">Данный параметр также определяет прослушиватель трассировки PSHost.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-183">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="c5ccf-184">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="c5ccf-184">-RemoveFileListener</span></span>

<span data-ttu-id="c5ccf-185">Прекращает трассировку, удаляя прослушиватель трассировки, связанный с указанным файлом.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="c5ccf-186">Введите путь и имя выходного файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-186">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="c5ccf-187">-Ремовелистенер</span><span class="sxs-lookup"><span data-stu-id="c5ccf-187">-RemoveListener</span></span>

<span data-ttu-id="c5ccf-188">Прекращает трассировку, удаляя прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="c5ccf-189">Используйте следующие значения с *ремовелистенер* :</span><span class="sxs-lookup"><span data-stu-id="c5ccf-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="c5ccf-190">Чтобы удалить PSHost (Console), введите `Host` .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="c5ccf-191">Чтобы удалить отладчик, введите `Debug` .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="c5ccf-192">Чтобы удалить все прослушиватели трассировки, введите `*` .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="c5ccf-193">Чтобы удалить прослушиватель трассировки файлов, используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

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

### <span data-ttu-id="c5ccf-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c5ccf-194">CommonParameters</span></span>

<span data-ttu-id="c5ccf-195">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5ccf-196">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5ccf-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5ccf-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c5ccf-197">INPUTS</span></span>

### <span data-ttu-id="c5ccf-198">System.String</span><span class="sxs-lookup"><span data-stu-id="c5ccf-198">System.String</span></span>

<span data-ttu-id="c5ccf-199">Строку, содержащую имя, можно передать в командлет **Set-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-199">You can pipe a string that contains a name to **Set-TraceSource**.</span></span>

## <span data-ttu-id="c5ccf-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c5ccf-200">OUTPUTS</span></span>

### <span data-ttu-id="c5ccf-201">None или System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="c5ccf-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="c5ccf-202">При использовании параметра *PassThru* командлет **Set-TraceSource** создает объект **System. Management. Automation. пстрацесаурце** , представляющий сеанс трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="c5ccf-203">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c5ccf-204">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c5ccf-204">NOTES</span></span>

* <span data-ttu-id="c5ccf-205">Трассировка — это метод, применяемый разработчиками для отладки и изменения программы.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="c5ccf-206">Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="c5ccf-207">Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="c5ccf-208">Они позволяют отслеживать практически все аспекты функциональности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="c5ccf-209">Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="c5ccf-210">Чтобы выполнить трассировку компонента, указать определить его источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="c5ccf-211">Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="c5ccf-212">Вы можете выбрать отправку данных трассировки в отладчике пользовательского режима или в режиме ядра в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="c5ccf-213">Чтобы запустить трассировку, используйте параметр *Name* , чтобы указать источник трассировки, а также параметры *FilePath* , *Debugger* или *PSHost* , чтобы указать прослушиватель (назначение для выходных данных).</span><span class="sxs-lookup"><span data-stu-id="c5ccf-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="c5ccf-214">Используйте параметр *Options* , чтобы определить типы отслеживаемых событий и параметр *листенероптион* для настройки выходных данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="c5ccf-215">Чтобы изменить конфигурацию трассировки, введите команду **Set-TraceSource** , как при запуске трассировки.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="c5ccf-216">PowerShell распознает, что источник трассировки уже отслеживается.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="c5ccf-217">Она остановит трассировку, добавит новую конфигурацию и запустит или перезапустит трассировку.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="c5ccf-218">Чтобы отключить трассировку, используйте параметр *ремовелистенер* .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="c5ccf-219">Чтобы отключить трассировку, использующую прослушиватель файла (трассировка, запущенная с помощью параметра *FilePath* ), используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="c5ccf-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="c5ccf-220">При удалении прослушивателя трассировка останавливается.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="c5ccf-221">Чтобы определить, какие компоненты можно трассировать, используйте командлет Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="c5ccf-222">Источники трассировки для каждого модуля загружаются автоматически при использовании компонента и отображаются в выходных данных **Get-TraceSource**.</span><span class="sxs-lookup"><span data-stu-id="c5ccf-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource**.</span></span>

## <span data-ttu-id="c5ccf-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c5ccf-223">RELATED LINKS</span></span>

[<span data-ttu-id="c5ccf-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="c5ccf-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="c5ccf-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="c5ccf-225">Trace-Command</span></span>](Trace-Command.md)
