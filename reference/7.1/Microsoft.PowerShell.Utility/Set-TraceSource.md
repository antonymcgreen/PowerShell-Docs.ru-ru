---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 00e9b3bc18d24fe252aee20eb77af0b5ad99468e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226566"
---
# <span data-ttu-id="95489-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="95489-103">Set-TraceSource</span></span>

## <span data-ttu-id="95489-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="95489-104">SYNOPSIS</span></span>
<span data-ttu-id="95489-105">Настраивает, запускает и останавливает трассировку компонентов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="95489-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95489-106">SYNTAX</span></span>

### <span data-ttu-id="95489-107">заданный по умолчанию параметр</span><span class="sxs-lookup"><span data-stu-id="95489-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="95489-108">ремовеалллистенерссет</span><span class="sxs-lookup"><span data-stu-id="95489-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="95489-109">ремовефилелистенерссет</span><span class="sxs-lookup"><span data-stu-id="95489-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="95489-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95489-110">DESCRIPTION</span></span>

<span data-ttu-id="95489-111">Командлет **Set-TraceSource** настраивает, запускает и останавливает трассировку компонента PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="95489-112">С его помощью можно указать, какие компоненты следует трассировать и куда нужно отправить результат трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="95489-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="95489-113">EXAMPLES</span></span>

### <span data-ttu-id="95489-114">Пример 1. Трассировка компонента ParameterBinding оболочки</span><span class="sxs-lookup"><span data-stu-id="95489-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="95489-115">Эта команда запускает трассировку для компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="95489-116">Он использует параметр *Name* для указания источника трассировки, параметр *Option* для выбора событий трассировки ExecutionFlow, а параметр *PSHost* — для выбора прослушивателя узла PowerShell, который отправляет выходные данные в консоль.</span><span class="sxs-lookup"><span data-stu-id="95489-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="95489-117">Параметр *листенероптион* добавляет значения ProcessID и timestamp к префиксу сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="95489-118">Пример 2. Завершение трассировки</span><span class="sxs-lookup"><span data-stu-id="95489-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="95489-119">Эта команда останавливает трассировку компонента ParameterBinding оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="95489-120">Он использует параметр *Name* для выявления отслеживаемого компонента и параметр *ремовелистенер* для обнаружения прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="95489-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95489-121">PARAMETERS</span></span>

### <span data-ttu-id="95489-122">-Отладчик</span><span class="sxs-lookup"><span data-stu-id="95489-122">-Debugger</span></span>

<span data-ttu-id="95489-123">Указывает, что командлет отправляет выходные данные трассировки в отладчик.</span><span class="sxs-lookup"><span data-stu-id="95489-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="95489-124">Выходные данные можно просмотреть в любом отладчике, работающем в пользовательском режиме или в режиме ядра, либо в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="95489-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="95489-125">Данный параметр также определяет прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95489-125">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="95489-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="95489-126">-FilePath</span></span>

<span data-ttu-id="95489-127">Указывает файл, в который этот командлет отправляет выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="95489-128">Данный параметр также определяет прослушиватель трассировки файла.</span><span class="sxs-lookup"><span data-stu-id="95489-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="95489-129">При использовании этого параметра для запуска трассировки используйте параметр *RemoveFileListener* , чтобы прерывать трассировку.</span><span class="sxs-lookup"><span data-stu-id="95489-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

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

### <span data-ttu-id="95489-130">-Force</span><span class="sxs-lookup"><span data-stu-id="95489-130">-Force</span></span>

<span data-ttu-id="95489-131">Указывает, что командлет перезаписывает файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="95489-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="95489-132">Используйте с параметром *FilePath* .</span><span class="sxs-lookup"><span data-stu-id="95489-132">Use with the *FilePath* parameter.</span></span>

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

### <span data-ttu-id="95489-133">-Листенероптион</span><span class="sxs-lookup"><span data-stu-id="95489-133">-ListenerOption</span></span>

<span data-ttu-id="95489-134">Указывает необязательные данные для префикса каждого сообщения трассировки в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="95489-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="95489-135">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="95489-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="95489-136">Нет</span><span class="sxs-lookup"><span data-stu-id="95489-136">None</span></span>
- <span data-ttu-id="95489-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="95489-137">LogicalOperationStack</span></span>
- <span data-ttu-id="95489-138">Дата и время</span><span class="sxs-lookup"><span data-stu-id="95489-138">DateTime</span></span>
- <span data-ttu-id="95489-139">Отметка времени</span><span class="sxs-lookup"><span data-stu-id="95489-139">Timestamp</span></span>
- <span data-ttu-id="95489-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="95489-140">ProcessId</span></span>
- <span data-ttu-id="95489-141">Tидентификатор</span><span class="sxs-lookup"><span data-stu-id="95489-141">ThreadId</span></span>
- <span data-ttu-id="95489-142">Части</span><span class="sxs-lookup"><span data-stu-id="95489-142">Callstack</span></span>

<span data-ttu-id="95489-143">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="95489-143">None is the default.</span></span>

