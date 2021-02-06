---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: f88e07e36ec7c6adf7f24e2c6e57ae5864eb1a60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605051"
---
# <span data-ttu-id="04217-102">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="04217-102">Restart-Service</span></span>

## <span data-ttu-id="04217-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04217-103">SYNOPSIS</span></span>
<span data-ttu-id="04217-104">Перезапускает одну или несколько служб.</span><span class="sxs-lookup"><span data-stu-id="04217-104">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="04217-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04217-105">SYNTAX</span></span>

### <span data-ttu-id="04217-106">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="04217-106">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="04217-107">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="04217-107">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="04217-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="04217-108">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="04217-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04217-109">DESCRIPTION</span></span>

<span data-ttu-id="04217-110">`Restart-Service`Командлет отправляет сообщение об ошибке, а затем начальное сообщение в контроллер служб Windows для указанной службы.</span><span class="sxs-lookup"><span data-stu-id="04217-110">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="04217-111">Если служба уже остановлена, она запускается без уведомления об ошибке.</span><span class="sxs-lookup"><span data-stu-id="04217-111">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="04217-112">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для передачи объекта, представляющего каждую службу, которую требуется перезапустить.</span><span class="sxs-lookup"><span data-stu-id="04217-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="04217-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="04217-113">EXAMPLES</span></span>

### <span data-ttu-id="04217-114">Пример 1. Перезапуск службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="04217-114">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="04217-115">Эта команда перезапускает службу инструментария управления Windows (WinMgmt) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="04217-115">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="04217-116">Пример 2. Исключение службы</span><span class="sxs-lookup"><span data-stu-id="04217-116">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="04217-117">Эта команда перезапускает службы с отображаемым именем, которое начинается с Net, за исключением службы Net Logon.</span><span class="sxs-lookup"><span data-stu-id="04217-117">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="04217-118">Пример 3. Запуск всех остановленных сетевых служб</span><span class="sxs-lookup"><span data-stu-id="04217-118">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="04217-119">Эта команда запускает все остановленные сетевые службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="04217-119">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="04217-120">Эта команда использует `Get-Service` командлет для получения объектов, представляющих службы, имя службы которых начинается с net.</span><span class="sxs-lookup"><span data-stu-id="04217-120">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="04217-121">Оператор конвейера ( `|` ) отправляет объект служб в `Where-Object` командлет, который выбирает только службы с состоянием "остановлено".</span><span class="sxs-lookup"><span data-stu-id="04217-121">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="04217-122">Другой конвейерный оператор отправляет выбранные службы в `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="04217-122">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="04217-123">На практике можно использовать параметр **WhatIf** для определения эффекта от команды, перед тем как выполнять ее.</span><span class="sxs-lookup"><span data-stu-id="04217-123">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="04217-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04217-124">PARAMETERS</span></span>

### <span data-ttu-id="04217-125">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="04217-125">-DisplayName</span></span>

<span data-ttu-id="04217-126">Указывает отображаемые имена перезапускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="04217-126">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="04217-127">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="04217-127">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="04217-128">-Exclude</span><span class="sxs-lookup"><span data-stu-id="04217-128">-Exclude</span></span>

<span data-ttu-id="04217-129">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="04217-129">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="04217-130">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="04217-130">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="04217-131">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="04217-131">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="04217-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="04217-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="04217-133">-Force</span><span class="sxs-lookup"><span data-stu-id="04217-133">-Force</span></span>

<span data-ttu-id="04217-134">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="04217-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="04217-135">-Include</span><span class="sxs-lookup"><span data-stu-id="04217-135">-Include</span></span>

<span data-ttu-id="04217-136">Указывает службы, Перезапускаемые этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="04217-136">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="04217-137">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="04217-137">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="04217-138">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="04217-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="04217-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="04217-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="04217-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="04217-140">-InputObject</span></span>

<span data-ttu-id="04217-141">Указывает объекты **ServiceController** , представляющие службы для перезапуска.</span><span class="sxs-lookup"><span data-stu-id="04217-141">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="04217-142">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="04217-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="04217-143">-Name</span><span class="sxs-lookup"><span data-stu-id="04217-143">-Name</span></span>

<span data-ttu-id="04217-144">Указывает имена перезапускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="04217-144">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="04217-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="04217-145">-PassThru</span></span>

<span data-ttu-id="04217-146">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="04217-146">Returns an object that represents the service.</span></span> <span data-ttu-id="04217-147">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="04217-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="04217-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="04217-148">-Confirm</span></span>

<span data-ttu-id="04217-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="04217-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="04217-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="04217-150">-WhatIf</span></span>

<span data-ttu-id="04217-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="04217-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="04217-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="04217-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="04217-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="04217-153">CommonParameters</span></span>

<span data-ttu-id="04217-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04217-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04217-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04217-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04217-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="04217-156">INPUTS</span></span>

### <span data-ttu-id="04217-157">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="04217-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="04217-158">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="04217-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="04217-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="04217-159">OUTPUTS</span></span>

### <span data-ttu-id="04217-160">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="04217-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="04217-161">При указании параметра **PassThru** этот командлет создает объект **System.ServiceProcess.ServiceController**, представляющий перезапускаемую службу.</span><span class="sxs-lookup"><span data-stu-id="04217-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="04217-162">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="04217-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="04217-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="04217-163">NOTES</span></span>

<span data-ttu-id="04217-164">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="04217-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="04217-165">`Restart-Service` может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="04217-165">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="04217-166">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="04217-166">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="04217-167">Чтобы найти имена службы и отображаемые имена служб в системе, введите `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="04217-167">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="04217-168">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="04217-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="04217-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="04217-169">RELATED LINKS</span></span>

[<span data-ttu-id="04217-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="04217-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="04217-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="04217-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="04217-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="04217-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="04217-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="04217-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="04217-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="04217-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="04217-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="04217-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="04217-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="04217-176">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="04217-177">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="04217-177">Remove-Service</span></span>](Remove-Service.md)
