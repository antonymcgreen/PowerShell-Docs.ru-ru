---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: a79bcdaa60c420c4436276749c1b4d298158f8a6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343017"
---
# <span data-ttu-id="c14ba-103">Start-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-103">Start-Service</span></span>

## <span data-ttu-id="c14ba-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c14ba-104">SYNOPSIS</span></span>
<span data-ttu-id="c14ba-105">Запускает одну или несколько остановленных служб.</span><span class="sxs-lookup"><span data-stu-id="c14ba-105">Starts one or more stopped services.</span></span>

## <span data-ttu-id="c14ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c14ba-106">SYNTAX</span></span>

### <span data-ttu-id="c14ba-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c14ba-107">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c14ba-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c14ba-108">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c14ba-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c14ba-109">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c14ba-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c14ba-110">DESCRIPTION</span></span>

<span data-ttu-id="c14ba-111">`Start-Service`Командлет отправляет начальное сообщение в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="c14ba-111">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="c14ba-112">Если служба уже запущена, сообщение пропускается без ошибок.</span><span class="sxs-lookup"><span data-stu-id="c14ba-112">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="c14ba-113">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для предоставления объекта службы, представляющего службы, которые необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="c14ba-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="c14ba-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="c14ba-114">EXAMPLES</span></span>

### <span data-ttu-id="c14ba-115">Пример 1. Запуск службы с помощью ее имени</span><span class="sxs-lookup"><span data-stu-id="c14ba-115">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="c14ba-116">В этом примере запускается служба EventLog на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c14ba-116">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="c14ba-117">Параметр **Name** идентифицирует службу по ее имени службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-117">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="c14ba-118">Пример 2. Отображение сведений без запуска службы</span><span class="sxs-lookup"><span data-stu-id="c14ba-118">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="c14ba-119">В этом примере показано, что произойдет при запуске служб с отображаемым именем, которое содержит "Remote".</span><span class="sxs-lookup"><span data-stu-id="c14ba-119">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="c14ba-120">Параметр **DisplayName** определяет службы по отображаемому имени, а не по имени службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-120">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="c14ba-121">Параметр **WhatIf** приводит к тому, что командлет отображает, что произойдет при выполнении команды, но не вносит изменения.</span><span class="sxs-lookup"><span data-stu-id="c14ba-121">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="c14ba-122">Пример 3. Запуск службы и запись действия в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="c14ba-122">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="c14ba-123">В этом примере запускается служба инструментарий управления Windows (WMI) (WMI) на компьютере и добавляется запись действия в файл services.txt.</span><span class="sxs-lookup"><span data-stu-id="c14ba-123">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="c14ba-124">Сначала мы используем `Get-Service` , чтобы получить объект, который представляет службу WMI, и сохранить ее в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="c14ba-124">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="c14ba-125">Далее мы начнем службу.</span><span class="sxs-lookup"><span data-stu-id="c14ba-125">Next, we start the service.</span></span> <span data-ttu-id="c14ba-126">Без параметра **PassThru** `Start-Service` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c14ba-126">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="c14ba-127">Оператор конвейера (|) передает выходные данные объекта `Start-Service` в командлет, `Format-List` чтобы отформатировать объект как список его свойств.</span><span class="sxs-lookup"><span data-stu-id="c14ba-127">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="c14ba-128">Оператор добавления перенаправления ( \> \> ) перенаправляет выходные данные в файл services.txt.</span><span class="sxs-lookup"><span data-stu-id="c14ba-128">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="c14ba-129">Выходные данные добавляются в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="c14ba-129">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="c14ba-130">Пример 4. Запуск отключенной службы</span><span class="sxs-lookup"><span data-stu-id="c14ba-130">Example 4: Start a disabled service</span></span>

<span data-ttu-id="c14ba-131">В этом примере показано, как запустить службу при **отключенном** типе запуска службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-131">This example shows how to start a service when the start type of the service is **Disabled**.</span></span>

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

