---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: fd617cd145c4f36ceede9898de93cbad33cb4bf3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225689"
---
# <span data-ttu-id="09804-103">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="09804-103">Wait-Event</span></span>

## <span data-ttu-id="09804-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="09804-104">SYNOPSIS</span></span>
<span data-ttu-id="09804-105">Ожидает определенное событие, прежде чем продолжить выполнение.</span><span class="sxs-lookup"><span data-stu-id="09804-105">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="09804-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09804-106">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="09804-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09804-107">DESCRIPTION</span></span>

<span data-ttu-id="09804-108">`Wait-Event`Командлет приостанавливает выполнение скрипта или функции до тех пор, пока не будет вызвано определенное событие.</span><span class="sxs-lookup"><span data-stu-id="09804-108">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="09804-109">Выполнение возобновляется после обнаружении события.</span><span class="sxs-lookup"><span data-stu-id="09804-109">Execution resumes when the event is detected.</span></span> <span data-ttu-id="09804-110">Чтобы отменить ожидание, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="09804-110">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="09804-111">Эта функция представляет альтернативу опросу события.</span><span class="sxs-lookup"><span data-stu-id="09804-111">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="09804-112">Он также позволяет определить ответ на событие двумя разными способами:</span><span class="sxs-lookup"><span data-stu-id="09804-112">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="09804-113">Использование параметра **Action** подписки на события</span><span class="sxs-lookup"><span data-stu-id="09804-113">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="09804-114">ожидание возврата события и ответ с действием</span><span class="sxs-lookup"><span data-stu-id="09804-114">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="09804-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="09804-115">EXAMPLES</span></span>

### <span data-ttu-id="09804-116">Пример 1. ожидание следующего события</span><span class="sxs-lookup"><span data-stu-id="09804-116">Example 1: Wait for the next event</span></span>

<span data-ttu-id="09804-117">В этом примере ожидает следующего вызванного события.</span><span class="sxs-lookup"><span data-stu-id="09804-117">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="09804-118">Пример 2. ожидание события с указанным идентификатором источника</span><span class="sxs-lookup"><span data-stu-id="09804-118">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="09804-119">Этот пример ожидает следующего вызванного события и имеет идентификатор источника ProcessStarted.</span><span class="sxs-lookup"><span data-stu-id="09804-119">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="09804-120">Пример 3. ожидание события Elapsed Timer</span><span class="sxs-lookup"><span data-stu-id="09804-120">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="09804-121">В этом примере используется `Wait-Event` командлет для ожидания события таймера в таймере, установленном в течение 2000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="09804-121">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### <span data-ttu-id="09804-122">Пример 4. ожидание события после указанного времени ожидания</span><span class="sxs-lookup"><span data-stu-id="09804-122">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="09804-123">В этом примере ожидается задержка до 90 секунд для следующего вызванного события и имеющего идентификатор источника **ProcessStarted**.</span><span class="sxs-lookup"><span data-stu-id="09804-123">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted**.</span></span> <span data-ttu-id="09804-124">Если указанное время истекает, ожидание завершается.</span><span class="sxs-lookup"><span data-stu-id="09804-124">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="09804-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09804-125">PARAMETERS</span></span>

### <span data-ttu-id="09804-126">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="09804-126">-SourceIdentifier</span></span>

<span data-ttu-id="09804-127">Указывает идентификатор источника, который этот командлет ожидает события.</span><span class="sxs-lookup"><span data-stu-id="09804-127">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="09804-128">По умолчанию `Wait-Event` ожидает любого события.</span><span class="sxs-lookup"><span data-stu-id="09804-128">By default, `Wait-Event` waits for any event.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="09804-129">-Timeout</span><span class="sxs-lookup"><span data-stu-id="09804-129">-Timeout</span></span>

<span data-ttu-id="09804-130">Указывает максимальное время в секундах, которое ожидает наступления `Wait-Event` события.</span><span class="sxs-lookup"><span data-stu-id="09804-130">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="09804-131">Значение по умолчанию, -1, обозначает неопределенное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="09804-131">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="09804-132">Время начинается с момента отправки `Wait-Event` команды.</span><span class="sxs-lookup"><span data-stu-id="09804-132">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="09804-133">Если указанное время ожидания превышено, ожидание прекращается и возвращается командная строка, даже если событие не возникло.</span><span class="sxs-lookup"><span data-stu-id="09804-133">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="09804-134">Сообщение об ошибке не отображается.</span><span class="sxs-lookup"><span data-stu-id="09804-134">No error message is displayed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="09804-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="09804-135">CommonParameters</span></span>

<span data-ttu-id="09804-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="09804-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09804-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="09804-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="09804-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="09804-138">INPUTS</span></span>

### <span data-ttu-id="09804-139">System.String</span><span class="sxs-lookup"><span data-stu-id="09804-139">System.String</span></span>

## <span data-ttu-id="09804-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="09804-140">OUTPUTS</span></span>

### <span data-ttu-id="09804-141">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="09804-141">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="09804-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="09804-142">NOTES</span></span>

<span data-ttu-id="09804-143">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="09804-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="09804-144">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="09804-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="09804-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="09804-145">RELATED LINKS</span></span>

[<span data-ttu-id="09804-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="09804-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="09804-147">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="09804-147">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="09804-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="09804-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="09804-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="09804-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="09804-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="09804-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="09804-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="09804-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="09804-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="09804-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="09804-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="09804-153">Wait-Event</span></span>](Wait-Event.md)
