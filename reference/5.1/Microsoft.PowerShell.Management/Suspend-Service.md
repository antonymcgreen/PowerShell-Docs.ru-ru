---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 529edca36e63d9a72d2a300ebc8c6c26033db0d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227838"
---
# <span data-ttu-id="34699-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="34699-103">Suspend-Service</span></span>

## <span data-ttu-id="34699-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="34699-104">SYNOPSIS</span></span>
<span data-ttu-id="34699-105">Приостанавливает одну или несколько запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="34699-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="34699-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34699-106">SYNTAX</span></span>

### <span data-ttu-id="34699-107">InputObject (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="34699-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="34699-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="34699-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="34699-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="34699-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="34699-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="34699-110">DESCRIPTION</span></span>

<span data-ttu-id="34699-111">Командлет **Suspend-Service** отправляет сообщение о приостановке в контроллер служб Windows для каждой из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="34699-111">The **Suspend-Service** cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="34699-112">При приостановке служба все еще выполняется, но ее действие останавливается до возобновления, например с помощью командлета использовании Resume-Service.</span><span class="sxs-lookup"><span data-stu-id="34699-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe Resume-Service cmdlet.</span></span>
<span data-ttu-id="34699-113">Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта службы, представляющего службы, которые необходимо приостановить.</span><span class="sxs-lookup"><span data-stu-id="34699-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="34699-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="34699-114">EXAMPLES</span></span>

### <span data-ttu-id="34699-115">Пример 1. Приостановка службы</span><span class="sxs-lookup"><span data-stu-id="34699-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="34699-116">Эта команда приостанавливает службу Telnet (Tlntsvr) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34699-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="34699-117">Пример 2. Отображение того, что произойдет при приостановке служб</span><span class="sxs-lookup"><span data-stu-id="34699-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="34699-118">Эта команда сообщает, что произойдет, если вы приостановили службы с именем службы, которое начинается с LanMan.</span><span class="sxs-lookup"><span data-stu-id="34699-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span>
<span data-ttu-id="34699-119">Чтобы приостановить службы, выполните команду без параметра *WhatIf* .</span><span class="sxs-lookup"><span data-stu-id="34699-119">To suspend the services, rerun the command without the *WhatIf* parameter.</span></span>

### <span data-ttu-id="34699-120">Пример 3. получение и приостановка службы</span><span class="sxs-lookup"><span data-stu-id="34699-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="34699-121">Эта команда использует командлет **Get-Service** для получения объекта, представляющего планировщик задач (расписание) службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="34699-121">This command uses the **Get-Service** cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span>
<span data-ttu-id="34699-122">Оператор конвейера (|) передает результат в **Suspend-Service** , который приостанавливает работу службы.</span><span class="sxs-lookup"><span data-stu-id="34699-122">The pipeline operator (|) passes the result to **Suspend-Service** , which suspends the service.</span></span>

### <span data-ttu-id="34699-123">Пример 4. Приостановка всех служб, которые могут быть приостановлены</span><span class="sxs-lookup"><span data-stu-id="34699-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="34699-124">Эта команда приостанавливает все службы на компьютере, которые можно приостановить.</span><span class="sxs-lookup"><span data-stu-id="34699-124">This command suspends all of the services on the computer that can be suspended.</span></span>
<span data-ttu-id="34699-125">Он использует **Get-Service** для получения объектов, представляющих службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="34699-125">It uses **Get-Service** to get objects that represent the services on the computer.</span></span>
<span data-ttu-id="34699-126">Оператор конвейера передает результаты в командлет Where-Object, который выбирает только службы со значением $True для свойства **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="34699-126">The pipeline operator passes the results to the Where-Object cmdlet, which selects only the services that have a value of $True for the **CanPauseAndContinue** property.</span></span>
<span data-ttu-id="34699-127">Другой оператор конвейера передает результаты в **Suspend-Service** .</span><span class="sxs-lookup"><span data-stu-id="34699-127">Another pipeline operator passes the results to **Suspend-Service** .</span></span>
<span data-ttu-id="34699-128">Параметр *Confirm* запрашивает подтверждение перед приостановкой каждой службы.</span><span class="sxs-lookup"><span data-stu-id="34699-128">The *Confirm* parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="34699-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34699-129">PARAMETERS</span></span>

### <span data-ttu-id="34699-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="34699-130">-DisplayName</span></span>

<span data-ttu-id="34699-131">Указывает отображаемые имена приостанавливаемых служб.</span><span class="sxs-lookup"><span data-stu-id="34699-131">Specifies the display names of the services to be suspended.</span></span>
<span data-ttu-id="34699-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="34699-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="34699-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="34699-133">-Exclude</span></span>

