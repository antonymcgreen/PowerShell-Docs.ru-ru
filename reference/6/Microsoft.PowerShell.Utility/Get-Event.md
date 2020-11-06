---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 1920d7a834de133b377cdab7e16851c86477c3da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229021"
---
# <span data-ttu-id="c2263-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="c2263-103">Get-Event</span></span>

## <span data-ttu-id="c2263-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c2263-104">SYNOPSIS</span></span>
<span data-ttu-id="c2263-105">Получает события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="c2263-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="c2263-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c2263-106">SYNTAX</span></span>

### <span data-ttu-id="c2263-107">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c2263-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c2263-108">Метод byid</span><span class="sxs-lookup"><span data-stu-id="c2263-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="c2263-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c2263-109">DESCRIPTION</span></span>

<span data-ttu-id="c2263-110">Командлет **Get-Event** Возвращает события в очереди событий PowerShell для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2263-110">The **Get-Event** cmdlet gets events in the PowerShell event queue for the current session.</span></span>
<span data-ttu-id="c2263-111">Чтобы указать события, можно получить все события или использовать параметр *EventIdentifier* или *SourceIdentifier* .</span><span class="sxs-lookup"><span data-stu-id="c2263-111">You can get all events or use the *EventIdentifier* or *SourceIdentifier* parameter to specify the events.</span></span>

<span data-ttu-id="c2263-112">Каждое возникающее событие добавляется в очередь событий.</span><span class="sxs-lookup"><span data-stu-id="c2263-112">When an event occurs, it is added to the event queue.</span></span>
<span data-ttu-id="c2263-113">Очередь событий включает события, которые зарегистрированы, события, созданные с помощью командлета New-Event, и событие, возникающее при завершении работы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2263-113">The event queue includes events for which you have registered, events created by using the New-Event cmdlet, and the event that is raised when PowerShell exits.</span></span>
<span data-ttu-id="c2263-114">Для получения событий можно использовать **Get-Event** или Wait-Event.</span><span class="sxs-lookup"><span data-stu-id="c2263-114">You can use **Get-Event** or Wait-Event to get the events.</span></span>

<span data-ttu-id="c2263-115">Данный командлет не получает события из журналов средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="c2263-115">This cmdlet does not get events from the Event Viewer logs.</span></span>
<span data-ttu-id="c2263-116">Для получения этих событий используются командлеты Get-WinEvent и Get-EventLog.</span><span class="sxs-lookup"><span data-stu-id="c2263-116">To get those events, use Get-WinEvent or Get-EventLog.</span></span>

## <span data-ttu-id="c2263-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="c2263-117">EXAMPLES</span></span>

### <span data-ttu-id="c2263-118">Пример 1. получение всех событий</span><span class="sxs-lookup"><span data-stu-id="c2263-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="c2263-119">Эта команда получает все события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="c2263-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="c2263-120">Пример 2. получение событий по идентификатору источника</span><span class="sxs-lookup"><span data-stu-id="c2263-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="c2263-121">Эта команда возвращает события, в которых значение свойства SourceIdentifier — PowerShell. Процесскреатед.</span><span class="sxs-lookup"><span data-stu-id="c2263-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="c2263-122">Пример 3. Получение события на основе времени его создания</span><span class="sxs-lookup"><span data-stu-id="c2263-122">Example 3: Get an event based on the time it was generated</span></span>

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

<span data-ttu-id="c2263-123">В этом примере показано, как получать события с помощью свойств, отличных от SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="c2263-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="c2263-124">Первая команда получает все события в очереди событий и сохраняет их в переменной $Events.</span><span class="sxs-lookup"><span data-stu-id="c2263-124">The first command gets all events in the event queue and saves them in the $Events variable.</span></span>

