---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 8ce2182117167d93c8f7abd86eeb2c79abdf09c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602297"
---
# <span data-ttu-id="fd2e7-102">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-102">Resume-Service</span></span>

## <span data-ttu-id="fd2e7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fd2e7-103">SYNOPSIS</span></span>
<span data-ttu-id="fd2e7-104">Возобновляет одну или несколько приостановленных служб.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-104">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="fd2e7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd2e7-105">SYNTAX</span></span>

### <span data-ttu-id="fd2e7-106">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fd2e7-106">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd2e7-107">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="fd2e7-107">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fd2e7-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fd2e7-108">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd2e7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd2e7-109">DESCRIPTION</span></span>

<span data-ttu-id="fd2e7-110">`Resume-Service`Командлет отправляет сообщение о возобновлении в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-110">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="fd2e7-111">Если служба приостановлена, она возобновляется.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-111">If a service is suspended, it resumes.</span></span> <span data-ttu-id="fd2e7-112">Если в данный момент он выполняется, сообщение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-112">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="fd2e7-113">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для передачи объекта службы, представляющего службы, которые требуется возобновить.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="fd2e7-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="fd2e7-114">EXAMPLES</span></span>

### <span data-ttu-id="fd2e7-115">Пример 1. Возобновление службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="fd2e7-115">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="fd2e7-116">Эта команда возобновляет службу уведомлений о системных событиях на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-116">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="fd2e7-117">Имя службы представлено в команде Сенс.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-117">The service name is represented in the command by sens.</span></span> <span data-ttu-id="fd2e7-118">Команда использует параметр **Name** для указания имени службы службы, но команда пропускает имя параметра, так как имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-118">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="fd2e7-119">Пример 2. возобновление всех приостановленных служб</span><span class="sxs-lookup"><span data-stu-id="fd2e7-119">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="fd2e7-120">Эта команда возобновляет работу всех приостановленных служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-120">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="fd2e7-121">`Get-Service`Команда командлет возвращает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-121">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="fd2e7-122">Оператор конвейера ( `|` ) передает результаты в `Where-Object` командлет, который выбирает службы с приостановленным свойством **Status** .</span><span class="sxs-lookup"><span data-stu-id="fd2e7-122">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="fd2e7-123">Следующий оператор конвейера отправляет результаты в `Resume-Service` , что возобновляет работу приостановленных служб.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-123">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="fd2e7-124">На практике можно использовать параметр **WhatIf** для определения эффекта от команды, перед тем как выполнять ее.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="fd2e7-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd2e7-125">PARAMETERS</span></span>

### <span data-ttu-id="fd2e7-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="fd2e7-126">-DisplayName</span></span>

<span data-ttu-id="fd2e7-127">Указывает отображаемые имена служб, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-127">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="fd2e7-128">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="fd2e7-129">-Exclude</span><span class="sxs-lookup"><span data-stu-id="fd2e7-129">-Exclude</span></span>

<span data-ttu-id="fd2e7-130">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="fd2e7-131">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="fd2e7-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="fd2e7-132">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="fd2e7-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="fd2e7-133">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="fd2e7-134">-Include</span><span class="sxs-lookup"><span data-stu-id="fd2e7-134">-Include</span></span>

<span data-ttu-id="fd2e7-135">Указывает службы для возобновления.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-135">Specifies services to resume.</span></span> <span data-ttu-id="fd2e7-136">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="fd2e7-136">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="fd2e7-137">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="fd2e7-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="fd2e7-138">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="fd2e7-139">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd2e7-139">-InputObject</span></span>

<span data-ttu-id="fd2e7-140">Указывает объекты **ServiceController** , представляющие службы, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-140">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="fd2e7-141">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-141">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="fd2e7-142">-Name</span><span class="sxs-lookup"><span data-stu-id="fd2e7-142">-Name</span></span>

<span data-ttu-id="fd2e7-143">Указывает имена служб, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-143">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="fd2e7-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fd2e7-144">-PassThru</span></span>

<span data-ttu-id="fd2e7-145">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-145">Returns an object that represents the service.</span></span> <span data-ttu-id="fd2e7-146">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fd2e7-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd2e7-147">-Confirm</span></span>

<span data-ttu-id="fd2e7-148">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd2e7-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd2e7-149">-WhatIf</span></span>

<span data-ttu-id="fd2e7-150">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fd2e7-151">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-151">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd2e7-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fd2e7-152">CommonParameters</span></span>

<span data-ttu-id="fd2e7-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd2e7-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd2e7-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd2e7-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fd2e7-155">INPUTS</span></span>

### <span data-ttu-id="fd2e7-156">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="fd2e7-156">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="fd2e7-157">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-157">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="fd2e7-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fd2e7-158">OUTPUTS</span></span>

### <span data-ttu-id="fd2e7-159">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="fd2e7-159">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="fd2e7-160">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий возобновляемую службу, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="fd2e7-160">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="fd2e7-161">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fd2e7-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fd2e7-162">NOTES</span></span>

<span data-ttu-id="fd2e7-163">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-163">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="fd2e7-164">Состояние приостановленных служб приостановлено.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="fd2e7-165">Когда службы возобновляются, их состояние выполняется.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-165">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="fd2e7-166">`Resume-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-166">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="fd2e7-167">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="fd2e7-168">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="fd2e7-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="fd2e7-169">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="fd2e7-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="fd2e7-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fd2e7-170">RELATED LINKS</span></span>

[<span data-ttu-id="fd2e7-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="fd2e7-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="fd2e7-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="fd2e7-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="fd2e7-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="fd2e7-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="fd2e7-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="fd2e7-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="fd2e7-178">Remove-Service</span></span>](Remove-Service.md)
