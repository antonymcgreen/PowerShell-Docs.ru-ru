---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: b5af4f55166993e54048dd76bb8345550718c170
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227905"
---
# <span data-ttu-id="e6f97-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-103">Restart-Service</span></span>

## <span data-ttu-id="e6f97-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e6f97-104">SYNOPSIS</span></span>
<span data-ttu-id="e6f97-105">Перезапускает одну или несколько служб.</span><span class="sxs-lookup"><span data-stu-id="e6f97-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="e6f97-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6f97-106">SYNTAX</span></span>

### <span data-ttu-id="e6f97-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e6f97-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e6f97-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e6f97-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e6f97-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e6f97-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e6f97-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6f97-110">DESCRIPTION</span></span>

<span data-ttu-id="e6f97-111">Командлет **Restart-Service** отправляет сообщение об ошибке, а затем начальное сообщение в контроллер служб Windows для указанной службы.</span><span class="sxs-lookup"><span data-stu-id="e6f97-111">The **Restart-Service** cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span>
<span data-ttu-id="e6f97-112">Если служба уже остановлена, она запускается без уведомления об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e6f97-112">If a service was already stopped, it is started without notifying you of an error.</span></span>
<span data-ttu-id="e6f97-113">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта, представляющего каждую службу, которую требуется перезапустить.</span><span class="sxs-lookup"><span data-stu-id="e6f97-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="e6f97-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="e6f97-114">EXAMPLES</span></span>

### <span data-ttu-id="e6f97-115">Пример 1. Перезапуск службы на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="e6f97-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="e6f97-116">Эта команда перезапускает службу инструментария управления Windows (WinMgmt) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6f97-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="e6f97-117">Пример 2. Исключение службы</span><span class="sxs-lookup"><span data-stu-id="e6f97-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="e6f97-118">Эта команда перезапускает службы с отображаемым именем, которое начинается с Net, за исключением службы Net Logon.</span><span class="sxs-lookup"><span data-stu-id="e6f97-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="e6f97-119">Пример 3. Запуск всех остановленных сетевых служб</span><span class="sxs-lookup"><span data-stu-id="e6f97-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="e6f97-120">Эта команда запускает все остановленные сетевые службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6f97-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="e6f97-121">Она использует командлет Get-Service для получения объектов, представляющих службы, имена которых начинаются с net.</span><span class="sxs-lookup"><span data-stu-id="e6f97-121">This command uses the Get-Service cmdlet to get objects that represent the services whose service name starts with net.</span></span>
<span data-ttu-id="e6f97-122">Конвейерный оператор (|) отправляет объект служб в командлет Where-Object, который выбирает только службы с состоянием "Остановлена".</span><span class="sxs-lookup"><span data-stu-id="e6f97-122">The pipeline operator (|) sends the services object to the Where-Object cmdlet, which selects only the services that have a status of stopped.</span></span>
<span data-ttu-id="e6f97-123">Другой конвейерный оператор отправляет выбранные службы в **Restart-Service** .</span><span class="sxs-lookup"><span data-stu-id="e6f97-123">Another pipeline operator sends the selected services to **Restart-Service** .</span></span>

<span data-ttu-id="e6f97-124">На практике можно использовать параметр *WhatIf* для определения эффекта от команды, перед тем как выполнять ее.</span><span class="sxs-lookup"><span data-stu-id="e6f97-124">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="e6f97-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6f97-125">PARAMETERS</span></span>

### <span data-ttu-id="e6f97-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="e6f97-126">-DisplayName</span></span>

<span data-ttu-id="e6f97-127">Указывает отображаемые имена перезапускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="e6f97-127">Specifies the display names of services to restarted.</span></span>
<span data-ttu-id="e6f97-128">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e6f97-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e6f97-129">-Exclude</span><span class="sxs-lookup"><span data-stu-id="e6f97-129">-Exclude</span></span>

<span data-ttu-id="e6f97-130">Указывает службы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e6f97-130">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="e6f97-131">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="e6f97-131">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e6f97-132">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="e6f97-132">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="e6f97-133">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e6f97-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e6f97-134">-Force</span><span class="sxs-lookup"><span data-stu-id="e6f97-134">-Force</span></span>

<span data-ttu-id="e6f97-135">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6f97-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e6f97-136">-Include</span><span class="sxs-lookup"><span data-stu-id="e6f97-136">-Include</span></span>

<span data-ttu-id="e6f97-137">Указывает службы, Перезапускаемые этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="e6f97-137">Specifies services that this cmdlet restarts.</span></span>
<span data-ttu-id="e6f97-138">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="e6f97-138">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e6f97-139">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="e6f97-139">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="e6f97-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e6f97-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e6f97-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e6f97-141">-InputObject</span></span>

<span data-ttu-id="e6f97-142">Указывает объекты **ServiceController** , представляющие службы для перезапуска.</span><span class="sxs-lookup"><span data-stu-id="e6f97-142">Specifies **ServiceController** objects that represent the services to restart.</span></span>
<span data-ttu-id="e6f97-143">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="e6f97-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="e6f97-144">-Name</span><span class="sxs-lookup"><span data-stu-id="e6f97-144">-Name</span></span>

<span data-ttu-id="e6f97-145">Указывает имена перезапускаемых служб.</span><span class="sxs-lookup"><span data-stu-id="e6f97-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="e6f97-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e6f97-146">-PassThru</span></span>

<span data-ttu-id="e6f97-147">Возвращает объект, представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="e6f97-147">Returns an object that represents the service.</span></span>
<span data-ttu-id="e6f97-148">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e6f97-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e6f97-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e6f97-149">-Confirm</span></span>

<span data-ttu-id="e6f97-150">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e6f97-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e6f97-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e6f97-151">-WhatIf</span></span>

<span data-ttu-id="e6f97-152">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e6f97-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e6f97-153">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e6f97-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e6f97-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e6f97-154">CommonParameters</span></span>

<span data-ttu-id="e6f97-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6f97-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6f97-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6f97-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6f97-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e6f97-157">INPUTS</span></span>

### <span data-ttu-id="e6f97-158">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="e6f97-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="e6f97-159">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="e6f97-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="e6f97-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e6f97-160">OUTPUTS</span></span>

### <span data-ttu-id="e6f97-161">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="e6f97-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="e6f97-162">При указании параметра *PassThru* этот командлет создает объект **System.ServiceProcess.ServiceController** , представляющий перезапускаемую службу.</span><span class="sxs-lookup"><span data-stu-id="e6f97-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="e6f97-163">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e6f97-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e6f97-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e6f97-164">NOTES</span></span>

* <span data-ttu-id="e6f97-165">**Restart-Service** может управлять службами, только когда у текущего пользователя есть соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="e6f97-165">**Restart-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="e6f97-166">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="e6f97-166">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="e6f97-167">Чтобы найти имена службы и отображаемые имена служб в системе, введите команду **Get-Service** .</span><span class="sxs-lookup"><span data-stu-id="e6f97-167">To find the service names and display names of the services on your system, type **Get-Service** ".</span></span> <span data-ttu-id="e6f97-168">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="e6f97-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="e6f97-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e6f97-169">RELATED LINKS</span></span>

[<span data-ttu-id="e6f97-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="e6f97-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="e6f97-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="e6f97-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="e6f97-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="e6f97-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="e6f97-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="e6f97-176">Suspend-Service</span></span>](Suspend-Service.md)