<span data-ttu-id="34699-134">Указывает службы, исключаемые из указанных служб.</span><span class="sxs-lookup"><span data-stu-id="34699-134">Specifies services to omit from the specified services.</span></span>
<span data-ttu-id="34699-135">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="34699-135">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="34699-136">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="34699-136">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="34699-137">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="34699-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="34699-138">-Include</span><span class="sxs-lookup"><span data-stu-id="34699-138">-Include</span></span>

<span data-ttu-id="34699-139">Указывает службы для приостановки.</span><span class="sxs-lookup"><span data-stu-id="34699-139">Specifies services to suspend.</span></span>
<span data-ttu-id="34699-140">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="34699-140">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="34699-141">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="34699-141">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="34699-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="34699-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="34699-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="34699-143">-InputObject</span></span>

<span data-ttu-id="34699-144">Указывает объекты **ServiceController** , представляющие службы для приостановки.</span><span class="sxs-lookup"><span data-stu-id="34699-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span>
<span data-ttu-id="34699-145">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="34699-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="34699-146">-Name</span><span class="sxs-lookup"><span data-stu-id="34699-146">-Name</span></span>

<span data-ttu-id="34699-147">Указывает имена служб для приостановки.</span><span class="sxs-lookup"><span data-stu-id="34699-147">Specifies the service names of the services to suspend.</span></span>
<span data-ttu-id="34699-148">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="34699-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="34699-149">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="34699-149">The parameter name is optional.</span></span>
<span data-ttu-id="34699-150">Можно использовать *имя* или его псевдоним, *ServiceName* , или можно опустить имя параметра.</span><span class="sxs-lookup"><span data-stu-id="34699-150">You can use *Name* or its alias, *ServiceName* , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="34699-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="34699-151">-PassThru</span></span>

<span data-ttu-id="34699-152">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="34699-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="34699-153">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="34699-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="34699-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="34699-154">-Confirm</span></span>

<span data-ttu-id="34699-155">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="34699-155">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="34699-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="34699-156">-WhatIf</span></span>

<span data-ttu-id="34699-157">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="34699-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="34699-158">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="34699-158">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="34699-159">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="34699-159">CommonParameters</span></span>

<span data-ttu-id="34699-160">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="34699-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34699-161">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="34699-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34699-162">Входные данные</span><span class="sxs-lookup"><span data-stu-id="34699-162">INPUTS</span></span>

### <span data-ttu-id="34699-163">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="34699-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="34699-164">В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.</span><span class="sxs-lookup"><span data-stu-id="34699-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="34699-165">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="34699-165">OUTPUTS</span></span>

### <span data-ttu-id="34699-166">Нет или System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="34699-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="34699-167">Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, если указан параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="34699-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="34699-168">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="34699-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="34699-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="34699-169">NOTES</span></span>

* <span data-ttu-id="34699-170">**Suspend-Service** может управлять службами, только если у текущего пользователя есть разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="34699-170">**Suspend-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="34699-171">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="34699-171">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="34699-172">**Suspend-Service** может приостановить только службы, которые поддерживают приостановку и возобновление работы.</span><span class="sxs-lookup"><span data-stu-id="34699-172">**Suspend-Service** can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="34699-173">Чтобы определить, можно ли приостановить конкретную службу, используйте командлет Get-Service вместе со свойством **CanPauseAndContinue** .</span><span class="sxs-lookup"><span data-stu-id="34699-173">To determine whether a particular service can be suspended, use the Get-Service cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="34699-174">Например, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span><span class="sxs-lookup"><span data-stu-id="34699-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="34699-175">Чтобы найти все службы на компьютере, которые можно приостановить, введите `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .</span><span class="sxs-lookup"><span data-stu-id="34699-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
* <span data-ttu-id="34699-176">Чтобы найти имена службы и отображаемые имена служб в системе, введите **Get-Service** .</span><span class="sxs-lookup"><span data-stu-id="34699-176">To find the service names and display names of the services on your system, type **Get-Service** .</span></span> <span data-ttu-id="34699-177">Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="34699-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="34699-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="34699-178">RELATED LINKS</span></span>

[<span data-ttu-id="34699-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="34699-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="34699-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="34699-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="34699-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="34699-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="34699-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="34699-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="34699-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="34699-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="34699-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="34699-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="34699-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="34699-185">Stop-Service</span></span>](Stop-Service.md)