<span data-ttu-id="c2263-125">Вторая команда использует нотацию массива для получения первого события (0-index) в массиве в переменной $Events.</span><span class="sxs-lookup"><span data-stu-id="c2263-125">The second command uses array notation to get the first (0-index) event in the array in the $Events variable.</span></span>
<span data-ttu-id="c2263-126">С помощью конвейерного оператора (|) команда отправляет событие в команду Format-List, которая отображает все свойства события в списке.</span><span class="sxs-lookup"><span data-stu-id="c2263-126">The command uses a pipeline operator (|) to send the event to the Format-List command, which displays all properties of the event in a list.</span></span>
<span data-ttu-id="c2263-127">Это позволяет проверить свойства объекта события.</span><span class="sxs-lookup"><span data-stu-id="c2263-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="c2263-128">Третья команда показывает, как использовать командлет Where-Object для получения события в зависимости от времени его создания.</span><span class="sxs-lookup"><span data-stu-id="c2263-128">The third command shows how to use the Where-Object cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="c2263-129">Пример 4. Получение события по его идентификатору</span><span class="sxs-lookup"><span data-stu-id="c2263-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="c2263-130">Эта команда получает событие с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="c2263-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="c2263-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c2263-131">PARAMETERS</span></span>

### <span data-ttu-id="c2263-132">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="c2263-132">-EventIdentifier</span></span>

<span data-ttu-id="c2263-133">Указывает идентификаторы событий, для которых этот командлет получает события.</span><span class="sxs-lookup"><span data-stu-id="c2263-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2263-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="c2263-134">-SourceIdentifier</span></span>

<span data-ttu-id="c2263-135">Указывает идентификаторы источников, для которых этот командлет получает события.</span><span class="sxs-lookup"><span data-stu-id="c2263-135">Specifies source identifiers for which this cmdlet gets events.</span></span>
<span data-ttu-id="c2263-136">По умолчанию командлет получает все события в очереди.</span><span class="sxs-lookup"><span data-stu-id="c2263-136">The default is all events in the event queue.</span></span>
<span data-ttu-id="c2263-137">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="c2263-137">Wildcards are not permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2263-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c2263-138">CommonParameters</span></span>

<span data-ttu-id="c2263-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c2263-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c2263-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c2263-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c2263-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c2263-141">INPUTS</span></span>

### <span data-ttu-id="c2263-142">Нет</span><span class="sxs-lookup"><span data-stu-id="c2263-142">None</span></span>

<span data-ttu-id="c2263-143">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="c2263-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c2263-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c2263-144">OUTPUTS</span></span>

### <span data-ttu-id="c2263-145">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="c2263-145">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="c2263-146">**Get-Event** возвращает объект **PSEventArgs** для каждого события.</span><span class="sxs-lookup"><span data-stu-id="c2263-146">**Get-Event** returns a **PSEventArgs** object for each event.</span></span>
<span data-ttu-id="c2263-147">Чтобы просмотреть описание этого объекта, введите `Get-Help Get-Event -Full` и просмотрите раздел "Примечания" в разделе справки.</span><span class="sxs-lookup"><span data-stu-id="c2263-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="c2263-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c2263-148">NOTES</span></span>

* <span data-ttu-id="c2263-149">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="c2263-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="c2263-150">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="c2263-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="c2263-151">Командлет **Get-Event** возвращает объект **PSEventArgs** ( **System. Management. Automation. PSEventArgs** ) со следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="c2263-151">The **Get-Event** cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

  - <span data-ttu-id="c2263-152">ComputerName.</span><span class="sxs-lookup"><span data-stu-id="c2263-152">ComputerName.</span></span>
<span data-ttu-id="c2263-153">имя компьютера, на котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c2263-153">The name of the computer on which the event occurred.</span></span>
<span data-ttu-id="c2263-154">Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="c2263-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="c2263-155">Рунспацеид.</span><span class="sxs-lookup"><span data-stu-id="c2263-155">RunspaceId.</span></span>
<span data-ttu-id="c2263-156">GUID, однозначно идентифицирующий сеанс, в ходе которого произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c2263-156">A GUID that uniquely identifies the session in which the event occurred.</span></span>
<span data-ttu-id="c2263-157">Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="c2263-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="c2263-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="c2263-158">EventIdentifier.</span></span>
<span data-ttu-id="c2263-159">целое число (Int32), однозначно идентифицирующее уведомление о событии в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="c2263-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

  - <span data-ttu-id="c2263-160">Отправителя.</span><span class="sxs-lookup"><span data-stu-id="c2263-160">Sender.</span></span>
