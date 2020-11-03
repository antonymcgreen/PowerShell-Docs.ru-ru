---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: 8f36d2af0fe03685e44070a0b0db86b8a276c4ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228998"
---
# <span data-ttu-id="0ba03-103">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="0ba03-103">Get-EventSubscriber</span></span>

## <span data-ttu-id="0ba03-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0ba03-104">SYNOPSIS</span></span>
<span data-ttu-id="0ba03-105">Получает подписчики на событие в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0ba03-105">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="0ba03-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ba03-106">SYNTAX</span></span>

### <span data-ttu-id="0ba03-107">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0ba03-107">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="0ba03-108">Метод byid</span><span class="sxs-lookup"><span data-stu-id="0ba03-108">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="0ba03-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ba03-109">DESCRIPTION</span></span>

<span data-ttu-id="0ba03-110">Командлет **Get-EventSubscriber** получает подписчики на события в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0ba03-110">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="0ba03-111">При оформлении подписки на событие с помощью командлета регистрации событий в сеанс PowerShell добавляется подписчик событий, а события, на которые вы подписаны, добавляются в очередь событий каждый раз, когда они возникают.</span><span class="sxs-lookup"><span data-stu-id="0ba03-111">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="0ba03-112">Чтобы отменить подписку на событие, необходимо удалить подписчик с помощью командлета Unregister-Event.</span><span class="sxs-lookup"><span data-stu-id="0ba03-112">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="0ba03-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="0ba03-113">EXAMPLES</span></span>

### <span data-ttu-id="0ba03-114">Пример 1. получение подписчика на событие для события таймера</span><span class="sxs-lookup"><span data-stu-id="0ba03-114">Example 1: Get the event subscriber for a timer event</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

<span data-ttu-id="0ba03-115">В этом примере для получения подписчика на событие таймера используется команда **Get-EventSubscriber** .</span><span class="sxs-lookup"><span data-stu-id="0ba03-115">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="0ba03-116">Первая команда создает экземпляр объекта таймера с помощью командлета New-Object.</span><span class="sxs-lookup"><span data-stu-id="0ba03-116">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="0ba03-117">Новый объект Timer сохраняется в переменной $Timer.</span><span class="sxs-lookup"><span data-stu-id="0ba03-117">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="0ba03-118">Вторая команда отображает события, доступные для объектов таймера, с помощью командлета Get-Member.</span><span class="sxs-lookup"><span data-stu-id="0ba03-118">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="0ba03-119">Команда использует параметр типа командлета **Get-Member** со значением Event.</span><span class="sxs-lookup"><span data-stu-id="0ba03-119">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="0ba03-120">Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.</span><span class="sxs-lookup"><span data-stu-id="0ba03-120">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="0ba03-121">Четвертая команда использует командлет **Get-EventSubscriber** , чтобы получить подписчика на событие для события Elapsed.</span><span class="sxs-lookup"><span data-stu-id="0ba03-121">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="0ba03-122">Пример 2. Использование динамического модуля в PSEventJob в свойстве Action подписчика событий</span><span class="sxs-lookup"><span data-stu-id="0ba03-122">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

<span data-ttu-id="0ba03-123">В этом примере показано, как использовать динамический модуль в объекте **PSEventJob** в свойстве Action подписчика событий.</span><span class="sxs-lookup"><span data-stu-id="0ba03-123">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="0ba03-124">Первая команда создает объект таймера с помощью командлета New-Object.</span><span class="sxs-lookup"><span data-stu-id="0ba03-124">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="0ba03-125">Вторая команда устанавливает интервал времени таймера равным 500 (миллисекундам).</span><span class="sxs-lookup"><span data-stu-id="0ba03-125">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="0ba03-126">Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.</span><span class="sxs-lookup"><span data-stu-id="0ba03-126">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="0ba03-127">Она содержит действие, обрабатывающее событие.</span><span class="sxs-lookup"><span data-stu-id="0ba03-127">The command includes an action that handles the event.</span></span>
<span data-ttu-id="0ba03-128">Когда интервал времени таймера истекает, появляется событие и выполняются команды, содержащиеся в действии.</span><span class="sxs-lookup"><span data-stu-id="0ba03-128">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="0ba03-129">В этом случае командлет Get-Random создает случайное число от 0 до 100 и сохраняет его в переменной $Random.</span><span class="sxs-lookup"><span data-stu-id="0ba03-129">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="0ba03-130">Идентификатор источника события — Timer.Random.</span><span class="sxs-lookup"><span data-stu-id="0ba03-130">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="0ba03-131">При использовании параметра *Action* в команде **Register-ObjectEvent** команда возвращает объект **PSEventJob** , представляющий действие.</span><span class="sxs-lookup"><span data-stu-id="0ba03-131">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="0ba03-132">Четвертая команда включает таймер.</span><span class="sxs-lookup"><span data-stu-id="0ba03-132">The fourth command enables the timer.</span></span>

