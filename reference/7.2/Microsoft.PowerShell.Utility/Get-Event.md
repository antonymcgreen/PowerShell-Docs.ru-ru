---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 4b275d489984f85aea401b781e38c80fbc4b2177
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602498"
---
# <span data-ttu-id="822e7-102">Get-Event</span><span class="sxs-lookup"><span data-stu-id="822e7-102">Get-Event</span></span>

## <span data-ttu-id="822e7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="822e7-103">SYNOPSIS</span></span>
<span data-ttu-id="822e7-104">Получает события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="822e7-104">Gets the events in the event queue.</span></span>

## <span data-ttu-id="822e7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="822e7-105">SYNTAX</span></span>

### <span data-ttu-id="822e7-106">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="822e7-106">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="822e7-107">Метод byid</span><span class="sxs-lookup"><span data-stu-id="822e7-107">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="822e7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="822e7-108">DESCRIPTION</span></span>

<span data-ttu-id="822e7-109">`Get-Event`Командлет возвращает события в очереди событий PowerShell для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="822e7-109">The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session.</span></span> <span data-ttu-id="822e7-110">Чтобы указать события, можно получить все события или использовать параметр **EventIdentifier** или **SourceIdentifier** .</span><span class="sxs-lookup"><span data-stu-id="822e7-110">You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.</span></span>

<span data-ttu-id="822e7-111">Каждое возникающее событие добавляется в очередь событий.</span><span class="sxs-lookup"><span data-stu-id="822e7-111">When an event occurs, it is added to the event queue.</span></span> <span data-ttu-id="822e7-112">Очередь событий включает события, которые зарегистрированы, события, созданные с помощью `New-Event` командлета, и событие, возникающее при завершении работы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="822e7-112">The event queue includes events for which you have registered, events created by using the `New-Event` cmdlet, and the event that is raised when PowerShell exits.</span></span> <span data-ttu-id="822e7-113">`Get-Event` `Wait-Event` Для получения событий можно использовать или.</span><span class="sxs-lookup"><span data-stu-id="822e7-113">You can use `Get-Event` or `Wait-Event` to get the events.</span></span>

