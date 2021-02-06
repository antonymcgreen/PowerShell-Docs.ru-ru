---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 86a4370caccb43edf62af75337afb15f3fb63d7c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600187"
---
# <span data-ttu-id="3ed6a-102">New-Event</span><span class="sxs-lookup"><span data-stu-id="3ed6a-102">New-Event</span></span>

## <span data-ttu-id="3ed6a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3ed6a-103">SYNOPSIS</span></span>
<span data-ttu-id="3ed6a-104">Создает новое событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-104">Creates a new event.</span></span>

## <span data-ttu-id="3ed6a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ed6a-105">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="3ed6a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ed6a-106">DESCRIPTION</span></span>

<span data-ttu-id="3ed6a-107">`New-Event`Командлет создает новое пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-107">The `New-Event` cmdlet creates a new custom event.</span></span>

<span data-ttu-id="3ed6a-108">Пользовательские события позволяют уведомлять пользователей об изменениях состояния программы, а также о любых других изменениях, которые может обнаружить программа, включая изменения условий работы оборудования или системы, состояния приложений, состояния диска, состояния сети или завершение фонового задания.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-108">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="3ed6a-109">Пользовательские события автоматически добавляются в очередь событий в сеансе в момент их возникновения; настраивать подписку на эти события не нужно.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-109">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span> <span data-ttu-id="3ed6a-110">Однако если вы хотите перенаправить событие в локальный сеанс или указать действие, отвечающее на событие, используйте `Register-EngineEvent` командлет для подписки на пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-110">However, if you want to forward an event to the local session or specify an action to respond to the event, use the `Register-EngineEvent` cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="3ed6a-111">При создании подписки на пользовательское событие в сеанс добавляется подписчик на событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-111">When you subscribe to a custom event, the event subscriber is added to your session.</span></span> <span data-ttu-id="3ed6a-112">Если вы отменяете подписку на событие с помощью `Unregister-Event` командлета, подписчик на событие и пользовательское событие удаляются из сеанса.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-112">If you cancel the event subscription by using the `Unregister-Event` cmdlet, the event subscriber and custom event are deleted from the session.</span></span> <span data-ttu-id="3ed6a-113">Если вы не подписаны на пользовательское событие, для удаления события необходимо изменить условия программы или закрыть сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-113">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="3ed6a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ed6a-114">EXAMPLES</span></span>

### <span data-ttu-id="3ed6a-115">Пример 1. Создание нового события в очереди событий</span><span class="sxs-lookup"><span data-stu-id="3ed6a-115">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="3ed6a-116">Эта команда создает новое событие в очереди событий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-116">This command creates a new event in the PowerShell event queue.</span></span> <span data-ttu-id="3ed6a-117">Для отправки события используется объект **Windows. Timer** .</span><span class="sxs-lookup"><span data-stu-id="3ed6a-117">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="3ed6a-118">Пример 2. вызов события в ответ на другое событие</span><span class="sxs-lookup"><span data-stu-id="3ed6a-118">Example 2: Raise an event in response to another event</span></span>

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

<span data-ttu-id="3ed6a-119">Этот пример функции использует `New-Event` командлет для вызова события в ответ на другое событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-119">This sample function uses the `New-Event` cmdlet to raise an event in response to another event.</span></span> <span data-ttu-id="3ed6a-120">Команда использует `Register-ObjectEvent` командлет для подписки на событие инструментарий управления Windows (WMI) (WMI), возникающее при создании нового процесса.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-120">The command uses the `Register-ObjectEvent` cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span> <span data-ttu-id="3ed6a-121">Команда использует параметр **Action** командлета для вызова `New-Event` командлета, который создает новое событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-121">The command uses the **Action** parameter of the cmdlet to call the `New-Event` cmdlet, which creates the new event.</span></span>

<span data-ttu-id="3ed6a-122">Так как события, которые `New-Event` вызываются, автоматически добавляются в очередь событий PowerShell, регистрация для этого события не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-122">Because the events that `New-Event` raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="3ed6a-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ed6a-123">PARAMETERS</span></span>

### <span data-ttu-id="3ed6a-124">-Евентаргументс</span><span class="sxs-lookup"><span data-stu-id="3ed6a-124">-EventArguments</span></span>

<span data-ttu-id="3ed6a-125">Указывает объект, содержащий параметры события.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-125">Specifies an object that contains options for the event.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ed6a-126">-MessageData</span><span class="sxs-lookup"><span data-stu-id="3ed6a-126">-MessageData</span></span>

<span data-ttu-id="3ed6a-127">Указывает дополнительные данные, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-127">Specifies additional data associated with the event.</span></span> <span data-ttu-id="3ed6a-128">Значение этого параметра отображается в свойстве **MessageData** объекта события.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-128">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ed6a-129">— Отправитель</span><span class="sxs-lookup"><span data-stu-id="3ed6a-129">-Sender</span></span>

<span data-ttu-id="3ed6a-130">Указывает объект, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-130">Specifies the object that raises the event.</span></span> <span data-ttu-id="3ed6a-131">По умолчанию используется подсистема PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-131">The default is the PowerShell engine.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ed6a-132">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="3ed6a-132">-SourceIdentifier</span></span>

<span data-ttu-id="3ed6a-133">Задает имя нового события.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-133">Specifies a name for the new event.</span></span> <span data-ttu-id="3ed6a-134">Этот параметр является обязательным и должен быть уникальным в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-134">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="3ed6a-135">Значение этого параметра отображается в свойстве **SourceIdentifier** событий.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-135">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ed6a-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3ed6a-136">CommonParameters</span></span>

<span data-ttu-id="3ed6a-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ed6a-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ed6a-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ed6a-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3ed6a-139">INPUTS</span></span>

### <span data-ttu-id="3ed6a-140">None</span><span class="sxs-lookup"><span data-stu-id="3ed6a-140">None</span></span>

<span data-ttu-id="3ed6a-141">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3ed6a-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3ed6a-142">OUTPUTS</span></span>

### <span data-ttu-id="3ed6a-143">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="3ed6a-143">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="3ed6a-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3ed6a-144">NOTES</span></span>

<span data-ttu-id="3ed6a-145">На платформах Linux и macOS нет доступных источников событий.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-145">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="3ed6a-146">Новое пользовательское событие, подписка на событие и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="3ed6a-147">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="3ed6a-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="3ed6a-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3ed6a-148">RELATED LINKS</span></span>

[<span data-ttu-id="3ed6a-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="3ed6a-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="3ed6a-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="3ed6a-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="3ed6a-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="3ed6a-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="3ed6a-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="3ed6a-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="3ed6a-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="3ed6a-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="3ed6a-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="3ed6a-154">Wait-Event</span></span>](Wait-Event.md)