<span data-ttu-id="c2263-161">объект, создавший событие.</span><span class="sxs-lookup"><span data-stu-id="c2263-161">The object that generated the event.</span></span>
<span data-ttu-id="c2263-162">В значении параметра *Action* $sender автоматическая переменная содержит объект sender.</span><span class="sxs-lookup"><span data-stu-id="c2263-162">In the value of the *Action* parameter, the $Sender automatic variable contains the sender object.</span></span>

  - <span data-ttu-id="c2263-163">Саурцеевентаргс.</span><span class="sxs-lookup"><span data-stu-id="c2263-163">SourceEventArgs.</span></span>
<span data-ttu-id="c2263-164">первый параметр, который наследуется от EventArgs (если существует).</span><span class="sxs-lookup"><span data-stu-id="c2263-164">The first parameter that derives from EventArgs, if it exists.</span></span>
<span data-ttu-id="c2263-165">Например, в событии с истекшим таймером, в котором сигнатура имеет форму отправитель объекта, Timers. ElapsedEventArgs e, свойство Саурцеевентаргс будет содержать таймеры. ElapsedEventArgs.</span><span class="sxs-lookup"><span data-stu-id="c2263-165">For example, in a timer elapsed event in which the signature has the form Object sender, Timers.ElapsedEventArgs e, the SourceEventArgs property would contain the Timers.ElapsedEventArgs.</span></span>
<span data-ttu-id="c2263-166">В значении параметра *Action* $EventArgs автоматическая переменная содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="c2263-166">In the value of the *Action* parameter, the $EventArgs automatic variable contains this value.</span></span>

  - <span data-ttu-id="c2263-167">Саурцеаргс.</span><span class="sxs-lookup"><span data-stu-id="c2263-167">SourceArgs.</span></span>
<span data-ttu-id="c2263-168">все параметры сигнатуры исходного события.</span><span class="sxs-lookup"><span data-stu-id="c2263-168">All parameters of the original event signature.</span></span>
<span data-ttu-id="c2263-169">Для стандартной сигнатуры события $Args \[ 0 \] соответствует отправителю, а $args \[ 1 \] — саурцеевентаргс.</span><span class="sxs-lookup"><span data-stu-id="c2263-169">For a standard event signature, $Args\[0\] represents the sender, and $Args\[1\] represents the SourceEventArgs.</span></span>
<span data-ttu-id="c2263-170">В значении параметра *Action* $args автоматическая переменная содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="c2263-170">In the value of the *Action* parameter, the $Args automatic variable contains this value.</span></span>

  - <span data-ttu-id="c2263-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="c2263-171">SourceIdentifier.</span></span>
<span data-ttu-id="c2263-172">cтрока, идентифицирующая подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="c2263-172">A string that identifies the event subscription.</span></span>
<span data-ttu-id="c2263-173">В значении параметра *Action* свойство SourceIdentifier автоматической переменной $Event содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="c2263-173">In the value of the *Action* parameter, the SourceIdentifier property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="c2263-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="c2263-174">TimeGenerated.</span></span>
<span data-ttu-id="c2263-175">Объект **DateTime** , представляющий время создания события.</span><span class="sxs-lookup"><span data-stu-id="c2263-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
<span data-ttu-id="c2263-176">В значении параметра *Action* свойство timegenerated автоматической переменной $Event содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="c2263-176">In the value of the *Action* parameter, the TimeGenerated property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="c2263-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="c2263-177">MessageData.</span></span>
<span data-ttu-id="c2263-178">данные, связанные с подпиской на событие.</span><span class="sxs-lookup"><span data-stu-id="c2263-178">Data associated with the event subscription.</span></span>
<span data-ttu-id="c2263-179">Пользователи указывают эти данные при регистрации события.</span><span class="sxs-lookup"><span data-stu-id="c2263-179">Users specify this data when they register an event.</span></span>
<span data-ttu-id="c2263-180">В значении параметра *Action* свойство MessageData автоматической переменной $Event содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="c2263-180">In the value of the *Action* parameter, the MessageData property of the $Event automatic variable contains this value.</span></span>

## <span data-ttu-id="c2263-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c2263-181">RELATED LINKS</span></span>

[<span data-ttu-id="c2263-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="c2263-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="c2263-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="c2263-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="c2263-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="c2263-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="c2263-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="c2263-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="c2263-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="c2263-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="c2263-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="c2263-187">Wait-Event</span></span>](Wait-Event.md)