<span data-ttu-id="95489-144">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="95489-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="95489-145">-Name</span><span class="sxs-lookup"><span data-stu-id="95489-145">-Name</span></span>

<span data-ttu-id="95489-146">Указывает, какие компоненты будут трассироваться.</span><span class="sxs-lookup"><span data-stu-id="95489-146">Specifies which components are traced.</span></span>
<span data-ttu-id="95489-147">Введите имя источника трассировки для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="95489-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="95489-148">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="95489-148">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="95489-149">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="95489-149">-Option</span></span>

<span data-ttu-id="95489-150">Указывает тип отслеживаемых событий.</span><span class="sxs-lookup"><span data-stu-id="95489-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="95489-151">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="95489-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="95489-152">Нет</span><span class="sxs-lookup"><span data-stu-id="95489-152">None</span></span>
- <span data-ttu-id="95489-153">Конструктор</span><span class="sxs-lookup"><span data-stu-id="95489-153">Constructor</span></span>
- <span data-ttu-id="95489-154">Dispose</span><span class="sxs-lookup"><span data-stu-id="95489-154">Dispose</span></span>
- <span data-ttu-id="95489-155">Метод завершения</span><span class="sxs-lookup"><span data-stu-id="95489-155">Finalizer</span></span>
- <span data-ttu-id="95489-156">Метод</span><span class="sxs-lookup"><span data-stu-id="95489-156">Method</span></span>
- <span data-ttu-id="95489-157">Свойство</span><span class="sxs-lookup"><span data-stu-id="95489-157">Property</span></span>
- <span data-ttu-id="95489-158">Делегаты</span><span class="sxs-lookup"><span data-stu-id="95489-158">Delegates</span></span>
- <span data-ttu-id="95489-159">События</span><span class="sxs-lookup"><span data-stu-id="95489-159">Events</span></span>
- <span data-ttu-id="95489-160">Исключение</span><span class="sxs-lookup"><span data-stu-id="95489-160">Exception</span></span>
- <span data-ttu-id="95489-161">Блокировка</span><span class="sxs-lookup"><span data-stu-id="95489-161">Lock</span></span>
- <span data-ttu-id="95489-162">Ошибка</span><span class="sxs-lookup"><span data-stu-id="95489-162">Error</span></span>
- <span data-ttu-id="95489-163">ошибки</span><span class="sxs-lookup"><span data-stu-id="95489-163">Errors</span></span>
- <span data-ttu-id="95489-164">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="95489-164">Warning</span></span>
- <span data-ttu-id="95489-165">Подробный</span><span class="sxs-lookup"><span data-stu-id="95489-165">Verbose</span></span>
- <span data-ttu-id="95489-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="95489-166">WriteLine</span></span>
- <span data-ttu-id="95489-167">Данные</span><span class="sxs-lookup"><span data-stu-id="95489-167">Data</span></span>
- <span data-ttu-id="95489-168">Область</span><span class="sxs-lookup"><span data-stu-id="95489-168">Scope</span></span>
- <span data-ttu-id="95489-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="95489-169">ExecutionFlow</span></span>
- <span data-ttu-id="95489-170">Assert</span><span class="sxs-lookup"><span data-stu-id="95489-170">Assert</span></span>
- <span data-ttu-id="95489-171">Все</span><span class="sxs-lookup"><span data-stu-id="95489-171">All</span></span>

<span data-ttu-id="95489-172">По умолчанию используется значение All.</span><span class="sxs-lookup"><span data-stu-id="95489-172">All is the default.</span></span>

<span data-ttu-id="95489-173">Следующие значения являются комбинацией других значений:</span><span class="sxs-lookup"><span data-stu-id="95489-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="95489-174">ExecutionFlow: (конструктор, Dispose, финализатор, метод, делегаты, события и область)</span><span class="sxs-lookup"><span data-stu-id="95489-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="95489-175">Данные: (конструктор, Dispose, метод завершения, свойство, Verbose и WriteLine)</span><span class="sxs-lookup"><span data-stu-id="95489-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="95489-176">Ошибки: (ошибка и исключение).</span><span class="sxs-lookup"><span data-stu-id="95489-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="95489-177">Чтобы указать несколько параметров, разделите их запятыми без пробелов и заключите в кавычки, например так: "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="95489-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="95489-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="95489-178">-PassThru</span></span>

<span data-ttu-id="95489-179">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="95489-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="95489-180">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="95489-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="95489-181">-PSHost</span><span class="sxs-lookup"><span data-stu-id="95489-181">-PSHost</span></span>

<span data-ttu-id="95489-182">ндикатес, что этот командлет отправляет выходные данные трассировки на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="95489-183">Данный параметр также определяет прослушиватель трассировки PSHost.</span><span class="sxs-lookup"><span data-stu-id="95489-183">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="95489-184">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="95489-184">-RemoveFileListener</span></span>