<span data-ttu-id="822e7-114">Данный командлет не получает события из журналов средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="822e7-114">This cmdlet does not get events from the Event Viewer logs.</span></span> <span data-ttu-id="822e7-115">Чтобы получить эти события, используйте `Get-WinEvent` или `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="822e7-115">To get those events, use `Get-WinEvent` or `Get-EventLog`.</span></span>

## <span data-ttu-id="822e7-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="822e7-116">EXAMPLES</span></span>

### <span data-ttu-id="822e7-117">Пример 1. получение всех событий</span><span class="sxs-lookup"><span data-stu-id="822e7-117">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="822e7-118">Эта команда получает все события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="822e7-118">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="822e7-119">Пример 2. получение событий по идентификатору источника</span><span class="sxs-lookup"><span data-stu-id="822e7-119">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="822e7-120">Эта команда возвращает события, в которых значение свойства SourceIdentifier — PowerShell. Процесскреатед.</span><span class="sxs-lookup"><span data-stu-id="822e7-120">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="822e7-121">Пример 3. Получение события на основе времени его создания</span><span class="sxs-lookup"><span data-stu-id="822e7-121">Example 3: Get an event based on the time it was generated</span></span>

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

<span data-ttu-id="822e7-122">В этом примере показано, как получать события с помощью свойств, отличных от SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="822e7-122">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="822e7-123">Первая команда получает все события в очереди событий и сохраняет их в `$Events` переменной.</span><span class="sxs-lookup"><span data-stu-id="822e7-123">The first command gets all events in the event queue and saves them in the `$Events` variable.</span></span>

<span data-ttu-id="822e7-124">Вторая команда использует нотацию массива для получения первого события (0-index) в массиве `$Events` переменной.</span><span class="sxs-lookup"><span data-stu-id="822e7-124">The second command uses array notation to get the first (0-index) event in the array in the `$Events` variable.</span></span> <span data-ttu-id="822e7-125">Команда использует оператор конвейера ( `|` ) для отправки события в `Format-List` команду, которая отображает все свойства события в списке.</span><span class="sxs-lookup"><span data-stu-id="822e7-125">The command uses a pipeline operator (`|`) to send the event to the `Format-List` command, which displays all properties of the event in a list.</span></span> <span data-ttu-id="822e7-126">Это позволяет проверить свойства объекта события.</span><span class="sxs-lookup"><span data-stu-id="822e7-126">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="822e7-127">Третья команда показывает, как использовать `Where-Object` командлет для получения события в зависимости от времени его создания.</span><span class="sxs-lookup"><span data-stu-id="822e7-127">The third command shows how to use the `Where-Object` cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="822e7-128">Пример 4. Получение события по его идентификатору</span><span class="sxs-lookup"><span data-stu-id="822e7-128">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="822e7-129">Эта команда получает событие с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="822e7-129">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="822e7-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="822e7-130">PARAMETERS</span></span>

### <span data-ttu-id="822e7-131">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="822e7-131">-EventIdentifier</span></span>

<span data-ttu-id="822e7-132">Указывает идентификаторы событий, для которых этот командлет получает события.</span><span class="sxs-lookup"><span data-stu-id="822e7-132">Specifies the event identifiers for which this cmdlet gets events.</span></span>

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

### <span data-ttu-id="822e7-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="822e7-133">-SourceIdentifier</span></span>

<span data-ttu-id="822e7-134">Указывает идентификаторы источников, для которых этот командлет получает события.</span><span class="sxs-lookup"><span data-stu-id="822e7-134">Specifies source identifiers for which this cmdlet gets events.</span></span> <span data-ttu-id="822e7-135">По умолчанию командлет получает все события в очереди.</span><span class="sxs-lookup"><span data-stu-id="822e7-135">The default is all events in the event queue.</span></span> <span data-ttu-id="822e7-136">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="822e7-136">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="822e7-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="822e7-137">CommonParameters</span></span>

<span data-ttu-id="822e7-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="822e7-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="822e7-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="822e7-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="822e7-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="822e7-140">INPUTS</span></span>

### <span data-ttu-id="822e7-141">None</span><span class="sxs-lookup"><span data-stu-id="822e7-141">None</span></span>

<span data-ttu-id="822e7-142">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="822e7-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="822e7-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="822e7-143">OUTPUTS</span></span>

### <span data-ttu-id="822e7-144">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="822e7-144">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="822e7-145">`Get-Event` Возвращает объект **PSEventArgs** для каждого события.</span><span class="sxs-lookup"><span data-stu-id="822e7-145">`Get-Event` returns a **PSEventArgs** object for each event.</span></span> <span data-ttu-id="822e7-146">Чтобы просмотреть описание этого объекта, введите `Get-Help Get-Event -Full` и просмотрите раздел "Примечания" в разделе справки.</span><span class="sxs-lookup"><span data-stu-id="822e7-146">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="822e7-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="822e7-147">NOTES</span></span>

<span data-ttu-id="822e7-148">На платформах Linux и macOS нет доступных источников событий.</span><span class="sxs-lookup"><span data-stu-id="822e7-148">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="822e7-149">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="822e7-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="822e7-150">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="822e7-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="822e7-151">`Get-Event`Командлет возвращает объект **PSEventArgs** (**System. Management. Automation. PSEventArgs**) со следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="822e7-151">The `Get-Event` cmdlet returns a **PSEventArgs** object (**System.Management.Automation.PSEventArgs**) with the following properties:</span></span>

- <span data-ttu-id="822e7-152">ComputerName.</span><span class="sxs-lookup"><span data-stu-id="822e7-152">ComputerName.</span></span> <span data-ttu-id="822e7-153">имя компьютера, на котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="822e7-153">The name of the computer on which the event occurred.</span></span> <span data-ttu-id="822e7-154">Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="822e7-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="822e7-155">Рунспацеид.</span><span class="sxs-lookup"><span data-stu-id="822e7-155">RunspaceId.</span></span> <span data-ttu-id="822e7-156">GUID, однозначно идентифицирующий сеанс, в ходе которого произошло событие.</span><span class="sxs-lookup"><span data-stu-id="822e7-156">A GUID that uniquely identifies the session in which the event occurred.</span></span> <span data-ttu-id="822e7-157">Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="822e7-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="822e7-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="822e7-158">EventIdentifier.</span></span> <span data-ttu-id="822e7-159">целое число (Int32), однозначно идентифицирующее уведомление о событии в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="822e7-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

- <span data-ttu-id="822e7-160">Отправителя.</span><span class="sxs-lookup"><span data-stu-id="822e7-160">Sender.</span></span> <span data-ttu-id="822e7-161">объект, создавший событие.</span><span class="sxs-lookup"><span data-stu-id="822e7-161">The object that generated the event.</span></span> <span data-ttu-id="822e7-162">В значении параметра **Action** `$Sender` Автоматическая переменная содержит объект sender.</span><span class="sxs-lookup"><span data-stu-id="822e7-162">In the value of the **Action** parameter, the `$Sender` automatic variable contains the sender object.</span></span>

- <span data-ttu-id="822e7-163">Саурцеевентаргс.</span><span class="sxs-lookup"><span data-stu-id="822e7-163">SourceEventArgs.</span></span> <span data-ttu-id="822e7-164">первый параметр, который наследуется от EventArgs (если существует).</span><span class="sxs-lookup"><span data-stu-id="822e7-164">The first parameter that derives from EventArgs, if it exists.</span></span> <span data-ttu-id="822e7-165">Например, в событии с истекшим таймером, в котором сигнатура имеет форму отправитель объекта, **Timers. ElapsedEventArgs** e, свойство **Саурцеевентаргс** будет содержать **таймеры. ElapsedEventArgs**.</span><span class="sxs-lookup"><span data-stu-id="822e7-165">For example, in a timer elapsed event in which the signature has the form Object sender, **Timers.ElapsedEventArgs** e, the **SourceEventArgs** property would contain the **Timers.ElapsedEventArgs**.</span></span> <span data-ttu-id="822e7-166">В значении параметра **Action** `$EventArgs` Автоматическая переменная содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="822e7-166">In the value of the **Action** parameter, the `$EventArgs` automatic variable contains this value.</span></span>

- <span data-ttu-id="822e7-167">Саурцеаргс.</span><span class="sxs-lookup"><span data-stu-id="822e7-167">SourceArgs.</span></span> <span data-ttu-id="822e7-168">все параметры сигнатуры исходного события.</span><span class="sxs-lookup"><span data-stu-id="822e7-168">All parameters of the original event signature.</span></span> <span data-ttu-id="822e7-169">Для стандартной сигнатуры события `$Args[0]` представляет отправителя и `$Args[1]` представляет **саурцеевентаргс**.</span><span class="sxs-lookup"><span data-stu-id="822e7-169">For a standard event signature, `$Args[0]` represents the sender, and `$Args[1]` represents the **SourceEventArgs**.</span></span> <span data-ttu-id="822e7-170">В значении параметра **Action** `$Args` Автоматическая переменная содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="822e7-170">In the value of the **Action** parameter, the `$Args` automatic variable contains this value.</span></span>

- <span data-ttu-id="822e7-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="822e7-171">SourceIdentifier.</span></span> <span data-ttu-id="822e7-172">cтрока, идентифицирующая подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="822e7-172">A string that identifies the event subscription.</span></span> <span data-ttu-id="822e7-173">В значении параметра **Action** свойство **SourceIdentifier** `$Event` автоматически изменяемой переменной содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="822e7-173">In the value of the **Action** parameter, the **SourceIdentifier** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="822e7-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="822e7-174">TimeGenerated.</span></span> <span data-ttu-id="822e7-175">Объект **DateTime** , представляющий время создания события.</span><span class="sxs-lookup"><span data-stu-id="822e7-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
  <span data-ttu-id="822e7-176">В значении параметра **Action** свойство **timegenerated** `$Event` автоматически изменяемой переменной содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="822e7-176">In the value of the **Action** parameter, the **TimeGenerated** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="822e7-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="822e7-177">MessageData.</span></span> <span data-ttu-id="822e7-178">данные, связанные с подпиской на событие.</span><span class="sxs-lookup"><span data-stu-id="822e7-178">Data associated with the event subscription.</span></span> <span data-ttu-id="822e7-179">Пользователи указывают эти данные при регистрации события.</span><span class="sxs-lookup"><span data-stu-id="822e7-179">Users specify this data when they register an event.</span></span> <span data-ttu-id="822e7-180">В значении параметра **Action** свойство **MessageData** `$Event` автоматически изменяемой переменной содержит это значение.</span><span class="sxs-lookup"><span data-stu-id="822e7-180">In the value of the **Action** parameter, the **MessageData** property of the `$Event` automatic variable contains this value.</span></span>

## <span data-ttu-id="822e7-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="822e7-181">RELATED LINKS</span></span>

[<span data-ttu-id="822e7-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="822e7-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="822e7-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="822e7-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="822e7-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="822e7-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="822e7-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="822e7-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="822e7-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="822e7-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="822e7-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="822e7-187">Wait-Event</span></span>](Wait-Event.md)
