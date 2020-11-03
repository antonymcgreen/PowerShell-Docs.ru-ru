---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: f5f5b8c912664c96762890633297f6325968f3fa
ms.sourcegitcommit: 11abf355ac545531c2b04217a08ebe6be609c0bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "93230669"
---
# <span data-ttu-id="58908-103">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="58908-103">Stop-Process</span></span>

## <span data-ttu-id="58908-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="58908-104">SYNOPSIS</span></span>
<span data-ttu-id="58908-105">Останавливает один или несколько запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="58908-105">Stops one or more running processes.</span></span>

## <span data-ttu-id="58908-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="58908-106">SYNTAX</span></span>

### <span data-ttu-id="58908-107">Id (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="58908-107">Id (Default)</span></span>

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="58908-108">name</span><span class="sxs-lookup"><span data-stu-id="58908-108">Name</span></span>

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="58908-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="58908-109">InputObject</span></span>

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="58908-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="58908-110">DESCRIPTION</span></span>

<span data-ttu-id="58908-111">Командлет **Stop-Process** останавливает один или несколько запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="58908-111">The **Stop-Process** cmdlet stops one or more running processes.</span></span>
<span data-ttu-id="58908-112">Процесс можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID) или передать объект **процесса в Process** .</span><span class="sxs-lookup"><span data-stu-id="58908-112">You can specify a process by process name or process ID (PID), or pass a process object to **Stop-Process** .</span></span>
<span data-ttu-id="58908-113">Функция **останавливает-Process** работает только в процессах, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="58908-113">**Stop-Process** works only on processes running on the local computer.</span></span>

<span data-ttu-id="58908-114">В Windows Vista и более поздних версиях операционной системы Windows для завершения процесса, который не принадлежит текущему пользователю, необходимо запустить PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="58908-114">On Windows Vista and later versions of the Windows operating system, to stop a process that is not owned by the current user, you must start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="58908-115">Кроме того, запрос подтверждения не запрашивается, если не указан параметр *Confirm* .</span><span class="sxs-lookup"><span data-stu-id="58908-115">Also, you are not prompted for confirmation unless you specify the *Confirm* parameter.</span></span>

## <span data-ttu-id="58908-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="58908-116">EXAMPLES</span></span>

### <span data-ttu-id="58908-117">Пример 1. завершение всех экземпляров процесса</span><span class="sxs-lookup"><span data-stu-id="58908-117">Example 1: Stop all instances of a process</span></span>

```
PS C:\> Stop-Process -Name "notepad"
```

<span data-ttu-id="58908-118">Эта команда останавливает все экземпляры процесса Блокнота на компьютере.</span><span class="sxs-lookup"><span data-stu-id="58908-118">This command stops all instances of the Notepad process on the computer.</span></span>
<span data-ttu-id="58908-119">Каждый экземпляр блокнота выполняется в собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="58908-119">Each instance of Notepad runs in its own process.</span></span>
<span data-ttu-id="58908-120">В нем используется параметр *Name* для указания процессов, каждый из которых имеет одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="58908-120">It uses the *Name* parameter to specify the processes, all of which have the same name.</span></span>
<span data-ttu-id="58908-121">Если вы использовали параметр *ID* для завершения тех же процессов, необходимо перечислить идентификаторы каждого экземпляра блокнота.</span><span class="sxs-lookup"><span data-stu-id="58908-121">If you were to use the *Id* parameter to stop the same processes, you would have to list the process IDs of each instance of Notepad.</span></span>

### <span data-ttu-id="58908-122">Пример 2. останавливает конкретный экземпляр процесса</span><span class="sxs-lookup"><span data-stu-id="58908-122">Example 2: Stop a specific instance of a process</span></span>

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