<span data-ttu-id="c14ba-132">При первой попытке запуска службы Telnet (tlntsvr) происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="c14ba-132">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="c14ba-133">`Get-CimInstance`Команда показывает, что свойство **StartMode** службы tlntsvr **отключено**.</span><span class="sxs-lookup"><span data-stu-id="c14ba-133">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled**.</span></span> <span data-ttu-id="c14ba-134">`Set-Service`Командлет изменяет тип запуска на **ручной**.</span><span class="sxs-lookup"><span data-stu-id="c14ba-134">The `Set-Service` cmdlet changes the start type to **Manual**.</span></span> <span data-ttu-id="c14ba-135">Теперь мы можем повторно отправить `Start-Service` команду.</span><span class="sxs-lookup"><span data-stu-id="c14ba-135">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="c14ba-136">В этот раз команда будет успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="c14ba-136">This time, the command succeeds.</span></span> <span data-ttu-id="c14ba-137">Чтобы убедиться, что команда выполнена, выполните команду `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="c14ba-137">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="c14ba-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c14ba-138">PARAMETERS</span></span>

### <span data-ttu-id="c14ba-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="c14ba-139">-DisplayName</span></span>

<span data-ttu-id="c14ba-140">Указывает отображаемые имена запускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="c14ba-140">Specifies the display names of the services to start.</span></span> <span data-ttu-id="c14ba-141">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c14ba-141">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c14ba-142">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c14ba-142">-Exclude</span></span>

<span data-ttu-id="c14ba-143">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="c14ba-143">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="c14ba-144">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="c14ba-144">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="c14ba-145">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="c14ba-145">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="c14ba-146">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c14ba-146">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c14ba-147">-Include</span><span class="sxs-lookup"><span data-stu-id="c14ba-147">-Include</span></span>

<span data-ttu-id="c14ba-148">Указывает службы, которые запускается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="c14ba-148">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="c14ba-149">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="c14ba-149">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="c14ba-150">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="c14ba-150">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="c14ba-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c14ba-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c14ba-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c14ba-152">-InputObject</span></span>

<span data-ttu-id="c14ba-153">Указывает объекты **ServiceController** , представляющие запускаемые службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-153">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="c14ba-154">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="c14ba-154">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c14ba-155">-Name</span><span class="sxs-lookup"><span data-stu-id="c14ba-155">-Name</span></span>

<span data-ttu-id="c14ba-156">Указывает имена службы запускаемой службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-156">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="c14ba-157">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c14ba-157">The parameter name is optional.</span></span> <span data-ttu-id="c14ba-158">Можно использовать **имя** или его псевдоним, **ServiceName** , или можно опустить имя параметра.</span><span class="sxs-lookup"><span data-stu-id="c14ba-158">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c14ba-159">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c14ba-159">-PassThru</span></span>

<span data-ttu-id="c14ba-160">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="c14ba-160">Returns an object that represents the service.</span></span> <span data-ttu-id="c14ba-161">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c14ba-161">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c14ba-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c14ba-162">-Confirm</span></span>

<span data-ttu-id="c14ba-163">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c14ba-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c14ba-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c14ba-164">-WhatIf</span></span>

<span data-ttu-id="c14ba-165">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c14ba-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c14ba-166">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c14ba-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c14ba-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c14ba-167">CommonParameters</span></span>

<span data-ttu-id="c14ba-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c14ba-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c14ba-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c14ba-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c14ba-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c14ba-170">INPUTS</span></span>

### <span data-ttu-id="c14ba-171">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="c14ba-171">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="c14ba-172">В этот командлет можно передать объекты, представляющие службы или строки, которые содержат имена служб.</span><span class="sxs-lookup"><span data-stu-id="c14ba-172">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="c14ba-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c14ba-173">OUTPUTS</span></span>

### <span data-ttu-id="c14ba-174">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c14ba-174">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="c14ba-175">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при указании **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="c14ba-175">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru**.</span></span> <span data-ttu-id="c14ba-176">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c14ba-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c14ba-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c14ba-177">NOTES</span></span>

<span data-ttu-id="c14ba-178">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="c14ba-178">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="c14ba-179">Также можно ссылаться `Start-Service` по встроенному псевдониму `sasv` .</span><span class="sxs-lookup"><span data-stu-id="c14ba-179">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="c14ba-180">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="c14ba-180">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="c14ba-181">`Start-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="c14ba-181">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="c14ba-182">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="c14ba-182">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="c14ba-183">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="c14ba-183">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="c14ba-184">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="c14ba-184">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
- <span data-ttu-id="c14ba-185">Можно запускать только службы с типом запуска вручную, автоматически или автоматически (отложенный запуск).</span><span class="sxs-lookup"><span data-stu-id="c14ba-185">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="c14ba-186">Нельзя запустить службы с отключенным типом запуска.</span><span class="sxs-lookup"><span data-stu-id="c14ba-186">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="c14ba-187">Если `Start-Service` команда завершается с сообщением `Cannot start service \<service-name\> on computer` , используйте `Get-CimInstance` для поиска типа запуска службы и при необходимости используйте `Set-Service` командлет, чтобы изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-187">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
- <span data-ttu-id="c14ba-188">Некоторые службы, такие как журналы и оповещения производительности (SysmonLog), останавливаются автоматически, если у них нет работы.</span><span class="sxs-lookup"><span data-stu-id="c14ba-188">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="c14ba-189">Когда служба PowerShell запускает службу, которая останавливается почти сразу же, она отображает следующее сообщение: `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="c14ba-189">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="c14ba-190">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c14ba-190">RELATED LINKS</span></span>

[<span data-ttu-id="c14ba-191">Get-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-191">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="c14ba-192">New-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-192">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="c14ba-193">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-193">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="c14ba-194">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-194">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="c14ba-195">Set-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-195">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="c14ba-196">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-196">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="c14ba-197">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-197">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="c14ba-198">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="c14ba-198">Remove-Service</span></span>](Remove-Service.md)
