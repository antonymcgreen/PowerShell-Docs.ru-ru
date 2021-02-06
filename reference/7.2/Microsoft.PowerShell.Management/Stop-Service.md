---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 0216c7fae722121ead1c8e9ba122fbc3f1713725
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604425"
---
# <span data-ttu-id="0321d-102">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-102">Stop-Service</span></span>

## <span data-ttu-id="0321d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0321d-103">SYNOPSIS</span></span>
<span data-ttu-id="0321d-104">Останавливает одну или несколько запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="0321d-104">Stops one or more running services.</span></span>

## <span data-ttu-id="0321d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0321d-105">SYNTAX</span></span>

### <span data-ttu-id="0321d-106">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0321d-106">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0321d-107">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="0321d-107">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0321d-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0321d-108">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0321d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0321d-109">DESCRIPTION</span></span>

<span data-ttu-id="0321d-110">`Stop-Service`Командлет отправляет сообщение об ошибке в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="0321d-110">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="0321d-111">Службы можно указать по их именам служб или отображаемым именам. также можно использовать параметр **InputObject** для передачи объекта службы, представляющего службу, которую необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="0321d-111">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="0321d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="0321d-112">EXAMPLES</span></span>

### <span data-ttu-id="0321d-113">Пример 1. Завершение службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="0321d-113">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="0321d-114">Эта команда останавливает службы журналов производительности и оповещений (SysmonLog) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0321d-114">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="0321d-115">Пример 2. Завершение службы с помощью отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="0321d-115">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="0321d-116">Эта команда останавливает службу Telnet на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0321d-116">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="0321d-117">Команда использует `Get-Service` для получения объекта, представляющего службу Telnet.</span><span class="sxs-lookup"><span data-stu-id="0321d-117">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="0321d-118">Оператор конвейера ( `|` ) передает объект в `Stop-Service` , который останавливает службу.</span><span class="sxs-lookup"><span data-stu-id="0321d-118">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="0321d-119">Пример 3. Завершение службы, имеющей зависимые службы</span><span class="sxs-lookup"><span data-stu-id="0321d-119">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="0321d-120">В этом примере останавливается служба IISAdmin на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0321d-120">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="0321d-121">Поскольку остановка этой службы также останавливает службы, зависящие от службы IISAdmin, лучше использовать `Stop-Service` команду со списком служб, зависящих от службы IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="0321d-121">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="0321d-122">Первая команда указывает службы, зависимые от IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="0321d-122">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="0321d-123">Он использует `Get-Service` для получения объекта, представляющего службу IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="0321d-123">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="0321d-124">Оператор конвейера ( `|` ) передает результат в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="0321d-124">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="0321d-125">Команда использует параметр **Property** `Format-List` в для перечисления только свойств **Name** и **DependentServices** службы.</span><span class="sxs-lookup"><span data-stu-id="0321d-125">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="0321d-126">Вторая команда останавливает службу IISAdmin.</span><span class="sxs-lookup"><span data-stu-id="0321d-126">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="0321d-127">Параметр **Force** необходим для того, чтобы служба, имеющая зависимые службы, была остановлена.</span><span class="sxs-lookup"><span data-stu-id="0321d-127">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="0321d-128">Команда использует параметр **Confirm** для запроса подтверждения от пользователя перед остановкой каждой службы.</span><span class="sxs-lookup"><span data-stu-id="0321d-128">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="0321d-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0321d-129">PARAMETERS</span></span>

### <span data-ttu-id="0321d-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="0321d-130">-DisplayName</span></span>

<span data-ttu-id="0321d-131">Указывает отображаемые имена останавливаемых служб.</span><span class="sxs-lookup"><span data-stu-id="0321d-131">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="0321d-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0321d-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0321d-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="0321d-133">-Exclude</span></span>

<span data-ttu-id="0321d-134">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="0321d-134">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="0321d-135">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="0321d-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="0321d-136">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="0321d-136">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="0321d-137">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0321d-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0321d-138">-Force</span><span class="sxs-lookup"><span data-stu-id="0321d-138">-Force</span></span>

<span data-ttu-id="0321d-139">Заставляет командлет прекращать работу службы, даже если она зависит от служб.</span><span class="sxs-lookup"><span data-stu-id="0321d-139">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="0321d-140">-Include</span><span class="sxs-lookup"><span data-stu-id="0321d-140">-Include</span></span>

<span data-ttu-id="0321d-141">Указывает службы, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="0321d-141">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="0321d-142">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="0321d-142">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="0321d-143">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="0321d-143">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="0321d-144">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0321d-144">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0321d-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0321d-145">-InputObject</span></span>

<span data-ttu-id="0321d-146">Указывает объекты **ServiceController** , представляющие останавливаемые службы.</span><span class="sxs-lookup"><span data-stu-id="0321d-146">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="0321d-147">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="0321d-147">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="0321d-148">-Name</span><span class="sxs-lookup"><span data-stu-id="0321d-148">-Name</span></span>

<span data-ttu-id="0321d-149">Указывает имена служб для отмены.</span><span class="sxs-lookup"><span data-stu-id="0321d-149">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="0321d-150">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0321d-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0321d-151">-Неожидание</span><span class="sxs-lookup"><span data-stu-id="0321d-151">-NoWait</span></span>

<span data-ttu-id="0321d-152">Указывает, что этот командлет использует параметр No Wait.</span><span class="sxs-lookup"><span data-stu-id="0321d-152">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="0321d-153">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0321d-153">-PassThru</span></span>

<span data-ttu-id="0321d-154">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="0321d-154">Returns an object that represents the service.</span></span> <span data-ttu-id="0321d-155">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0321d-155">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0321d-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0321d-156">-Confirm</span></span>

<span data-ttu-id="0321d-157">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0321d-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0321d-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0321d-158">-WhatIf</span></span>

<span data-ttu-id="0321d-159">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0321d-159">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0321d-160">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0321d-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0321d-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0321d-161">CommonParameters</span></span>

<span data-ttu-id="0321d-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0321d-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0321d-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0321d-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0321d-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0321d-164">INPUTS</span></span>

### <span data-ttu-id="0321d-165">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="0321d-165">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="0321d-166">В этот командлет можно передать объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="0321d-166">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="0321d-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0321d-167">OUTPUTS</span></span>

### <span data-ttu-id="0321d-168">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="0321d-168">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="0321d-169">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при использовании параметра **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="0321d-169">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="0321d-170">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0321d-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0321d-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0321d-171">NOTES</span></span>

<span data-ttu-id="0321d-172">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="0321d-172">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="0321d-173">Также можно ссылаться `Stop-Service` по встроенному псевдониму **СПСВ**.</span><span class="sxs-lookup"><span data-stu-id="0321d-173">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="0321d-174">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="0321d-174">For more information, see about_Aliases.</span></span>

<span data-ttu-id="0321d-175">`Stop-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="0321d-175">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="0321d-176">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="0321d-176">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="0321d-177">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="0321d-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="0321d-178">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="0321d-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="0321d-179">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0321d-179">RELATED LINKS</span></span>

[<span data-ttu-id="0321d-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="0321d-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="0321d-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="0321d-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="0321d-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="0321d-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="0321d-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-186">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="0321d-187">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="0321d-187">Remove-Service</span></span>](Remove-Service.md)