<span data-ttu-id="58908-123">Эта команда останавливает определенный экземпляр процесса Блокнота.</span><span class="sxs-lookup"><span data-stu-id="58908-123">This command stops a particular instance of the Notepad process.</span></span>
<span data-ttu-id="58908-124">Для указания процесса в ней используется идентификатор процесса 3952.</span><span class="sxs-lookup"><span data-stu-id="58908-124">It uses the process ID, 3952, to identify the process.</span></span>
<span data-ttu-id="58908-125">Параметр *Confirm* направляет PowerShell запрос перед остановкой процесса.</span><span class="sxs-lookup"><span data-stu-id="58908-125">The *Confirm* parameter directs PowerShell to prompt you before it stops the process.</span></span>
<span data-ttu-id="58908-126">Так как запрос содержит имя процесса, дополненное к ИДЕНТИФИКАТОРу, рекомендуется использовать его.</span><span class="sxs-lookup"><span data-stu-id="58908-126">Because the prompt includes the process namein addition to its ID, this is best practice.</span></span>
<span data-ttu-id="58908-127">Параметр *PassThru* передает объект процесса модулю форматирования для вывода.</span><span class="sxs-lookup"><span data-stu-id="58908-127">The *PassThru* parameter passes the process object to the formatter for display.</span></span>
<span data-ttu-id="58908-128">Без этого параметра отображение после команды " **прерывать процесс** " будет отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="58908-128">Without this parameter, there would be no display after a **Stop-Process** command.</span></span>

### <span data-ttu-id="58908-129">Пример 3. остановка процесса и обнаружение его остановки</span><span class="sxs-lookup"><span data-stu-id="58908-129">Example 3: Stop a process and detect that it has stopped</span></span>

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

<span data-ttu-id="58908-130">Эта серия команд запускает и останавливает процесс Calc, а затем обнаруживает остановленные процессы.</span><span class="sxs-lookup"><span data-stu-id="58908-130">This series of commands starts and stops the Calc process, and then detects processes that have stopped.</span></span>

<span data-ttu-id="58908-131">Первая команда запускает экземпляр калькулятора.</span><span class="sxs-lookup"><span data-stu-id="58908-131">The first command starts an instance of the calculator.</span></span>

<span data-ttu-id="58908-132">Вторая команда использует **Get-Process для получения** объекта, представляющего процесс Calc, и сохраняет его в переменной $p.</span><span class="sxs-lookup"><span data-stu-id="58908-132">The second command uses **Get-Process** gets an object that represents the Calc process, and then stores it in the $p variable.</span></span>

<span data-ttu-id="58908-133">Третья команда останавливает процесс Calc.</span><span class="sxs-lookup"><span data-stu-id="58908-133">The third command stops the Calc process.</span></span>
<span data-ttu-id="58908-134">Он использует параметр *InputObject* для передачи объекта в командлет **Processing** .</span><span class="sxs-lookup"><span data-stu-id="58908-134">It uses the *InputObject* parameter to pass the object to **Stop-Process** .</span></span>

<span data-ttu-id="58908-135">Последняя команда возвращает все процессы на компьютере, которые были запущены, но теперь остановлены.</span><span class="sxs-lookup"><span data-stu-id="58908-135">The last command gets all of the processes on the computer that were running but that are now stopped.</span></span>
<span data-ttu-id="58908-136">Для получения всех процессов на компьютере используется **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="58908-136">It uses **Get-Process** to get all of the processes on the computer.</span></span>
<span data-ttu-id="58908-137">Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает, где значение свойства **хасекситед** равно $true.</span><span class="sxs-lookup"><span data-stu-id="58908-137">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the ones where the value of the **HasExited** property is $True.</span></span>
<span data-ttu-id="58908-138">**Хасекситед** — это только одно свойство объектов Process.</span><span class="sxs-lookup"><span data-stu-id="58908-138">**HasExited** is just one property of process objects.</span></span>
<span data-ttu-id="58908-139">Чтобы найти все свойства, введите `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="58908-139">To find all the properties, type `Get-Process | Get-Member`.</span></span>

### <span data-ttu-id="58908-140">Пример 4. завершение процесса, не принадлежащего текущему пользователю</span><span class="sxs-lookup"><span data-stu-id="58908-140">Example 4: Stop a process not owned by the current user</span></span>

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'`
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

