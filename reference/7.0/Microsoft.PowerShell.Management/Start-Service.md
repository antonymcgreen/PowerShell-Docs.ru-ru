---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: d5a7588022331aac6315b1e37159bdbd6994b64a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225962"
---
# <span data-ttu-id="ed11e-103">Start-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-103">Start-Service</span></span>

## <span data-ttu-id="ed11e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ed11e-104">SYNOPSIS</span></span>
<span data-ttu-id="ed11e-105">Запускает одну или несколько остановленных служб.</span><span class="sxs-lookup"><span data-stu-id="ed11e-105">Starts one or more stopped services.</span></span>

## <span data-ttu-id="ed11e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed11e-106">SYNTAX</span></span>

### <span data-ttu-id="ed11e-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ed11e-107">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed11e-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="ed11e-108">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="ed11e-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed11e-109">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed11e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed11e-110">DESCRIPTION</span></span>

<span data-ttu-id="ed11e-111">`Start-Service`Командлет отправляет начальное сообщение в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="ed11e-111">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="ed11e-112">Если служба уже запущена, сообщение пропускается без ошибок.</span><span class="sxs-lookup"><span data-stu-id="ed11e-112">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="ed11e-113">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для предоставления объекта службы, представляющего службы, которые необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="ed11e-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="ed11e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="ed11e-114">EXAMPLES</span></span>

### <span data-ttu-id="ed11e-115">Пример 1. Запуск службы с помощью ее имени</span><span class="sxs-lookup"><span data-stu-id="ed11e-115">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="ed11e-116">В этом примере запускается служба EventLog на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed11e-116">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="ed11e-117">Параметр **Name** идентифицирует службу по ее имени службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-117">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="ed11e-118">Пример 2. Отображение сведений без запуска службы</span><span class="sxs-lookup"><span data-stu-id="ed11e-118">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="ed11e-119">В этом примере показано, что произойдет при запуске служб с отображаемым именем, которое содержит "Remote".</span><span class="sxs-lookup"><span data-stu-id="ed11e-119">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="ed11e-120">Параметр **DisplayName** определяет службы по отображаемому имени, а не по имени службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-120">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="ed11e-121">Параметр **WhatIf** приводит к тому, что командлет отображает, что произойдет при выполнении команды, но не вносит изменения.</span><span class="sxs-lookup"><span data-stu-id="ed11e-121">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="ed11e-122">Пример 3. Запуск службы и запись действия в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="ed11e-122">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="ed11e-123">В этом примере запускается служба инструментарий управления Windows (WMI) (WMI) на компьютере и добавляется запись действия в файл services.txt.</span><span class="sxs-lookup"><span data-stu-id="ed11e-123">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="ed11e-124">Сначала мы используем `Get-Service` , чтобы получить объект, который представляет службу WMI, и сохранить ее в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="ed11e-124">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="ed11e-125">Далее мы начнем службу.</span><span class="sxs-lookup"><span data-stu-id="ed11e-125">Next, we start the service.</span></span> <span data-ttu-id="ed11e-126">Без параметра **PassThru** `Start-Service` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ed11e-126">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="ed11e-127">Оператор конвейера (|) передает выходные данные объекта `Start-Service` в командлет, `Format-List` чтобы отформатировать объект как список его свойств.</span><span class="sxs-lookup"><span data-stu-id="ed11e-127">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="ed11e-128">Оператор добавления перенаправления ( \> \> ) перенаправляет выходные данные в файл services.txt.</span><span class="sxs-lookup"><span data-stu-id="ed11e-128">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="ed11e-129">Выходные данные добавляются в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="ed11e-129">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="ed11e-130">Пример 4. Запуск отключенной службы</span><span class="sxs-lookup"><span data-stu-id="ed11e-130">Example 4: Start a disabled service</span></span>

<span data-ttu-id="ed11e-131">В этом примере показано, как запустить службу при **отключенном** типе запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-131">This example shows how to start a service when the start type of the service is **Disabled**.</span></span>

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

