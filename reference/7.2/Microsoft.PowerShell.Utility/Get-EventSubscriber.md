---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: b8f55770770fa9077f654d382818386cc480c638
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604583"
---
# <span data-ttu-id="68db0-102">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="68db0-102">Get-EventSubscriber</span></span>

## <span data-ttu-id="68db0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="68db0-103">SYNOPSIS</span></span>
<span data-ttu-id="68db0-104">Получает подписчики на событие в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="68db0-104">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="68db0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68db0-105">SYNTAX</span></span>

### <span data-ttu-id="68db0-106">Бисаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="68db0-106">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="68db0-107">Метод byid</span><span class="sxs-lookup"><span data-stu-id="68db0-107">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="68db0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68db0-108">DESCRIPTION</span></span>

<span data-ttu-id="68db0-109">Командлет **Get-EventSubscriber** получает подписчики на события в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="68db0-109">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="68db0-110">При оформлении подписки на событие с помощью командлета регистрации событий в сеанс PowerShell добавляется подписчик событий, а события, на которые вы подписаны, добавляются в очередь событий каждый раз, когда они возникают.</span><span class="sxs-lookup"><span data-stu-id="68db0-110">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="68db0-111">Чтобы отменить подписку на событие, необходимо удалить подписчик с помощью командлета Unregister-Event.</span><span class="sxs-lookup"><span data-stu-id="68db0-111">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="68db0-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="68db0-112">EXAMPLES</span></span>

### <span data-ttu-id="68db0-113">Пример 1. получение подписчика на событие для события таймера</span><span class="sxs-lookup"><span data-stu-id="68db0-113">Example 1: Get the event subscriber for a timer event</span></span>

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

<span data-ttu-id="68db0-114">В этом примере для получения подписчика на событие таймера используется команда **Get-EventSubscriber** .</span><span class="sxs-lookup"><span data-stu-id="68db0-114">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="68db0-115">Первая команда создает экземпляр объекта таймера с помощью командлета New-Object.</span><span class="sxs-lookup"><span data-stu-id="68db0-115">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="68db0-116">Новый объект Timer сохраняется в переменной $Timer.</span><span class="sxs-lookup"><span data-stu-id="68db0-116">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="68db0-117">Вторая команда отображает события, доступные для объектов таймера, с помощью командлета Get-Member.</span><span class="sxs-lookup"><span data-stu-id="68db0-117">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="68db0-118">Команда использует параметр типа командлета **Get-Member** со значением Event.</span><span class="sxs-lookup"><span data-stu-id="68db0-118">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="68db0-119">Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.</span><span class="sxs-lookup"><span data-stu-id="68db0-119">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="68db0-120">Четвертая команда использует командлет **Get-EventSubscriber** , чтобы получить подписчика на событие для события Elapsed.</span><span class="sxs-lookup"><span data-stu-id="68db0-120">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="68db0-121">Пример 2. Использование динамического модуля в PSEventJob в свойстве Action подписчика событий</span><span class="sxs-lookup"><span data-stu-id="68db0-121">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

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

<span data-ttu-id="68db0-122">В этом примере показано, как использовать динамический модуль в объекте **PSEventJob** в свойстве Action подписчика событий.</span><span class="sxs-lookup"><span data-stu-id="68db0-122">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="68db0-123">Первая команда создает объект таймера с помощью командлета New-Object.</span><span class="sxs-lookup"><span data-stu-id="68db0-123">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="68db0-124">Вторая команда устанавливает интервал времени таймера равным 500 (миллисекундам).</span><span class="sxs-lookup"><span data-stu-id="68db0-124">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="68db0-125">Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.</span><span class="sxs-lookup"><span data-stu-id="68db0-125">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="68db0-126">Она содержит действие, обрабатывающее событие.</span><span class="sxs-lookup"><span data-stu-id="68db0-126">The command includes an action that handles the event.</span></span>
<span data-ttu-id="68db0-127">Когда интервал времени таймера истекает, появляется событие и выполняются команды, содержащиеся в действии.</span><span class="sxs-lookup"><span data-stu-id="68db0-127">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="68db0-128">В этом случае командлет Get-Random создает случайное число от 0 до 100 и сохраняет его в переменной $Random.</span><span class="sxs-lookup"><span data-stu-id="68db0-128">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="68db0-129">Идентификатор источника события — Timer.Random.</span><span class="sxs-lookup"><span data-stu-id="68db0-129">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="68db0-130">При использовании параметра *Action* в команде **Register-ObjectEvent** команда возвращает объект **PSEventJob** , представляющий действие.</span><span class="sxs-lookup"><span data-stu-id="68db0-130">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="68db0-131">Четвертая команда включает таймер.</span><span class="sxs-lookup"><span data-stu-id="68db0-131">The fourth command enables the timer.</span></span>