<span data-ttu-id="58908-141">Эти команды показывают последствия использования *Force* для завершения процесса, который не принадлежит пользователю.</span><span class="sxs-lookup"><span data-stu-id="58908-141">These commands show the effect of using *Force* to stop a process that is not owned by the user.</span></span>

<span data-ttu-id="58908-142">Первая команда использует **Get-Process** для получения процесса Lsass.</span><span class="sxs-lookup"><span data-stu-id="58908-142">The first command uses **Get-Process** to get the Lsass process.</span></span>
<span data-ttu-id="58908-143">Оператор конвейера отправляет процесс для его отмены **процессом** .</span><span class="sxs-lookup"><span data-stu-id="58908-143">A pipeline operator sends the process to **Stop-Process** to stop it.</span></span>
<span data-ttu-id="58908-144">Как показано в примере выходных данных, первая команда завершается с сообщением об отказе в доступе, так как этот процесс может быть остановлен только членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="58908-144">As shown in the sample output, the first command fails with an Access denied message, because this process can be stopped only by a member of the Administrator group on the computer.</span></span>

<span data-ttu-id="58908-145">При открытии PowerShell с параметром Запуск от имени администратора и повторной команде PowerShell запрашивает подтверждение.</span><span class="sxs-lookup"><span data-stu-id="58908-145">When PowerShell is opened by using the Run as administrator option, and the command is repeated, PowerShell prompts you for confirmation.</span></span>

<span data-ttu-id="58908-146">Вторая команда указывает *Force* для подавления запроса.</span><span class="sxs-lookup"><span data-stu-id="58908-146">The second command specifies *Force* to suppress the prompt.</span></span>
<span data-ttu-id="58908-147">В результате процесс останавливается без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="58908-147">As a result, the process is stopped without confirmation.</span></span>

## <span data-ttu-id="58908-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="58908-148">PARAMETERS</span></span>

### <span data-ttu-id="58908-149">-Force</span><span class="sxs-lookup"><span data-stu-id="58908-149">-Force</span></span>

<span data-ttu-id="58908-150">Останавливает указанные параметры без запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="58908-150">Stops the specified processes without prompting for confirmation.</span></span>
<span data-ttu-id="58908-151">По умолчанию **остановить-Process** запрашивает подтверждение перед остановкой процесса, который не принадлежит текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="58908-151">By default, **Stop-Process** prompts for confirmation before stopping any process that is not owned by the current user.</span></span>

<span data-ttu-id="58908-152">Чтобы найти владельца процесса, используйте `Get-CimInstance` командлет для получения объекта **Win32_Process** , который представляет процесс, а затем используйте метод GetObject объекта. **GetOwner**</span><span class="sxs-lookup"><span data-stu-id="58908-152">To find the owner of a process, use the `Get-CimInstance` cmdlet to get a **Win32_Process** object that represents the process, and then use the **GetOwner** method of the object.</span></span>

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

### <span data-ttu-id="58908-153">-Id</span><span class="sxs-lookup"><span data-stu-id="58908-153">-Id</span></span>

<span data-ttu-id="58908-154">Указывает идентификаторы процессов для завершения.</span><span class="sxs-lookup"><span data-stu-id="58908-154">Specifies the process IDs of the processes to stop.</span></span>
<span data-ttu-id="58908-155">При указании нескольких идентификаторов разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="58908-155">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="58908-156">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="58908-156">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="58908-157">-InputObject</span><span class="sxs-lookup"><span data-stu-id="58908-157">-InputObject</span></span>

<span data-ttu-id="58908-158">Задает останавливаемые объекты процесса.</span><span class="sxs-lookup"><span data-stu-id="58908-158">Specifies the process objects to stop.</span></span>
<span data-ttu-id="58908-159">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="58908-159">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="58908-160">-Name</span><span class="sxs-lookup"><span data-stu-id="58908-160">-Name</span></span>

