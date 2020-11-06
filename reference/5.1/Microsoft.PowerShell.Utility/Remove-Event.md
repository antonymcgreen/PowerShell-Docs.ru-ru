---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 19841624e836f7cf8080487c977f11b88dd3174e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227541"
---
# <span data-ttu-id="35f62-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-103">Remove-Event</span></span>

## <span data-ttu-id="35f62-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="35f62-104">SYNOPSIS</span></span>
<span data-ttu-id="35f62-105">Удаляет события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="35f62-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="35f62-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35f62-106">SYNTAX</span></span>

### <span data-ttu-id="35f62-107">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="35f62-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="35f62-108">бидентифиер</span><span class="sxs-lookup"><span data-stu-id="35f62-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="35f62-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="35f62-109">DESCRIPTION</span></span>
<span data-ttu-id="35f62-110">Командлет **Remove-Event** удаляет события из очереди событий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35f62-110">The **Remove-Event** cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="35f62-111">Этот командлет удаляет только те события, которые в данный момент находятся в очереди.</span><span class="sxs-lookup"><span data-stu-id="35f62-111">This cmdlet deletes only the events currently in the queue.</span></span>
<span data-ttu-id="35f62-112">Для отмены регистрации событий или подписки воспользуйтесь командлетом Unregister-Event.</span><span class="sxs-lookup"><span data-stu-id="35f62-112">To cancel event registrations or unsubscribe, use the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="35f62-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="35f62-113">EXAMPLES</span></span>

### <span data-ttu-id="35f62-114">Пример 1. Удаление события по идентификатору источника</span><span class="sxs-lookup"><span data-stu-id="35f62-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="35f62-115">Эта команда удаляет события с идентификатором источника процесса, запущенным из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="35f62-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="35f62-116">Пример 2. Удаление события по идентификатору события</span><span class="sxs-lookup"><span data-stu-id="35f62-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="35f62-117">Эта команда удаляет из очереди событий событие с идентификатором 30.</span><span class="sxs-lookup"><span data-stu-id="35f62-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="35f62-118">Пример 3. Удаление всех событий</span><span class="sxs-lookup"><span data-stu-id="35f62-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="35f62-119">Эта команда удаляет все события из очереди событий.</span><span class="sxs-lookup"><span data-stu-id="35f62-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="35f62-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35f62-120">PARAMETERS</span></span>

### <span data-ttu-id="35f62-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="35f62-121">-EventIdentifier</span></span>
<span data-ttu-id="35f62-122">Указывает идентификатор события, для которого удаляется командлет.</span><span class="sxs-lookup"><span data-stu-id="35f62-122">Specifies the event identifier for which the cmdlet deletes.</span></span>
<span data-ttu-id="35f62-123">В каждой команде требуется параметр *EventIdentifier* или *SourceIdentifier* .</span><span class="sxs-lookup"><span data-stu-id="35f62-123">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

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

### <span data-ttu-id="35f62-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="35f62-124">-SourceIdentifier</span></span>
<span data-ttu-id="35f62-125">Указывает идентификатор источника, из которого этот командлет удаляет события.</span><span class="sxs-lookup"><span data-stu-id="35f62-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span>
<span data-ttu-id="35f62-126">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="35f62-126">Wildcards are not permitted.</span></span>
<span data-ttu-id="35f62-127">В каждой команде требуется параметр *EventIdentifier* или *SourceIdentifier* .</span><span class="sxs-lookup"><span data-stu-id="35f62-127">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

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

### <span data-ttu-id="35f62-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="35f62-128">-Confirm</span></span>
<span data-ttu-id="35f62-129">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="35f62-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="35f62-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="35f62-130">-WhatIf</span></span>
<span data-ttu-id="35f62-131">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="35f62-131">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="35f62-132">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="35f62-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="35f62-133">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="35f62-133">CommonParameters</span></span>
<span data-ttu-id="35f62-134">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="35f62-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35f62-135">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="35f62-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35f62-136">Входные данные</span><span class="sxs-lookup"><span data-stu-id="35f62-136">INPUTS</span></span>

### <span data-ttu-id="35f62-137">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="35f62-137">System.Management.Automation.PSEventArgs</span></span>
<span data-ttu-id="35f62-138">События можно передавать из Get-Event в **Remove-Event**.</span><span class="sxs-lookup"><span data-stu-id="35f62-138">You can pipe events from Get-Event to **Remove-Event**.</span></span>

## <span data-ttu-id="35f62-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="35f62-139">OUTPUTS</span></span>

### <span data-ttu-id="35f62-140">Нет</span><span class="sxs-lookup"><span data-stu-id="35f62-140">None</span></span>
<span data-ttu-id="35f62-141">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="35f62-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="35f62-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="35f62-142">NOTES</span></span>

* <span data-ttu-id="35f62-143">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35f62-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="35f62-144">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="35f62-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="35f62-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="35f62-145">RELATED LINKS</span></span>

[<span data-ttu-id="35f62-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="35f62-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="35f62-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="35f62-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="35f62-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="35f62-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="35f62-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="35f62-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="35f62-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="35f62-152">Wait-Event</span></span>](Wait-Event.md)