<span data-ttu-id="95489-185">Прекращает трассировку, удаляя прослушиватель трассировки, связанный с указанным файлом.</span><span class="sxs-lookup"><span data-stu-id="95489-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="95489-186">Введите путь и имя выходного файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-186">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="95489-187">-Ремовелистенер</span><span class="sxs-lookup"><span data-stu-id="95489-187">-RemoveListener</span></span>

<span data-ttu-id="95489-188">Прекращает трассировку, удаляя прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="95489-189">Используйте следующие значения с *ремовелистенер* :</span><span class="sxs-lookup"><span data-stu-id="95489-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="95489-190">Чтобы удалить PSHost (Console), введите `Host` .</span><span class="sxs-lookup"><span data-stu-id="95489-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="95489-191">Чтобы удалить отладчик, введите `Debug` .</span><span class="sxs-lookup"><span data-stu-id="95489-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="95489-192">Чтобы удалить все прослушиватели трассировки, введите `*` .</span><span class="sxs-lookup"><span data-stu-id="95489-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="95489-193">Чтобы удалить прослушиватель трассировки файлов, используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="95489-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

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

### <span data-ttu-id="95489-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="95489-194">CommonParameters</span></span>

<span data-ttu-id="95489-195">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95489-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95489-196">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="95489-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95489-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="95489-197">INPUTS</span></span>

### <span data-ttu-id="95489-198">System.String</span><span class="sxs-lookup"><span data-stu-id="95489-198">System.String</span></span>

<span data-ttu-id="95489-199">Строку, содержащую имя, можно передать в командлет **Set-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="95489-199">You can pipe a string that contains a name to **Set-TraceSource**.</span></span>

## <span data-ttu-id="95489-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="95489-200">OUTPUTS</span></span>

### <span data-ttu-id="95489-201">None или System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="95489-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="95489-202">При использовании параметра *PassThru* командлет **Set-TraceSource** создает объект **System. Management. Automation. пстрацесаурце** , представляющий сеанс трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="95489-203">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="95489-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="95489-204">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="95489-204">NOTES</span></span>

* <span data-ttu-id="95489-205">Трассировка — это метод, применяемый разработчиками для отладки и изменения программы.</span><span class="sxs-lookup"><span data-stu-id="95489-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="95489-206">Во время трассировки программа создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="95489-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="95489-207">Командлеты трассировки PowerShell предназначены для разработчиков с помощью PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="95489-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="95489-208">Они позволяют отслеживать практически все аспекты функциональности PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95489-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="95489-209">Источник трассировки является частью каждого компонента PowerShell, который управляет трассировкой и создает сообщения трассировки для компонента.</span><span class="sxs-lookup"><span data-stu-id="95489-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="95489-210">Чтобы выполнить трассировку компонента, указать определить его источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="95489-211">Прослушиватель трассировки получает выходные данные трассировки и отображает ее пользователю.</span><span class="sxs-lookup"><span data-stu-id="95489-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="95489-212">Вы можете выбрать отправку данных трассировки в отладчике пользовательского режима или в режиме ядра в консоль, в файл или в пользовательский прослушиватель, производный от класса **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="95489-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="95489-213">Чтобы запустить трассировку, используйте параметр *Name* , чтобы указать источник трассировки, а также параметры *FilePath* , *Debugger* или *PSHost* , чтобы указать прослушиватель (назначение для выходных данных).</span><span class="sxs-lookup"><span data-stu-id="95489-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="95489-214">Используйте параметр *Options* , чтобы определить типы отслеживаемых событий и параметр *листенероптион* для настройки выходных данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="95489-215">Чтобы изменить конфигурацию трассировки, введите команду **Set-TraceSource** , как при запуске трассировки.</span><span class="sxs-lookup"><span data-stu-id="95489-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="95489-216">PowerShell распознает, что источник трассировки уже отслеживается.</span><span class="sxs-lookup"><span data-stu-id="95489-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="95489-217">Она остановит трассировку, добавит новую конфигурацию и запустит или перезапустит трассировку.</span><span class="sxs-lookup"><span data-stu-id="95489-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="95489-218">Чтобы отключить трассировку, используйте параметр *ремовелистенер* .</span><span class="sxs-lookup"><span data-stu-id="95489-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="95489-219">Чтобы отключить трассировку, использующую прослушиватель файла (трассировка, запущенная с помощью параметра *FilePath* ), используйте параметр *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="95489-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="95489-220">При удалении прослушивателя трассировка останавливается.</span><span class="sxs-lookup"><span data-stu-id="95489-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="95489-221">Чтобы определить, какие компоненты можно трассировать, используйте командлет Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="95489-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="95489-222">Источники трассировки для каждого модуля загружаются автоматически при использовании компонента и отображаются в выходных данных **Get-TraceSource**.</span><span class="sxs-lookup"><span data-stu-id="95489-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource**.</span></span>

## <span data-ttu-id="95489-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="95489-223">RELATED LINKS</span></span>

[<span data-ttu-id="95489-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="95489-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="95489-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="95489-225">Trace-Command</span></span>](Trace-Command.md)
