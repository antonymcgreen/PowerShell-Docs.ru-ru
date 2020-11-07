---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: ed62e60e18594624c4c7aa940cc90bd09a1aa83c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345074"
---
# <span data-ttu-id="6ffa1-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-103">Stop-Service</span></span>

## <span data-ttu-id="6ffa1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6ffa1-104">SYNOPSIS</span></span>
<span data-ttu-id="6ffa1-105">Останавливает одну или несколько запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-105">Stops one or more running services.</span></span>

## <span data-ttu-id="6ffa1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ffa1-106">SYNTAX</span></span>

### <span data-ttu-id="6ffa1-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6ffa1-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6ffa1-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="6ffa1-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6ffa1-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6ffa1-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6ffa1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ffa1-110">DESCRIPTION</span></span>

<span data-ttu-id="6ffa1-111">`Stop-Service`Командлет отправляет сообщение об ошибке в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-111">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="6ffa1-112">Службы можно указать по их именам служб или отображаемым именам. также можно использовать параметр **InputObject** для передачи объекта службы, представляющего службу, которую необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="6ffa1-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="6ffa1-113">EXAMPLES</span></span>

### <span data-ttu-id="6ffa1-114">Пример 1. Завершение службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="6ffa1-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="6ffa1-115">Эта команда останавливает службы журналов производительности и оповещений (SysmonLog) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="6ffa1-116">Пример 2. Завершение службы с помощью отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="6ffa1-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="6ffa1-117">Эта команда останавливает службу Telnet на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-117">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="6ffa1-118">Команда использует `Get-Service` для получения объекта, представляющего службу Telnet.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-118">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="6ffa1-119">Оператор конвейера ( `|` ) передает объект в `Stop-Service` , который останавливает службу.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-119">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="6ffa1-120">Пример 3. Завершение службы, имеющей зависимые службы</span><span class="sxs-lookup"><span data-stu-id="6ffa1-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="6ffa1-121">В этом примере останавливается служба IISAdmin на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-121">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="6ffa1-122">Поскольку остановка этой службы также останавливает службы, зависящие от службы IISAdmin, лучше использовать `Stop-Service` команду со списком служб, зависящих от службы IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="6ffa1-123">Первая команда указывает службы, зависимые от IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-123">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="6ffa1-124">Он использует `Get-Service` для получения объекта, представляющего службу IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-124">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="6ffa1-125">Оператор конвейера ( `|` ) передает результат в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-125">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6ffa1-126">Команда использует параметр **Property** `Format-List` в для перечисления только свойств **Name** и **DependentServices** службы.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-126">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="6ffa1-127">Вторая команда останавливает службу IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-127">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="6ffa1-128">Параметр **Force** необходим для того, чтобы служба, имеющая зависимые службы, была остановлена.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-128">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="6ffa1-129">Команда использует параметр **Confirm** для запроса подтверждения от пользователя перед остановкой каждой службы.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-129">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="6ffa1-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ffa1-130">PARAMETERS</span></span>

### <span data-ttu-id="6ffa1-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="6ffa1-131">-DisplayName</span></span>

<span data-ttu-id="6ffa1-132">Указывает отображаемые имена останавливаемых служб.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="6ffa1-133">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="6ffa1-134">-Exclude</span><span class="sxs-lookup"><span data-stu-id="6ffa1-134">-Exclude</span></span>

<span data-ttu-id="6ffa1-135">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-135">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="6ffa1-136">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ffa1-136">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="6ffa1-137">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="6ffa1-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="6ffa1-138">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="6ffa1-139">-Force</span><span class="sxs-lookup"><span data-stu-id="6ffa1-139">-Force</span></span>

<span data-ttu-id="6ffa1-140">Заставляет командлет прекращать работу службы, даже если она зависит от служб.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="6ffa1-141">-Include</span><span class="sxs-lookup"><span data-stu-id="6ffa1-141">-Include</span></span>

<span data-ttu-id="6ffa1-142">Указывает службы, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-142">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="6ffa1-143">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ffa1-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="6ffa1-144">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="6ffa1-144">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="6ffa1-145">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="6ffa1-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6ffa1-146">-InputObject</span></span>

<span data-ttu-id="6ffa1-147">Указывает объекты **ServiceController** , представляющие останавливаемые службы.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-147">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="6ffa1-148">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="6ffa1-149">-Name</span><span class="sxs-lookup"><span data-stu-id="6ffa1-149">-Name</span></span>

<span data-ttu-id="6ffa1-150">Указывает имена служб для отмены.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-150">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="6ffa1-151">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6ffa1-152">-Неожидание</span><span class="sxs-lookup"><span data-stu-id="6ffa1-152">-NoWait</span></span>

<span data-ttu-id="6ffa1-153">Указывает, что этот командлет использует параметр No Wait.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="6ffa1-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6ffa1-154">-PassThru</span></span>

<span data-ttu-id="6ffa1-155">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-155">Returns an object that represents the service.</span></span> <span data-ttu-id="6ffa1-156">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="6ffa1-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6ffa1-157">-Confirm</span></span>

<span data-ttu-id="6ffa1-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6ffa1-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6ffa1-159">-WhatIf</span></span>

<span data-ttu-id="6ffa1-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6ffa1-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6ffa1-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6ffa1-162">CommonParameters</span></span>

<span data-ttu-id="6ffa1-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ffa1-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ffa1-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ffa1-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6ffa1-165">INPUTS</span></span>

### <span data-ttu-id="6ffa1-166">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="6ffa1-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="6ffa1-167">В этот командлет можно передать объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="6ffa1-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6ffa1-168">OUTPUTS</span></span>

### <span data-ttu-id="6ffa1-169">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="6ffa1-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="6ffa1-170">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при использовании параметра **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="6ffa1-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="6ffa1-171">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6ffa1-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6ffa1-172">NOTES</span></span>

<span data-ttu-id="6ffa1-173">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-173">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="6ffa1-174">Также можно ссылаться `Stop-Service` по встроенному псевдониму **СПСВ**.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-174">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="6ffa1-175">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="6ffa1-175">For more information, see about_Aliases.</span></span>

<span data-ttu-id="6ffa1-176">`Stop-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-176">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="6ffa1-177">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-177">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="6ffa1-178">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="6ffa1-178">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="6ffa1-179">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="6ffa1-179">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="6ffa1-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6ffa1-180">RELATED LINKS</span></span>

[<span data-ttu-id="6ffa1-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="6ffa1-182">New-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-182">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="6ffa1-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="6ffa1-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="6ffa1-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="6ffa1-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="6ffa1-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="6ffa1-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="6ffa1-188">Remove-Service</span></span>](Remove-Service.md)
