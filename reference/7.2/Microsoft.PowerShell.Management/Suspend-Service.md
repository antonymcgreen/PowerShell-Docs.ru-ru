---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 9515f524df38813817b3fefd1437a3e2df296392
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604592"
---
# <span data-ttu-id="77d93-102">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-102">Suspend-Service</span></span>

## <span data-ttu-id="77d93-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="77d93-103">SYNOPSIS</span></span>
<span data-ttu-id="77d93-104">Приостанавливает одну или несколько запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="77d93-104">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="77d93-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77d93-105">SYNTAX</span></span>

### <span data-ttu-id="77d93-106">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="77d93-106">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="77d93-107">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="77d93-107">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="77d93-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="77d93-108">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="77d93-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77d93-109">DESCRIPTION</span></span>

<span data-ttu-id="77d93-110">`Suspend-Service`Командлет отправляет сообщение о приостановке в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="77d93-110">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="77d93-111">При приостановке служба все еще выполняется, но ее действие останавливается до возобновления, например `Resume-Service` командлетом использовании.</span><span class="sxs-lookup"><span data-stu-id="77d93-111">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="77d93-112">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для передачи объекта службы, представляющего службы, которые необходимо приостановить.</span><span class="sxs-lookup"><span data-stu-id="77d93-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="77d93-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="77d93-113">EXAMPLES</span></span>

### <span data-ttu-id="77d93-114">Пример 1. Приостановка службы</span><span class="sxs-lookup"><span data-stu-id="77d93-114">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="77d93-115">Эта команда приостанавливает службу Telnet (Tlntsvr) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77d93-115">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="77d93-116">Пример 2. Отображение того, что произойдет при приостановке служб</span><span class="sxs-lookup"><span data-stu-id="77d93-116">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="77d93-117">Эта команда сообщает, что произойдет, если вы приостановили службы с именем службы, которое начинается с LanMan.</span><span class="sxs-lookup"><span data-stu-id="77d93-117">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="77d93-118">Чтобы приостановить службы, выполните команду без параметра **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="77d93-118">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="77d93-119">Пример 3. получение и приостановка службы</span><span class="sxs-lookup"><span data-stu-id="77d93-119">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="77d93-120">Эта команда использует `Get-Service` командлет для получения объекта, представляющего планировщик задач (расписание) службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="77d93-120">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="77d93-121">Оператор конвейера ( `|` ) передает результат в `Suspend-Service` , который приостанавливает работу службы.</span><span class="sxs-lookup"><span data-stu-id="77d93-121">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="77d93-122">Пример 4. Приостановка всех служб, которые могут быть приостановлены</span><span class="sxs-lookup"><span data-stu-id="77d93-122">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="77d93-123">Эта команда приостанавливает все службы на компьютере, которые можно приостановить.</span><span class="sxs-lookup"><span data-stu-id="77d93-123">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="77d93-124">Он использует `Get-Service` для получения объектов, представляющих службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="77d93-124">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="77d93-125">Оператор конвейера передает результаты в `Where-Object` командлет, который выбирает только те службы, значение которых равно `$True` свойству **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="77d93-125">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="77d93-126">Другой оператор конвейера передает результаты в `Suspend-Service` .</span><span class="sxs-lookup"><span data-stu-id="77d93-126">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="77d93-127">Параметр **Confirm** запрашивает подтверждение перед приостановкой каждой службы.</span><span class="sxs-lookup"><span data-stu-id="77d93-127">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="77d93-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77d93-128">PARAMETERS</span></span>

### <span data-ttu-id="77d93-129">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="77d93-129">-DisplayName</span></span>

<span data-ttu-id="77d93-130">Указывает отображаемые имена приостанавливаемых служб.</span><span class="sxs-lookup"><span data-stu-id="77d93-130">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="77d93-131">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="77d93-131">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="77d93-132">-Exclude</span><span class="sxs-lookup"><span data-stu-id="77d93-132">-Exclude</span></span>

<span data-ttu-id="77d93-133">Указывает службы, исключаемые из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="77d93-133">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="77d93-134">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="77d93-134">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="77d93-135">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="77d93-135">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="77d93-136">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="77d93-136">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="77d93-137">-Include</span><span class="sxs-lookup"><span data-stu-id="77d93-137">-Include</span></span>

<span data-ttu-id="77d93-138">Указывает службы для приостановки.</span><span class="sxs-lookup"><span data-stu-id="77d93-138">Specifies services to suspend.</span></span> <span data-ttu-id="77d93-139">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="77d93-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="77d93-140">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="77d93-140">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="77d93-141">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="77d93-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="77d93-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="77d93-142">-InputObject</span></span>

<span data-ttu-id="77d93-143">Указывает объекты **ServiceController** , представляющие службы для приостановки.</span><span class="sxs-lookup"><span data-stu-id="77d93-143">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="77d93-144">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="77d93-144">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="77d93-145">-Name</span><span class="sxs-lookup"><span data-stu-id="77d93-145">-Name</span></span>

<span data-ttu-id="77d93-146">Указывает имена служб для приостановки.</span><span class="sxs-lookup"><span data-stu-id="77d93-146">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="77d93-147">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="77d93-147">Wildcard characters are permitted.</span></span>

<span data-ttu-id="77d93-148">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="77d93-148">The parameter name is optional.</span></span> <span data-ttu-id="77d93-149">Можно использовать **имя** или его псевдоним, **ServiceName**, или можно опустить имя параметра.</span><span class="sxs-lookup"><span data-stu-id="77d93-149">You can use **Name** or its alias, **ServiceName**, or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="77d93-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="77d93-150">-PassThru</span></span>

<span data-ttu-id="77d93-151">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="77d93-151">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="77d93-152">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="77d93-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="77d93-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77d93-153">-Confirm</span></span>

<span data-ttu-id="77d93-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="77d93-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77d93-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77d93-155">-WhatIf</span></span>

<span data-ttu-id="77d93-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="77d93-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="77d93-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="77d93-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="77d93-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="77d93-158">CommonParameters</span></span>

<span data-ttu-id="77d93-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="77d93-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77d93-160">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="77d93-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77d93-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="77d93-161">INPUTS</span></span>

### <span data-ttu-id="77d93-162">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="77d93-162">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="77d93-163">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="77d93-163">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="77d93-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="77d93-164">OUTPUTS</span></span>

### <span data-ttu-id="77d93-165">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="77d93-165">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="77d93-166">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="77d93-166">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="77d93-167">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="77d93-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="77d93-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="77d93-168">NOTES</span></span>

<span data-ttu-id="77d93-169">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="77d93-169">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="77d93-170">`Suspend-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="77d93-170">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="77d93-171">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="77d93-171">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="77d93-172">`Suspend-Service` может приостанавливать только службы, которые поддерживают приостановку и возобновление работы.</span><span class="sxs-lookup"><span data-stu-id="77d93-172">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="77d93-173">Чтобы определить, можно ли приостановить конкретную службу, используйте `Get-Service` командлет вместе со свойством **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="77d93-173">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="77d93-174">Пример: `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span><span class="sxs-lookup"><span data-stu-id="77d93-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="77d93-175">Чтобы найти все службы на компьютере, которые можно приостановить, введите `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .</span><span class="sxs-lookup"><span data-stu-id="77d93-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="77d93-176">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="77d93-176">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="77d93-177">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="77d93-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="77d93-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="77d93-178">RELATED LINKS</span></span>

[<span data-ttu-id="77d93-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="77d93-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="77d93-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="77d93-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="77d93-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="77d93-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="77d93-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-185">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="77d93-186">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="77d93-186">Remove-Service</span></span>](Remove-Service.md)
