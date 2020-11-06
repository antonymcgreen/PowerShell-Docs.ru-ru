---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: a799326c943b09b5b9c0f9cecfdae3b64e6af409
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226289"
---
# <span data-ttu-id="2d624-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-103">Resume-Service</span></span>

## <span data-ttu-id="2d624-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2d624-104">SYNOPSIS</span></span>
<span data-ttu-id="2d624-105">Возобновляет одну или несколько приостановленных служб.</span><span class="sxs-lookup"><span data-stu-id="2d624-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="2d624-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d624-106">SYNTAX</span></span>

### <span data-ttu-id="2d624-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2d624-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2d624-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="2d624-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2d624-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2d624-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2d624-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d624-110">DESCRIPTION</span></span>

<span data-ttu-id="2d624-111">Командлет **Resume-Service** отправляет сообщение о возобновлении в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="2d624-111">The **Resume-Service** cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="2d624-112">Если служба приостановлена, она возобновляется.</span><span class="sxs-lookup"><span data-stu-id="2d624-112">If a service is suspended, it resumes.</span></span>
<span data-ttu-id="2d624-113">Если в данный момент он выполняется, сообщение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2d624-113">If it is currently running, the message is ignored.</span></span>
<span data-ttu-id="2d624-114">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта службы, представляющего службы, которые требуется возобновить.</span><span class="sxs-lookup"><span data-stu-id="2d624-114">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="2d624-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d624-115">EXAMPLES</span></span>

### <span data-ttu-id="2d624-116">Пример 1. Возобновление службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="2d624-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="2d624-117">Эта команда возобновляет службу уведомлений о системных событиях на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d624-117">This command resumes the System Event Notification service  on the local computer.</span></span>
<span data-ttu-id="2d624-118">Имя службы представлено в команде Сенс.</span><span class="sxs-lookup"><span data-stu-id="2d624-118">The service name is represented in the command by sens.</span></span>
<span data-ttu-id="2d624-119">Команда использует параметр *Name* для указания имени службы службы, но команда пропускает имя параметра, так как имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2d624-119">The command uses the *Name* parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="2d624-120">Пример 2. возобновление всех приостановленных служб</span><span class="sxs-lookup"><span data-stu-id="2d624-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="2d624-121">Эта команда возобновляет работу всех приостановленных служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d624-121">This command resumes all of the suspended  services on the computer.</span></span>
<span data-ttu-id="2d624-122">Команда Get-Service командлет возвращает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d624-122">The Get-Service cmdlet command gets all of the services on the computer.</span></span>
<span data-ttu-id="2d624-123">Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает службы с приостановленным свойством **Status** .</span><span class="sxs-lookup"><span data-stu-id="2d624-123">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the services that have a **Status** property of Paused.</span></span>
<span data-ttu-id="2d624-124">Следующий оператор конвейера отправляет результаты в **Resume-Service** , что возобновляет работу приостановленных служб.</span><span class="sxs-lookup"><span data-stu-id="2d624-124">The next pipeline operator sends the results to **Resume-Service** , which resumes the paused services.</span></span>

<span data-ttu-id="2d624-125">На практике можно использовать параметр *WhatIf* для определения эффекта от команды, перед тем как выполнять ее.</span><span class="sxs-lookup"><span data-stu-id="2d624-125">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="2d624-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d624-126">PARAMETERS</span></span>

### <span data-ttu-id="2d624-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="2d624-127">-DisplayName</span></span>

<span data-ttu-id="2d624-128">Указывает отображаемые имена служб, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="2d624-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="2d624-129">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2d624-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d624-130">-Exclude</span><span class="sxs-lookup"><span data-stu-id="2d624-130">-Exclude</span></span>

<span data-ttu-id="2d624-131">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="2d624-131">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="2d624-132">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="2d624-132">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="2d624-133">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="2d624-133">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="2d624-134">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2d624-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d624-135">-Include</span><span class="sxs-lookup"><span data-stu-id="2d624-135">-Include</span></span>

<span data-ttu-id="2d624-136">Указывает службы для возобновления.</span><span class="sxs-lookup"><span data-stu-id="2d624-136">Specifies services to resume.</span></span>
<span data-ttu-id="2d624-137">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="2d624-137">The value of this parameter qualifies *Name* parameter.</span></span>
<span data-ttu-id="2d624-138">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="2d624-138">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="2d624-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2d624-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d624-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2d624-140">-InputObject</span></span>

<span data-ttu-id="2d624-141">Указывает объекты **ServiceController** , представляющие службы, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="2d624-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span>
<span data-ttu-id="2d624-142">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="2d624-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="2d624-143">-Name</span><span class="sxs-lookup"><span data-stu-id="2d624-143">-Name</span></span>

<span data-ttu-id="2d624-144">Указывает имена служб, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="2d624-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="2d624-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2d624-145">-PassThru</span></span>

<span data-ttu-id="2d624-146">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="2d624-146">Returns an object that represents the service.</span></span>
<span data-ttu-id="2d624-147">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2d624-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2d624-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2d624-148">-Confirm</span></span>

<span data-ttu-id="2d624-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2d624-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2d624-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2d624-150">-WhatIf</span></span>

<span data-ttu-id="2d624-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2d624-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2d624-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2d624-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2d624-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2d624-153">CommonParameters</span></span>

<span data-ttu-id="2d624-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d624-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d624-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d624-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d624-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2d624-156">INPUTS</span></span>

### <span data-ttu-id="2d624-157">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="2d624-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="2d624-158">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="2d624-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="2d624-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2d624-159">OUTPUTS</span></span>

### <span data-ttu-id="2d624-160">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="2d624-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="2d624-161">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий возобновляемую службу, если указан параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="2d624-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="2d624-162">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2d624-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2d624-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2d624-163">NOTES</span></span>

* <span data-ttu-id="2d624-164">Состояние приостановленных служб приостановлено.</span><span class="sxs-lookup"><span data-stu-id="2d624-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="2d624-165">Когда службы возобновляются, их состояние выполняется.</span><span class="sxs-lookup"><span data-stu-id="2d624-165">When services are resumed, their status is Running.</span></span>
* <span data-ttu-id="2d624-166">**Resume-Service** может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="2d624-166">**Resume-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="2d624-167">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="2d624-167">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="2d624-168">Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="2d624-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="2d624-169">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="2d624-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="2d624-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2d624-170">RELATED LINKS</span></span>

[<span data-ttu-id="2d624-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="2d624-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="2d624-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="2d624-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="2d624-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="2d624-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="2d624-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="2d624-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="2d624-178">Remove-Service</span></span>](Remove-Service.md)