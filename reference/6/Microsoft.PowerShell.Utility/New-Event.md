---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 6056861bc6b472e389939e446d922d2bc4302294
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228950"
---
# <span data-ttu-id="b7f9b-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="b7f9b-103">New-Event</span></span>

## <span data-ttu-id="b7f9b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b7f9b-104">SYNOPSIS</span></span>
<span data-ttu-id="b7f9b-105">Создает новое событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-105">Creates a new event.</span></span>

## <span data-ttu-id="b7f9b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7f9b-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="b7f9b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b7f9b-107">DESCRIPTION</span></span>

<span data-ttu-id="b7f9b-108">Командлет **New-Event** создает новое пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-108">The **New-Event** cmdlet creates a new custom event.</span></span>

<span data-ttu-id="b7f9b-109">Пользовательские события позволяют уведомлять пользователей об изменениях состояния программы, а также о любых других изменениях, которые может обнаружить программа, включая изменения условий работы оборудования или системы, состояния приложений, состояния диска, состояния сети или завершение фонового задания.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="b7f9b-110">Пользовательские события автоматически добавляются в очередь событий в сеансе в момент их возникновения; настраивать подписку на эти события не нужно.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span>
<span data-ttu-id="b7f9b-111">Однако если требуется перенаправить событие в локальный сеанс или настроить реакцию на событие, необходимо подписаться на соответствующее пользовательское событие с помощью командлета Register-EngineEvent.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the Register-EngineEvent cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="b7f9b-112">При создании подписки на пользовательское событие в сеанс добавляется подписчик на событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span>
<span data-ttu-id="b7f9b-113">Если отменить подписку на событие с помощью командлета Unregister-Event, подписчик на событие и само пользовательское событие будут удалены из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-113">If you cancel the event subscription by using the Unregister-Event cmdlet, the event subscriber and custom event are deleted from the session.</span></span>
<span data-ttu-id="b7f9b-114">Если вы не подписаны на пользовательское событие, для удаления события необходимо изменить условия программы или закрыть сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="b7f9b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="b7f9b-115">EXAMPLES</span></span>

### <span data-ttu-id="b7f9b-116">Пример 1. Создание нового события в очереди событий</span><span class="sxs-lookup"><span data-stu-id="b7f9b-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="b7f9b-117">Эта команда создает новое событие в очереди событий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-117">This command creates a new event in the PowerShell event queue.</span></span>
<span data-ttu-id="b7f9b-118">Для отправки события используется объект **Windows. Timer** .</span><span class="sxs-lookup"><span data-stu-id="b7f9b-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="b7f9b-119">Пример 2. вызов события в ответ на другое событие</span><span class="sxs-lookup"><span data-stu-id="b7f9b-119">Example 2: Raise an event in response to another event</span></span>

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

<span data-ttu-id="b7f9b-120">Этот пример функции использует командлет **New-Event** для вызова события в ответ на другое событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-120">This sample function uses the **New-Event** cmdlet to raise an event in response to another event.</span></span>
<span data-ttu-id="b7f9b-121">С помощью командлета Register-ObjectEvent команда создает подписку на событие инструментария управления Windows (WMI), возникающее при создании нового процесса.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-121">The command uses the Register-ObjectEvent cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span>
<span data-ttu-id="b7f9b-122">Команда использует параметр *Action* командлета для вызова командлета **New-Event** , который создает новое событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-122">The command uses the *Action* parameter of the cmdlet to call the **New-Event** cmdlet, which creates the new event.</span></span>

<span data-ttu-id="b7f9b-123">Так как события, создаваемые **событием New** , автоматически добавляются в очередь событий PowerShell, регистрация для этого события не требуется.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-123">Because the events that **New-Event** raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="b7f9b-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7f9b-124">PARAMETERS</span></span>

### <span data-ttu-id="b7f9b-125">-Евентаргументс</span><span class="sxs-lookup"><span data-stu-id="b7f9b-125">-EventArguments</span></span>

<span data-ttu-id="b7f9b-126">Указывает объект, содержащий параметры события.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-126">Specifies an object that contains options for the event.</span></span>

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

### <span data-ttu-id="b7f9b-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="b7f9b-127">-MessageData</span></span>

<span data-ttu-id="b7f9b-128">Указывает дополнительные данные, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-128">Specifies additional data associated with the event.</span></span>
<span data-ttu-id="b7f9b-129">Значение этого параметра отображается в свойстве **MessageData** объекта события.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

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

### <span data-ttu-id="b7f9b-130">— Отправитель</span><span class="sxs-lookup"><span data-stu-id="b7f9b-130">-Sender</span></span>

<span data-ttu-id="b7f9b-131">Указывает объект, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-131">Specifies the object that raises the event.</span></span>
<span data-ttu-id="b7f9b-132">По умолчанию используется подсистема PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-132">The default is the PowerShell engine.</span></span>

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

### <span data-ttu-id="b7f9b-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="b7f9b-133">-SourceIdentifier</span></span>

<span data-ttu-id="b7f9b-134">Задает имя нового события.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-134">Specifies a name for the new event.</span></span>
<span data-ttu-id="b7f9b-135">Этот параметр является обязательным и должен быть уникальным в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="b7f9b-136">Значение этого параметра отображается в свойстве **SourceIdentifier** событий.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

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

### <span data-ttu-id="b7f9b-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b7f9b-137">CommonParameters</span></span>

<span data-ttu-id="b7f9b-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7f9b-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b7f9b-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b7f9b-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b7f9b-140">INPUTS</span></span>

### <span data-ttu-id="b7f9b-141">Нет</span><span class="sxs-lookup"><span data-stu-id="b7f9b-141">None</span></span>

<span data-ttu-id="b7f9b-142">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b7f9b-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b7f9b-143">OUTPUTS</span></span>

### <span data-ttu-id="b7f9b-144">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="b7f9b-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="b7f9b-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b7f9b-145">NOTES</span></span>

<span data-ttu-id="b7f9b-146">Новое пользовательское событие, подписка на событие и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span> <span data-ttu-id="b7f9b-147">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="b7f9b-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="b7f9b-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b7f9b-148">RELATED LINKS</span></span>

[<span data-ttu-id="b7f9b-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="b7f9b-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="b7f9b-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="b7f9b-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="b7f9b-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="b7f9b-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="b7f9b-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="b7f9b-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="b7f9b-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="b7f9b-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="b7f9b-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="b7f9b-154">Wait-Event</span></span>](Wait-Event.md)