<span data-ttu-id="68db0-132">Пятая команда использует командлет **Get-EventSubscriber** для получения подписчика на событие Timer. Random.</span><span class="sxs-lookup"><span data-stu-id="68db0-132">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="68db0-133">Объект подписчика событий сохраняется в переменной $Subscriber.</span><span class="sxs-lookup"><span data-stu-id="68db0-133">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="68db0-134">Шестая команда показывает, что свойство Action объекта подписчика событий содержит объект **PSEventJob** .</span><span class="sxs-lookup"><span data-stu-id="68db0-134">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="68db0-135">Фактически он содержит тот же объект **PSEventJob** , который возвращает команда **Register-ObjectEvent** .</span><span class="sxs-lookup"><span data-stu-id="68db0-135">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="68db0-136">Седьмая команда использует командлет Format-List для вывода всех свойств объекта **PSEventJob** в свойстве Action в списке.</span><span class="sxs-lookup"><span data-stu-id="68db0-136">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="68db0-137">Результат показывает, что объект **PSEventJob** имеет свойство Module, которое содержит динамический модуль скрипта, реализующий действие.</span><span class="sxs-lookup"><span data-stu-id="68db0-137">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="68db0-138">Остальные команды используют оператор Call (&) для вызова команды в модуле и вывода значения переменной $Random.</span><span class="sxs-lookup"><span data-stu-id="68db0-138">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="68db0-139">Оператор вызова можно использовать для вызова любой команды в модуле, включая команды, которые не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="68db0-139">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="68db0-140">В этом случае команды показывают случайное число, создаваемое при появлении события Elapsed.</span><span class="sxs-lookup"><span data-stu-id="68db0-140">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="68db0-141">Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="68db0-141">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="68db0-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68db0-142">PARAMETERS</span></span>

### <span data-ttu-id="68db0-143">-Force</span><span class="sxs-lookup"><span data-stu-id="68db0-143">-Force</span></span>

<span data-ttu-id="68db0-144">Указывает, что этот командлет получает все подписчики на события, включая подписчики для событий, которые скрыты с помощью параметра *SupportEvent* Register-ObjectEvent, Register-WmiEvent и Register-EngineEvent.</span><span class="sxs-lookup"><span data-stu-id="68db0-144">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

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

### <span data-ttu-id="68db0-145">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="68db0-145">-SourceIdentifier</span></span>

<span data-ttu-id="68db0-146">Указывает значение свойства **SourceIdentifier** , которое получает только подписчики на события.</span><span class="sxs-lookup"><span data-stu-id="68db0-146">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="68db0-147">По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.</span><span class="sxs-lookup"><span data-stu-id="68db0-147">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="68db0-148">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="68db0-148">Wildcards are not permitted.</span></span>
<span data-ttu-id="68db0-149">Этот параметр чувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="68db0-149">This parameter is case-sensitive.</span></span>

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

### <span data-ttu-id="68db0-150">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="68db0-150">-SubscriptionId</span></span>

<span data-ttu-id="68db0-151">Указывает идентификатор подписки, который получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="68db0-151">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="68db0-152">По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.</span><span class="sxs-lookup"><span data-stu-id="68db0-152">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

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

### <span data-ttu-id="68db0-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="68db0-153">CommonParameters</span></span>

<span data-ttu-id="68db0-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68db0-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68db0-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68db0-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68db0-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="68db0-156">INPUTS</span></span>

### <span data-ttu-id="68db0-157">None</span><span class="sxs-lookup"><span data-stu-id="68db0-157">None</span></span>

<span data-ttu-id="68db0-158">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="68db0-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="68db0-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="68db0-159">OUTPUTS</span></span>

### <span data-ttu-id="68db0-160">System. Management. Automation. Псевентсубскрибер</span><span class="sxs-lookup"><span data-stu-id="68db0-160">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="68db0-161">Командлет **Get-EventSubscriber** возвращает объект, представляющий каждого подписчика на события.</span><span class="sxs-lookup"><span data-stu-id="68db0-161">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="68db0-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="68db0-162">NOTES</span></span>

* <span data-ttu-id="68db0-163">Командлет New-Event, создающий пользовательское событие, не создает подписчик.</span><span class="sxs-lookup"><span data-stu-id="68db0-163">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="68db0-164">Поэтому командлет **Get-EventSubscriber** не обнаружит объект подписчика для этих событий.</span><span class="sxs-lookup"><span data-stu-id="68db0-164">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="68db0-165">Однако, если вы используете командлет Register-EngineEvent для подписки на пользовательское событие (чтобы перенаправить событие или указать действие), **Get-EventSubscriber** обнаружит подписчика, который вызывает **Register-EngineEvent** .</span><span class="sxs-lookup"><span data-stu-id="68db0-165">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="68db0-166">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="68db0-166">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="68db0-167">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="68db0-167">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="68db0-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="68db0-168">RELATED LINKS</span></span>

[<span data-ttu-id="68db0-169">Get-Event</span><span class="sxs-lookup"><span data-stu-id="68db0-169">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="68db0-170">New-Event</span><span class="sxs-lookup"><span data-stu-id="68db0-170">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="68db0-171">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="68db0-171">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="68db0-172">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="68db0-172">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="68db0-173">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="68db0-173">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="68db0-174">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="68db0-174">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="68db0-175">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="68db0-175">Wait-Event</span></span>](Wait-Event.md)

