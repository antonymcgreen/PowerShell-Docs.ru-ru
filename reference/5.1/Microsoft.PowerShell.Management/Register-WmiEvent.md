---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "93230189"
---
# <span data-ttu-id="5865f-103">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="5865f-103">Register-WmiEvent</span></span>

## <span data-ttu-id="5865f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5865f-104">SYNOPSIS</span></span>
<span data-ttu-id="5865f-105">Подписывается на событие WMI.</span><span class="sxs-lookup"><span data-stu-id="5865f-105">Subscribes to a Windows Management Instrumentation (WMI) event.</span></span>

## <span data-ttu-id="5865f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5865f-106">SYNTAX</span></span>

### <span data-ttu-id="5865f-107">Класс (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5865f-107">class (Default)</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="5865f-108">query</span><span class="sxs-lookup"><span data-stu-id="5865f-108">query</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="5865f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5865f-109">DESCRIPTION</span></span>

<span data-ttu-id="5865f-110">`Register-WmiEvent`Командлет подписывается на события инструментарий управления Windows (WMI) (WMI) на локальном компьютере или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5865f-110">The `Register-WmiEvent` cmdlet subscribes to Windows Management Instrumentation (WMI) events on the local computer or on a remote computer.</span></span>

<span data-ttu-id="5865f-111">При возникновении соответствующего события WMI оно добавляется в очередь событий в локальном сеансе, даже если событие инициировано на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5865f-111">When the subscribed WMI event is raised, it is added to the event queue in your local session even if the event occurs on a remote computer.</span></span> <span data-ttu-id="5865f-112">Чтобы получить события в очереди событий, используйте `Get-Event` командлет.</span><span class="sxs-lookup"><span data-stu-id="5865f-112">To get events in the event queue, use the `Get-Event` cmdlet.</span></span>

<span data-ttu-id="5865f-113">Параметры функции можно использовать `Register-WmiEvent` для подписки на события на удаленных компьютерах, а также для указания значений свойств событий, которые могут помочь определить событие в очереди.</span><span class="sxs-lookup"><span data-stu-id="5865f-113">You can use the parameters of `Register-WmiEvent` to subscribe to events on remote computers and to specify the property values of the events that can help you identify the event in the queue.</span></span> <span data-ttu-id="5865f-114">Можно также использовать параметр **Action** , чтобы указать действия, выполняемые при возникновении подписанного события.</span><span class="sxs-lookup"><span data-stu-id="5865f-114">You can also use the **Action** parameter to specify actions to take when a subscribed event is raised.</span></span>

<span data-ttu-id="5865f-115">При подписке на событие к текущему сеансу добавляется подписчик события.</span><span class="sxs-lookup"><span data-stu-id="5865f-115">When you subscribe to an event, an event subscriber is added to your session.</span></span> <span data-ttu-id="5865f-116">Чтобы получить подписчиков событий в сеансе, используйте `Get-EventSubscriber` командлет.</span><span class="sxs-lookup"><span data-stu-id="5865f-116">To get the event subscribers in the session, use the `Get-EventSubscriber` cmdlet.</span></span> <span data-ttu-id="5865f-117">Чтобы отменить подписку, используйте `Unregister-Event` командлет, который удаляет подписчика событий из сеанса.</span><span class="sxs-lookup"><span data-stu-id="5865f-117">To cancel the subscription, use the `Unregister-Event` cmdlet, which deletes the event subscriber from the session.</span></span>