<span data-ttu-id="0ba03-133">Пятая команда использует командлет **Get-EventSubscriber** для получения подписчика на событие Timer. Random.</span><span class="sxs-lookup"><span data-stu-id="0ba03-133">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="0ba03-134">Объект подписчика событий сохраняется в переменной $Subscriber.</span><span class="sxs-lookup"><span data-stu-id="0ba03-134">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="0ba03-135">Шестая команда показывает, что свойство Action объекта подписчика событий содержит объект **PSEventJob** .</span><span class="sxs-lookup"><span data-stu-id="0ba03-135">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="0ba03-136">Фактически он содержит тот же объект **PSEventJob** , который возвращает команда **Register-ObjectEvent** .</span><span class="sxs-lookup"><span data-stu-id="0ba03-136">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="0ba03-137">Седьмая команда использует командлет Format-List для вывода всех свойств объекта **PSEventJob** в свойстве Action в списке.</span><span class="sxs-lookup"><span data-stu-id="0ba03-137">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="0ba03-138">Результат показывает, что объект **PSEventJob** имеет свойство Module, которое содержит динамический модуль скрипта, реализующий действие.</span><span class="sxs-lookup"><span data-stu-id="0ba03-138">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="0ba03-139">Остальные команды используют оператор Call (&) для вызова команды в модуле и вывода значения переменной $Random.</span><span class="sxs-lookup"><span data-stu-id="0ba03-139">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="0ba03-140">Оператор вызова можно использовать для вызова любой команды в модуле, включая команды, которые не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="0ba03-140">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="0ba03-141">В этом случае команды показывают случайное число, создаваемое при появлении события Elapsed.</span><span class="sxs-lookup"><span data-stu-id="0ba03-141">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="0ba03-142">Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="0ba03-142">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="0ba03-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ba03-143">PARAMETERS</span></span>

### <span data-ttu-id="0ba03-144">-Force</span><span class="sxs-lookup"><span data-stu-id="0ba03-144">-Force</span></span>

<span data-ttu-id="0ba03-145">Указывает, что этот командлет получает все подписчики на события, включая подписчики для событий, которые скрыты с помощью параметра *SupportEvent* Register-ObjectEvent, Register-WmiEvent и Register-EngineEvent.</span><span class="sxs-lookup"><span data-stu-id="0ba03-145">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ba03-146">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="0ba03-146">-SourceIdentifier</span></span>

<span data-ttu-id="0ba03-147">Указывает значение свойства **SourceIdentifier** , которое получает только подписчики на события.</span><span class="sxs-lookup"><span data-stu-id="0ba03-147">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="0ba03-148">По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.</span><span class="sxs-lookup"><span data-stu-id="0ba03-148">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="0ba03-149">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="0ba03-149">Wildcards are not permitted.</span></span>
<span data-ttu-id="0ba03-150">Этот параметр чувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="0ba03-150">This parameter is case-sensitive.</span></span>

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

### <span data-ttu-id="0ba03-151">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="0ba03-151">-SubscriptionId</span></span>

<span data-ttu-id="0ba03-152">Указывает идентификатор подписки, который получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="0ba03-152">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="0ba03-153">По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.</span><span class="sxs-lookup"><span data-stu-id="0ba03-153">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

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

### <span data-ttu-id="0ba03-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0ba03-154">CommonParameters</span></span>

<span data-ttu-id="0ba03-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ba03-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ba03-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ba03-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ba03-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0ba03-157">INPUTS</span></span>

### <span data-ttu-id="0ba03-158">Нет</span><span class="sxs-lookup"><span data-stu-id="0ba03-158">None</span></span>

<span data-ttu-id="0ba03-159">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="0ba03-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0ba03-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0ba03-160">OUTPUTS</span></span>

### <span data-ttu-id="0ba03-161">System. Management. Automation. Псевентсубскрибер</span><span class="sxs-lookup"><span data-stu-id="0ba03-161">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="0ba03-162">Командлет **Get-EventSubscriber** возвращает объект, представляющий каждого подписчика на события.</span><span class="sxs-lookup"><span data-stu-id="0ba03-162">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="0ba03-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0ba03-163">NOTES</span></span>

* <span data-ttu-id="0ba03-164">Командлет New-Event, создающий пользовательское событие, не создает подписчик.</span><span class="sxs-lookup"><span data-stu-id="0ba03-164">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="0ba03-165">Поэтому командлет **Get-EventSubscriber** не обнаружит объект подписчика для этих событий.</span><span class="sxs-lookup"><span data-stu-id="0ba03-165">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="0ba03-166">Однако, если вы используете командлет Register-EngineEvent для подписки на пользовательское событие (чтобы перенаправить событие или указать действие), **Get-EventSubscriber** обнаружит подписчика, который вызывает **Register-EngineEvent** .</span><span class="sxs-lookup"><span data-stu-id="0ba03-166">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="0ba03-167">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0ba03-167">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="0ba03-168">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="0ba03-168">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="0ba03-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0ba03-169">RELATED LINKS</span></span>

[<span data-ttu-id="0ba03-170">Get-Event</span><span class="sxs-lookup"><span data-stu-id="0ba03-170">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="0ba03-171">New-Event</span><span class="sxs-lookup"><span data-stu-id="0ba03-171">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="0ba03-172">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="0ba03-172">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="0ba03-173">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="0ba03-173">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="0ba03-174">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0ba03-174">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="0ba03-175">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="0ba03-175">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="0ba03-176">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="0ba03-176">Wait-Event</span></span>](Wait-Event.md)