<span data-ttu-id="ed11e-132">При первой попытке запуска службы Telnet (tlntsvr) происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="ed11e-132">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="ed11e-133">`Get-CimInstance`Команда показывает, что свойство **StartMode** службы tlntsvr **отключено**.</span><span class="sxs-lookup"><span data-stu-id="ed11e-133">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled**.</span></span> <span data-ttu-id="ed11e-134">`Set-Service`Командлет изменяет тип запуска на **ручной**.</span><span class="sxs-lookup"><span data-stu-id="ed11e-134">The `Set-Service` cmdlet changes the start type to **Manual**.</span></span> <span data-ttu-id="ed11e-135">Теперь мы можем повторно отправить `Start-Service` команду.</span><span class="sxs-lookup"><span data-stu-id="ed11e-135">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="ed11e-136">В этот раз команда будет успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="ed11e-136">This time, the command succeeds.</span></span> <span data-ttu-id="ed11e-137">Чтобы убедиться, что команда выполнена, выполните команду `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="ed11e-137">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="ed11e-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed11e-138">PARAMETERS</span></span>

### <span data-ttu-id="ed11e-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed11e-139">-DisplayName</span></span>

<span data-ttu-id="ed11e-140">Указывает отображаемые имена запускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="ed11e-140">Specifies the display names of the services to start.</span></span> <span data-ttu-id="ed11e-141">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ed11e-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed11e-142">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ed11e-142">-Exclude</span></span>

<span data-ttu-id="ed11e-143">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ed11e-143">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="ed11e-144">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="ed11e-144">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ed11e-145">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="ed11e-145">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="ed11e-146">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ed11e-146">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed11e-147">-Include</span><span class="sxs-lookup"><span data-stu-id="ed11e-147">-Include</span></span>

<span data-ttu-id="ed11e-148">Указывает службы, которые запускается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="ed11e-148">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="ed11e-149">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="ed11e-149">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ed11e-150">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="ed11e-150">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="ed11e-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ed11e-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed11e-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ed11e-152">-InputObject</span></span>

<span data-ttu-id="ed11e-153">Указывает объекты **ServiceController** , представляющие запускаемые службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-153">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="ed11e-154">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="ed11e-154">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="ed11e-155">-Name</span><span class="sxs-lookup"><span data-stu-id="ed11e-155">-Name</span></span>

<span data-ttu-id="ed11e-156">Указывает имена службы запускаемой службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-156">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="ed11e-157">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ed11e-157">The parameter name is optional.</span></span> <span data-ttu-id="ed11e-158">Можно использовать **имя** или его псевдоним, **ServiceName** , или можно опустить имя параметра.</span><span class="sxs-lookup"><span data-stu-id="ed11e-158">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="ed11e-159">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ed11e-159">-PassThru</span></span>

<span data-ttu-id="ed11e-160">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="ed11e-160">Returns an object that represents the service.</span></span> <span data-ttu-id="ed11e-161">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="ed11e-161">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ed11e-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed11e-162">-Confirm</span></span>

<span data-ttu-id="ed11e-163">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ed11e-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed11e-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed11e-164">-WhatIf</span></span>

<span data-ttu-id="ed11e-165">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ed11e-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ed11e-166">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ed11e-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed11e-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ed11e-167">CommonParameters</span></span>

<span data-ttu-id="ed11e-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed11e-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed11e-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed11e-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed11e-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ed11e-170">INPUTS</span></span>

### <span data-ttu-id="ed11e-171">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="ed11e-171">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="ed11e-172">В этот командлет можно передать объекты, представляющие службы или строки, которые содержат имена служб.</span><span class="sxs-lookup"><span data-stu-id="ed11e-172">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="ed11e-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ed11e-173">OUTPUTS</span></span>

### <span data-ttu-id="ed11e-174">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="ed11e-174">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="ed11e-175">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при указании **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="ed11e-175">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru**.</span></span> <span data-ttu-id="ed11e-176">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ed11e-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ed11e-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ed11e-177">NOTES</span></span>

* <span data-ttu-id="ed11e-178">Также можно ссылаться `Start-Service` по встроенному псевдониму `sasv` .</span><span class="sxs-lookup"><span data-stu-id="ed11e-178">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="ed11e-179">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="ed11e-179">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
* <span data-ttu-id="ed11e-180">`Start-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="ed11e-180">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="ed11e-181">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="ed11e-181">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="ed11e-182">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="ed11e-182">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="ed11e-183">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="ed11e-183">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
* <span data-ttu-id="ed11e-184">Можно запускать только службы с типом запуска вручную, автоматически или автоматически (отложенный запуск).</span><span class="sxs-lookup"><span data-stu-id="ed11e-184">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="ed11e-185">Нельзя запустить службы с отключенным типом запуска.</span><span class="sxs-lookup"><span data-stu-id="ed11e-185">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="ed11e-186">Если `Start-Service` команда завершается с сообщением `Cannot start service \<service-name\> on computer` , используйте `Get-CimInstance` для поиска типа запуска службы и при необходимости используйте `Set-Service` командлет, чтобы изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-186">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
* <span data-ttu-id="ed11e-187">Некоторые службы, такие как журналы и оповещения производительности (SysmonLog), останавливаются автоматически, если у них нет работы.</span><span class="sxs-lookup"><span data-stu-id="ed11e-187">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="ed11e-188">Когда служба PowerShell запускает службу, которая останавливается почти сразу же, она отображает следующее сообщение: `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="ed11e-188">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="ed11e-189">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ed11e-189">RELATED LINKS</span></span>

[<span data-ttu-id="ed11e-190">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-190">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="ed11e-191">New-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-191">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="ed11e-192">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-192">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="ed11e-193">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-193">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="ed11e-194">Set-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-194">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="ed11e-195">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-195">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="ed11e-196">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-196">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="ed11e-197">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="ed11e-197">Remove-Service</span></span>](Remove-Service.md)