<span data-ttu-id="58908-161">Указывает имена процессов, которые нужно прерывать.</span><span class="sxs-lookup"><span data-stu-id="58908-161">Specifies the process names of the processes to stop.</span></span>
<span data-ttu-id="58908-162">Можно ввести несколько имен процессов, разделенных запятыми, или использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="58908-162">You can type multiple process names, separated by commas, or use wildcard characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="58908-163">-PassThru</span><span class="sxs-lookup"><span data-stu-id="58908-163">-PassThru</span></span>

<span data-ttu-id="58908-164">Возвращает объект, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="58908-164">Returns an object that represents the process.</span></span>
<span data-ttu-id="58908-165">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="58908-165">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="58908-166">-Confirm</span><span class="sxs-lookup"><span data-stu-id="58908-166">-Confirm</span></span>

<span data-ttu-id="58908-167">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="58908-167">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="58908-168">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="58908-168">-WhatIf</span></span>

<span data-ttu-id="58908-169">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="58908-169">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="58908-170">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="58908-170">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="58908-171">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="58908-171">CommonParameters</span></span>

<span data-ttu-id="58908-172">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="58908-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58908-173">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="58908-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58908-174">Входные данные</span><span class="sxs-lookup"><span data-stu-id="58908-174">INPUTS</span></span>

### <span data-ttu-id="58908-175">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="58908-175">System.Diagnostics.Process</span></span>

<span data-ttu-id="58908-176">Объект процесса можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="58908-176">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="58908-177">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="58908-177">OUTPUTS</span></span>

### <span data-ttu-id="58908-178">Нет, System. Диагностика. Process</span><span class="sxs-lookup"><span data-stu-id="58908-178">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="58908-179">Этот командлет возвращает объект **System. Diagnostics. Process** , представляющий остановленный процесс, если указан параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="58908-179">This cmdlet returns a **System.Diagnostics.Process** object that represents the stopped process, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="58908-180">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="58908-180">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="58908-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="58908-181">NOTES</span></span>

* <span data-ttu-id="58908-182">Можно также ссылаться на **остановить процесс** по его встроенным псевдонимам, **Kill** и **СППС** .</span><span class="sxs-lookup"><span data-stu-id="58908-182">You can also refer to **Stop-Process** by its built-in aliases, **kill** and **spps** .</span></span> <span data-ttu-id="58908-183">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="58908-183">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="58908-184">Также можно использовать свойства и методы **Win32_Process** объекта инструментарий управления Windows (WMI) (WMI) в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58908-184">You can also use the properties and methods of the Windows Management Instrumentation (WMI) **Win32_Process** object in Windows PowerShell.</span></span>
<span data-ttu-id="58908-185">Дополнительные сведения см `Get-CimInstance` . в разделе и пакете SDK для инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="58908-185">For more information, see `Get-CimInstance` and the WMI SDK.</span></span>

* <span data-ttu-id="58908-186">При остановке процессов следует понимать, что остановка процесса может остановить процесс и службы, зависящие от этого процесса.</span><span class="sxs-lookup"><span data-stu-id="58908-186">When stopping processes, realize that stopping a process can stop process and services that depend on the process.</span></span>
<span data-ttu-id="58908-187">В крайнем случае остановка процесса может привести к остановке Windows.</span><span class="sxs-lookup"><span data-stu-id="58908-187">In an extreme case, stopping a process can stop Windows.</span></span>

## <span data-ttu-id="58908-188">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="58908-188">RELATED LINKS</span></span>

[<span data-ttu-id="58908-189">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="58908-189">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="58908-190">Get-Process</span><span class="sxs-lookup"><span data-stu-id="58908-190">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="58908-191">Start-Process</span><span class="sxs-lookup"><span data-stu-id="58908-191">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="58908-192">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="58908-192">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="58908-193">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="58908-193">Wait-Process</span></span>](Wait-Process.md)
