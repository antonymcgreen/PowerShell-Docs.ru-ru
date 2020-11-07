---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 7aff17c29c8105c79d9bb3955552c75a3a05f752
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344730"
---
# <span data-ttu-id="4e24c-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-103">Unregister-Event</span></span>

## <span data-ttu-id="4e24c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4e24c-104">SYNOPSIS</span></span>
<span data-ttu-id="4e24c-105">Отменяет подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="4e24c-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="4e24c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e24c-106">SYNTAX</span></span>

### <span data-ttu-id="4e24c-107">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4e24c-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4e24c-108">Метод byid</span><span class="sxs-lookup"><span data-stu-id="4e24c-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4e24c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4e24c-109">DESCRIPTION</span></span>

<span data-ttu-id="4e24c-110">`Unregister-Event`Командлет отменяет подписку на событие, созданную с помощью `Register-EngineEvent` `Register-ObjectEvent` `Register-WmiEvent` командлета, или.</span><span class="sxs-lookup"><span data-stu-id="4e24c-110">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="4e24c-111">При отмене подписки на событие подписчик удаляется из сеанса, а события, на которые была оформлена подписка, больше не добавляются в очередь событий.</span><span class="sxs-lookup"><span data-stu-id="4e24c-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="4e24c-112">При отмене подписки на событие, созданное с помощью `New-Event` командлета, новое событие также удаляется из сеанса.</span><span class="sxs-lookup"><span data-stu-id="4e24c-112">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="4e24c-113">`Unregister-Event` не удаляет события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="4e24c-113">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="4e24c-114">Чтобы удалить события, используйте `Remove-Event` командлет.</span><span class="sxs-lookup"><span data-stu-id="4e24c-114">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="4e24c-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4e24c-115">EXAMPLES</span></span>

### <span data-ttu-id="4e24c-116">Пример 1. Отмена подписки на событие по идентификатору источника</span><span class="sxs-lookup"><span data-stu-id="4e24c-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="4e24c-117">Эта команда отменяет подписку на событие, имеющую идентификатор источника ProcessStarted.</span><span class="sxs-lookup"><span data-stu-id="4e24c-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="4e24c-118">Чтобы найти идентификатор источника события, используйте `Get-Event` командлет.</span><span class="sxs-lookup"><span data-stu-id="4e24c-118">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="4e24c-119">Чтобы найти идентификатор источника подписки на события, используйте `Get-EventSubscriber` командлет.</span><span class="sxs-lookup"><span data-stu-id="4e24c-119">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="4e24c-120">Пример 2. Отмена подписки на событие по идентификатору подписки</span><span class="sxs-lookup"><span data-stu-id="4e24c-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="4e24c-121">Эта команда отменяет подписку на событие с идентификатором подписки 2.</span><span class="sxs-lookup"><span data-stu-id="4e24c-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="4e24c-122">Чтобы найти идентификатор подписки подписки на события, используйте `Get-EventSubscriber` командлет.</span><span class="sxs-lookup"><span data-stu-id="4e24c-122">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="4e24c-123">Пример 3. Отмена всех подписок на события</span><span class="sxs-lookup"><span data-stu-id="4e24c-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="4e24c-124">Эта команда отменяет все подписки на события в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="4e24c-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="4e24c-125">Команда использует `Get-EventSubscriber` командлет для получения всех объектов подписчиков событий в сеансе, включая подписчики, скрытые с помощью параметра **SupportEvent** командлетов регистрации событий.</span><span class="sxs-lookup"><span data-stu-id="4e24c-125">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="4e24c-126">Он использует оператор конвейера ( `|` ) для отправки объектов подписчика `Unregister-Event` , который удаляет их из сеанса.</span><span class="sxs-lookup"><span data-stu-id="4e24c-126">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="4e24c-127">Для выполнения задачи параметр **Force** также требуется для `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="4e24c-127">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="4e24c-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e24c-128">PARAMETERS</span></span>

### <span data-ttu-id="4e24c-129">-Force</span><span class="sxs-lookup"><span data-stu-id="4e24c-129">-Force</span></span>

<span data-ttu-id="4e24c-130">Отменяет все подписки на события, включая подписки, которые были скрыты с помощью параметра **SupportEvent** `Register-ObjectEvent` , `Register-WmiEvent` и `Register-EngineEvent` .</span><span class="sxs-lookup"><span data-stu-id="4e24c-130">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="4e24c-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4e24c-131">-SourceIdentifier</span></span>

<span data-ttu-id="4e24c-132">Указывает идентификатор источника, который этот командлет отменяет подписки на события.</span><span class="sxs-lookup"><span data-stu-id="4e24c-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4e24c-133">Параметр **SourceIdentifier** или **SubscriptionId** должен включаться в каждую команду.</span><span class="sxs-lookup"><span data-stu-id="4e24c-133">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e24c-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="4e24c-134">-SubscriptionId</span></span>

<span data-ttu-id="4e24c-135">Указывает идентификатор исходного идентификатора, по которому этот командлет отменяет подписки на события.</span><span class="sxs-lookup"><span data-stu-id="4e24c-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4e24c-136">Параметр **SourceIdentifier** или **SubscriptionId** должен включаться в каждую команду.</span><span class="sxs-lookup"><span data-stu-id="4e24c-136">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e24c-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4e24c-137">-Confirm</span></span>

<span data-ttu-id="4e24c-138">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4e24c-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4e24c-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4e24c-139">-WhatIf</span></span>

<span data-ttu-id="4e24c-140">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4e24c-140">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4e24c-141">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4e24c-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4e24c-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4e24c-142">CommonParameters</span></span>

<span data-ttu-id="4e24c-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4e24c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4e24c-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4e24c-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4e24c-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4e24c-145">INPUTS</span></span>

### <span data-ttu-id="4e24c-146">System. Management. Automation. Псевентсубскрибер</span><span class="sxs-lookup"><span data-stu-id="4e24c-146">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="4e24c-147">Выходные данные можно передать в `Get-EventSubscriber` `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="4e24c-147">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="4e24c-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4e24c-148">OUTPUTS</span></span>

### <span data-ttu-id="4e24c-149">Нет</span><span class="sxs-lookup"><span data-stu-id="4e24c-149">None</span></span>

<span data-ttu-id="4e24c-150">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4e24c-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4e24c-151">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4e24c-151">NOTES</span></span>

<span data-ttu-id="4e24c-152">На платформах Linux и macOS нет доступных источников событий.</span><span class="sxs-lookup"><span data-stu-id="4e24c-152">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="4e24c-153">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4e24c-153">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4e24c-154">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="4e24c-154">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="4e24c-155">`Unregister-Event` невозможно удалить события, созданные с помощью `New-Event` командлета, если только вы не подписаны на событие с помощью `Register-EngineEvent` командлета.</span><span class="sxs-lookup"><span data-stu-id="4e24c-155">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="4e24c-156">Чтобы удалить из сеанса настраиваемое событие, используйте программный способ или закройте сеанс.</span><span class="sxs-lookup"><span data-stu-id="4e24c-156">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="4e24c-157">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4e24c-157">RELATED LINKS</span></span>

[<span data-ttu-id="4e24c-158">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-158">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4e24c-159">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="4e24c-159">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="4e24c-160">New-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-160">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4e24c-161">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4e24c-161">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4e24c-162">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4e24c-162">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4e24c-163">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-163">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4e24c-164">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-164">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4e24c-165">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4e24c-165">Wait-Event</span></span>](Wait-Event.md)
