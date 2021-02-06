---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 3193de9020f2f54795bde9d5cce1bb86c4431ef9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602082"
---
# <span data-ttu-id="12c8f-102">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-102">Remove-Event</span></span>

## <span data-ttu-id="12c8f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12c8f-103">SYNOPSIS</span></span>
<span data-ttu-id="12c8f-104">Удаляет события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="12c8f-104">Deletes events from the event queue.</span></span>

## <span data-ttu-id="12c8f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12c8f-105">SYNTAX</span></span>

### <span data-ttu-id="12c8f-106">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="12c8f-106">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12c8f-107">бидентифиер</span><span class="sxs-lookup"><span data-stu-id="12c8f-107">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="12c8f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12c8f-108">DESCRIPTION</span></span>

<span data-ttu-id="12c8f-109">`Remove-Event`Командлет удаляет события из очереди событий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="12c8f-109">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="12c8f-110">Этот командлет удаляет только те события, которые в данный момент находятся в очереди.</span><span class="sxs-lookup"><span data-stu-id="12c8f-110">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="12c8f-111">Чтобы отменить регистрацию событий или отказаться от подписки, используйте `Unregister-Event` командлет.</span><span class="sxs-lookup"><span data-stu-id="12c8f-111">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="12c8f-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="12c8f-112">EXAMPLES</span></span>

### <span data-ttu-id="12c8f-113">Пример 1. Удаление события по идентификатору источника</span><span class="sxs-lookup"><span data-stu-id="12c8f-113">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="12c8f-114">Эта команда удаляет события с идентификатором источника процесса, запущенным из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="12c8f-114">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="12c8f-115">Пример 2. Удаление события по идентификатору события</span><span class="sxs-lookup"><span data-stu-id="12c8f-115">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="12c8f-116">Эта команда удаляет из очереди событий событие с идентификатором 30.</span><span class="sxs-lookup"><span data-stu-id="12c8f-116">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="12c8f-117">Пример 3. Удаление всех событий</span><span class="sxs-lookup"><span data-stu-id="12c8f-117">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="12c8f-118">Эта команда удаляет все события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="12c8f-118">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="12c8f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12c8f-119">PARAMETERS</span></span>

### <span data-ttu-id="12c8f-120">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="12c8f-120">-EventIdentifier</span></span>

<span data-ttu-id="12c8f-121">Указывает идентификатор события, для которого удаляется командлет.</span><span class="sxs-lookup"><span data-stu-id="12c8f-121">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="12c8f-122">В каждой команде требуется параметр **EventIdentifier** или **SourceIdentifier** .</span><span class="sxs-lookup"><span data-stu-id="12c8f-122">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12c8f-123">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="12c8f-123">-SourceIdentifier</span></span>

<span data-ttu-id="12c8f-124">Указывает идентификатор источника, из которого этот командлет удаляет события.</span><span class="sxs-lookup"><span data-stu-id="12c8f-124">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="12c8f-125">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="12c8f-125">Wildcards are not permitted.</span></span> <span data-ttu-id="12c8f-126">В каждой команде требуется параметр **EventIdentifier** или **SourceIdentifier** .</span><span class="sxs-lookup"><span data-stu-id="12c8f-126">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12c8f-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12c8f-127">-Confirm</span></span>

<span data-ttu-id="12c8f-128">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="12c8f-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12c8f-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12c8f-129">-WhatIf</span></span>

<span data-ttu-id="12c8f-130">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="12c8f-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="12c8f-131">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="12c8f-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="12c8f-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="12c8f-132">CommonParameters</span></span>

<span data-ttu-id="12c8f-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12c8f-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12c8f-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12c8f-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12c8f-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="12c8f-135">INPUTS</span></span>

### <span data-ttu-id="12c8f-136">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="12c8f-136">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="12c8f-137">Можно передать события из `Get-Event` в `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="12c8f-137">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="12c8f-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="12c8f-138">OUTPUTS</span></span>

### <span data-ttu-id="12c8f-139">None</span><span class="sxs-lookup"><span data-stu-id="12c8f-139">None</span></span>

<span data-ttu-id="12c8f-140">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="12c8f-140">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="12c8f-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="12c8f-141">NOTES</span></span>

<span data-ttu-id="12c8f-142">На платформах Linux и macOS нет доступных источников событий.</span><span class="sxs-lookup"><span data-stu-id="12c8f-142">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="12c8f-143">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="12c8f-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="12c8f-144">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="12c8f-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="12c8f-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="12c8f-145">RELATED LINKS</span></span>

[<span data-ttu-id="12c8f-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="12c8f-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="12c8f-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="12c8f-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="12c8f-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="12c8f-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="12c8f-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="12c8f-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="12c8f-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="12c8f-152">Wait-Event</span></span>](Wait-Event.md)