<span data-ttu-id="5865f-118">В Windows PowerShell 3.0 появились новые командлеты модели CIM, выполняющие те же задачи, что и командлеты инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="5865f-118">New Common Information Model (CIM) cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="5865f-119">Командлеты модели CIM соответствуют стандартам WS-Management (WSMan) и CIM, что позволяет им использовать те же способы управления компьютерами под управлением Windows и других операционных систем.</span><span class="sxs-lookup"><span data-stu-id="5865f-119">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those that run other operating systems.</span></span> <span data-ttu-id="5865f-120">Вместо использования `Register-WmiEvent` , рассмотрите возможность использования командлета [Register-Циминдикатионевент](../cimcmdlets/register-cimindicationevent.md) .</span><span class="sxs-lookup"><span data-stu-id="5865f-120">Instead of using `Register-WmiEvent`, consider using the [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet.</span></span>

## <span data-ttu-id="5865f-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="5865f-121">EXAMPLES</span></span>

### <span data-ttu-id="5865f-122">Пример 1. Подписка на события, создаваемые с помощью класса</span><span class="sxs-lookup"><span data-stu-id="5865f-122">Example 1: Subscribe to events generated by a class</span></span>

<span data-ttu-id="5865f-123">Эта команда подписывается на события, создаваемые классом **Win32_ProcessStartTrace** .</span><span class="sxs-lookup"><span data-stu-id="5865f-123">This command subscribes to the events generated by the **Win32_ProcessStartTrace** class.</span></span> <span data-ttu-id="5865f-124">Этот класс вызывает событие при запуске процесса.</span><span class="sxs-lookup"><span data-stu-id="5865f-124">This class raises an event whenever a process starts.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="5865f-125">Пример 2. Подписка на события создания процесса</span><span class="sxs-lookup"><span data-stu-id="5865f-125">Example 2: Subscribe to creation events for a process</span></span>

<span data-ttu-id="5865f-126">Эта команда использует запрос для подписки на события создания экземпляра Win32_process.</span><span class="sxs-lookup"><span data-stu-id="5865f-126">This command uses a query to subscribe to Win32_process instance creation events.</span></span>

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### <span data-ttu-id="5865f-127">Пример 3. Использование действия в ответ на событие</span><span class="sxs-lookup"><span data-stu-id="5865f-127">Example 3: Use an action to respond to an event</span></span>

<span data-ttu-id="5865f-128">В этом примере показано, как использовать действие в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="5865f-128">This example shows how to use an action to respond to an event.</span></span> <span data-ttu-id="5865f-129">В этом случае при запуске процесса все `Start-Process` команды в текущем сеансе записываются в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="5865f-129">In this case, when a process starts, any `Start-Process` commands in the current session are written to an XML file.</span></span>

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

<span data-ttu-id="5865f-130">При использовании параметра **Action** `Register-WmiEvent` возвращает фоновое задание, представляющее действие события.</span><span class="sxs-lookup"><span data-stu-id="5865f-130">When you use the **Action** parameter, `Register-WmiEvent` returns a background job that represents the event action.</span></span> <span data-ttu-id="5865f-131">**Job** `Get-Job` `Receive-Job` Для управления заданием события можно использовать командлеты задания, такие как и.</span><span class="sxs-lookup"><span data-stu-id="5865f-131">You can use the **Job** cmdlets, such as `Get-Job` and `Receive-Job`, to manage the event job.</span></span>

<span data-ttu-id="5865f-132">Дополнительные сведения см. в разделе about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="5865f-132">For more information, see about_Jobs.</span></span>

### <span data-ttu-id="5865f-133">Пример 4. Регистрация для событий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="5865f-133">Example 4: Register for events on a remote computer</span></span>

<span data-ttu-id="5865f-134">Этот пример регистрируется для событий на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5865f-134">This example registers for events on the Server01 remote computer.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

<span data-ttu-id="5865f-135">WMI возвращает события на локальный компьютер и сохраняет их в очередь событий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5865f-135">WMI returns the events to the local computer and stores them in the event queue in the current session.</span></span> <span data-ttu-id="5865f-136">Чтобы получить события, выполните локальную `Get-Event` команду.</span><span class="sxs-lookup"><span data-stu-id="5865f-136">To retrieve the events, run a local `Get-Event` command.</span></span>

## <span data-ttu-id="5865f-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5865f-137">PARAMETERS</span></span>

### <span data-ttu-id="5865f-138">-Action</span><span class="sxs-lookup"><span data-stu-id="5865f-138">-Action</span></span>

<span data-ttu-id="5865f-139">Задает команды, которые обрабатывают события.</span><span class="sxs-lookup"><span data-stu-id="5865f-139">Specifies commands that handle the events.</span></span> <span data-ttu-id="5865f-140">Команды в параметре **Action** выполняются при возникновении события вместо отправки события в очередь событий.</span><span class="sxs-lookup"><span data-stu-id="5865f-140">The commands in the **Action** parameter run when an event is raised instead of sending the event to the event queue.</span></span> <span data-ttu-id="5865f-141">Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="5865f-141">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="5865f-142">Значение **Action** может включать `$Event` переменные,, `$EventSubscriber` `$Sender` , `$EventArgs` и `$Args` автоматически, которые предоставляют сведения о событии блоку сценария **действия** .</span><span class="sxs-lookup"><span data-stu-id="5865f-142">The value of **Action** can include the `$Event`, `$EventSubscriber`, `$Sender`, `$EventArgs`, and `$Args` automatic variables, which provide information about the event to the **Action** script block.</span></span> <span data-ttu-id="5865f-143">Дополнительные сведения см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="5865f-143">For more information, see about_Automatic_Variables.</span></span>

<span data-ttu-id="5865f-144">При указании действия `Register-WmiEvent` возвращает объект задания события, представляющий это действие.</span><span class="sxs-lookup"><span data-stu-id="5865f-144">When you specify an action, `Register-WmiEvent` returns an event job object that represents that action.</span></span> <span data-ttu-id="5865f-145">Для управления заданием события можно использовать командлеты, содержащие существительное **задания** (командлеты **задания** ).</span><span class="sxs-lookup"><span data-stu-id="5865f-145">You can use the cmdlets that contain the **Job** noun (the **Job** cmdlets) to manage the event job.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-146">-Class</span><span class="sxs-lookup"><span data-stu-id="5865f-146">-Class</span></span>

<span data-ttu-id="5865f-147">Указывает событие, на которое вы подписываетесь.</span><span class="sxs-lookup"><span data-stu-id="5865f-147">Specifies the event to which you are subscribing.</span></span> <span data-ttu-id="5865f-148">Введите класс WMI, который создает событие.</span><span class="sxs-lookup"><span data-stu-id="5865f-148">Enter the WMI class that generates the events.</span></span> <span data-ttu-id="5865f-149">В каждой команде требуется указать **класс** или параметр **запроса** .</span><span class="sxs-lookup"><span data-stu-id="5865f-149">A **Class** or **Query** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5865f-150">-ComputerName</span></span>

<span data-ttu-id="5865f-151">Задает имя компьютера, на котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="5865f-151">Specifies the name of the computer on which the command runs.</span></span> <span data-ttu-id="5865f-152">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="5865f-152">The default is the local computer.</span></span>

<span data-ttu-id="5865f-153">Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="5865f-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of the computer.</span></span> <span data-ttu-id="5865f-154">Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или localhost.</span><span class="sxs-lookup"><span data-stu-id="5865f-154">To specify the local computer, type the computer name, a dot (`.`), or localhost.</span></span>

<span data-ttu-id="5865f-155">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5865f-155">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="5865f-156">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="5865f-156">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="5865f-157">-Credential</span></span>

<span data-ttu-id="5865f-158">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="5865f-158">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="5865f-159">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="5865f-159">The default is the current user.</span></span>

<span data-ttu-id="5865f-160">Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="5865f-160">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="5865f-161">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="5865f-161">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-162">-Forward</span><span class="sxs-lookup"><span data-stu-id="5865f-162">-Forward</span></span>

<span data-ttu-id="5865f-163">Указывает, что этот командлет отправляет события по данной подписке в сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5865f-163">Indicates that this cmdlet sends events for this subscription to the session on the local computer.</span></span>
<span data-ttu-id="5865f-164">Этот параметр используется при регистрации событий, полученных на удаленном компьютере или в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5865f-164">Use this parameter when you are registering for events on a remote computer or in a remote session.</span></span>

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

### <span data-ttu-id="5865f-165">-MaxTriggerCount</span><span class="sxs-lookup"><span data-stu-id="5865f-165">-MaxTriggerCount</span></span>

<span data-ttu-id="5865f-166">Указывает максимальное число триггеров.</span><span class="sxs-lookup"><span data-stu-id="5865f-166">Specifies the maximum trigger count.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-167">-MessageData</span><span class="sxs-lookup"><span data-stu-id="5865f-167">-MessageData</span></span>

<span data-ttu-id="5865f-168">Указывает дополнительные данные, которые будут связаны с подпиской на событие.</span><span class="sxs-lookup"><span data-stu-id="5865f-168">Specifies any additional data to be associated with this event subscription.</span></span> <span data-ttu-id="5865f-169">Значение этого параметра отображается в свойстве **MessageData** всех событий, связанных с этой подпиской.</span><span class="sxs-lookup"><span data-stu-id="5865f-169">The value of this parameter appears in the **MessageData** property of all events associated with this subscription.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-170">-Namespace</span><span class="sxs-lookup"><span data-stu-id="5865f-170">-Namespace</span></span>

<span data-ttu-id="5865f-171">Задает пространство имен класса WMI.</span><span class="sxs-lookup"><span data-stu-id="5865f-171">Specifies the namespace of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-172">-Query</span><span class="sxs-lookup"><span data-stu-id="5865f-172">-Query</span></span>

<span data-ttu-id="5865f-173">Указывает запрос на языке запросов WMI, определяющий класс событий инструментария WMI, например `select * from __InstanceDeletionEvent`.</span><span class="sxs-lookup"><span data-stu-id="5865f-173">Specifies a query in WMI Query Language (WQL) that identifies the WMI event class, such as: `select * from __InstanceDeletionEvent`.</span></span>

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-174">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="5865f-174">-SourceIdentifier</span></span>

<span data-ttu-id="5865f-175">Указывает имя, выбранное для подписки.</span><span class="sxs-lookup"><span data-stu-id="5865f-175">Specifies a name that you select for the subscription.</span></span> <span data-ttu-id="5865f-176">Выбранное имя должно быть уникальным в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5865f-176">The name that you select must be unique in the current session.</span></span> <span data-ttu-id="5865f-177">Значение по умолчанию — идентификатор GUID, который назначает Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5865f-177">The default value is the GUID that Windows PowerShell assigns.</span></span>

<span data-ttu-id="5865f-178">Значение этого параметра отображается в значении свойства **SourceIdentifier** объекта подписчика, а также всех объектов событий, связанных с этой подпиской.</span><span class="sxs-lookup"><span data-stu-id="5865f-178">The value of this parameter appears in the value of the **SourceIdentifier** property of the subscriber object and of all event objects associated with this subscription.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-179">-SupportEvent</span><span class="sxs-lookup"><span data-stu-id="5865f-179">-SupportEvent</span></span>

<span data-ttu-id="5865f-180">Указывает, что этот командлет скрывает подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="5865f-180">Indicates that this cmdlet hides the event subscription.</span></span> <span data-ttu-id="5865f-181">Этот параметр используется, если текущая подписка является частью более сложного механизма регистрации событий и не должна обнаруживаться независимым образом.</span><span class="sxs-lookup"><span data-stu-id="5865f-181">Use this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered independently.</span></span>

<span data-ttu-id="5865f-182">Чтобы просмотреть или отменить подписку, созданную с помощью параметра **SupportEvent** , укажите параметр **Force** `Get-EventSubscriber` `Unregister-Event` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="5865f-182">To view or cancel a subscription that was created by using the **SupportEvent** parameter, specify the **Force** parameter of the `Get-EventSubscriber` and `Unregister-Event` cmdlets.</span></span>

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

### <span data-ttu-id="5865f-183">-Timeout</span><span class="sxs-lookup"><span data-stu-id="5865f-183">-Timeout</span></span>

<span data-ttu-id="5865f-184">Указывает время ожидания выполнения команды в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5865f-184">Specifies how long Windows PowerShell waits for this command to finish.</span></span>

<span data-ttu-id="5865f-185">Значение по умолчанию — 0 (ноль) означает, что времени ожидания нет, из-за чего Windows PowerShell ожидает команды бессрочно.</span><span class="sxs-lookup"><span data-stu-id="5865f-185">The default value, 0 (zero), means that there is no time-out, and it causes Windows PowerShell to wait indefinitely.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5865f-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5865f-186">CommonParameters</span></span>

<span data-ttu-id="5865f-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5865f-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5865f-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5865f-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5865f-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5865f-189">INPUTS</span></span>

### <span data-ttu-id="5865f-190">Нет</span><span class="sxs-lookup"><span data-stu-id="5865f-190">None</span></span>

<span data-ttu-id="5865f-191">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="5865f-191">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="5865f-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5865f-192">OUTPUTS</span></span>

### <span data-ttu-id="5865f-193">Нет</span><span class="sxs-lookup"><span data-stu-id="5865f-193">None</span></span>

<span data-ttu-id="5865f-194">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5865f-194">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5865f-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5865f-195">NOTES</span></span>

<span data-ttu-id="5865f-196">Чтобы использовать этот командлет в Windows Vista или более поздней версии ОС Windows, запустите Windows PowerShell, используя параметр "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="5865f-196">To use this cmdlet in Windows Vista or a later version of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="5865f-197">События, подписки на события и очередь событий существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5865f-197">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="5865f-198">Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.</span><span class="sxs-lookup"><span data-stu-id="5865f-198">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="5865f-199">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5865f-199">RELATED LINKS</span></span>
