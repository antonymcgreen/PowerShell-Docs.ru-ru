---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Управление службами
description: PowerShell предоставляет несколько командлетов, позволяющих управлять службами на локальном или удаленном компьютере.
ms.openlocfilehash: 003803cdaa37e51b3788f3f897cbec7d6e243ca8
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500357"
---
# <a name="managing-services"></a><span data-ttu-id="ff0d5-104">Управление службами</span><span class="sxs-lookup"><span data-stu-id="ff0d5-104">Managing Services</span></span>

<span data-ttu-id="ff0d5-105">Существует восемь основных командлетов Service, предназначенных для широкого спектра задач обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-105">There are eight core Service cmdlets, designed for a wide range of service tasks .</span></span> <span data-ttu-id="ff0d5-106">Мы рассмотрим только вывод списка служб и изменение состояния их выполнения, но вы можете получить весь список командлетов Service с помощью `Get-Help \*-Service`, а сведения о каждом из них можно просмотреть с помощью командлета`Get-Help <Cmdlet-Name>`, например`Get-Help New-Service`.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-106">We will look only at listing and changing running state for services, but you can get a list of Service cmdlets by using `Get-Help \*-Service`, and you can find information about each Service cmdlet by using `Get-Help <Cmdlet-Name>`, such as `Get-Help New-Service`.</span></span>

## <a name="getting-services"></a><span data-ttu-id="ff0d5-107">Получение служб</span><span class="sxs-lookup"><span data-stu-id="ff0d5-107">Getting Services</span></span>

<span data-ttu-id="ff0d5-108">Получить службы на локальном или удаленном компьютере можно с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-108">You can get the services on a local or remote computer by using the `Get-Service` cmdlet.</span></span> <span data-ttu-id="ff0d5-109">Как и в случае с `Get-Process`, использование команды `Get-Service` без параметров возвращает все службы.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-109">As with `Get-Process`, using the `Get-Service` command without parameters returns all services.</span></span> <span data-ttu-id="ff0d5-110">Можно фильтровать по имени, даже используя звездочку как подстановочный знак:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-110">You can filter by name, even using an asterisk as a wildcard:</span></span>

```powershell
PS> Get-Service -Name se*

Status   Name               DisplayName
------   ----               -----------
Running  seclogon           Secondary Logon
Running  SENS               System Event Notification
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="ff0d5-111">Так как реальное имя службы не всегда очевидно, может потребоваться найти службы по отображаемому имени.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-111">Because it is not always obvious what the real name for the service is, you may find you need to find services by display name.</span></span> <span data-ttu-id="ff0d5-112">Это можно сделать с использованием определенного имени, подстановочных знаков или списка отображаемых имен:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-112">You can do this by specific name, using wildcards, or using a list of display names:</span></span>

```powershell
PS> Get-Service -DisplayName se*

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Running  SamSs              Security Accounts Manager
Running  seclogon           Secondary Logon
Stopped  ServiceLayer       ServiceLayer
Running  wscsvc             Security Center

PS> Get-Service -DisplayName ServiceLayer,Server

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="ff0d5-113">Параметр ComputerName командлета Get-Service можно использовать для получения служб на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-113">You can use the ComputerName parameter of the Get-Service cmdlet to get the services on remote computers.</span></span> <span data-ttu-id="ff0d5-114">Параметр ComputerName принимает несколько значений и подстановочные знаки, что позволяет получить службы на нескольких компьютерах с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-114">The ComputerName parameter accepts multiple values and wildcard characters, so you can get the services on multiple computers with a single command.</span></span> <span data-ttu-id="ff0d5-115">Например, приведенная ниже команда получает службы на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-115">For example, the following command gets the services on the Server01 remote computer.</span></span>

```powershell
Get-Service -ComputerName Server01
```

## <a name="getting-required-and-dependent-services"></a><span data-ttu-id="ff0d5-116">Получение необходимых и зависимых служб</span><span class="sxs-lookup"><span data-stu-id="ff0d5-116">Getting Required and Dependent Services</span></span>

<span data-ttu-id="ff0d5-117">Командлет Get-Service имеет два параметра, которые удобно использовать при администрировании служб.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-117">The Get-Service cmdlet has two parameters that are very useful in service administration.</span></span> <span data-ttu-id="ff0d5-118">Параметр DependentServices получает службы, которые зависят от данной службы.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-118">The DependentServices parameter gets services that depend on the service.</span></span> <span data-ttu-id="ff0d5-119">Параметр RequiredServices получает службы, от которых зависит данная служба.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-119">The RequiredServices parameter gets services upon which this service depends.</span></span>

<span data-ttu-id="ff0d5-120">Эти параметры просто отображают значения свойств DependentServices и ServicesDependedOn (псевдоним RequiredServices) объекта System.ServiceProcess.ServiceController, возвращаемого Get-Service, но они упрощают работу с командами и получение этой информации.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-120">These parameters just display the values of the DependentServices and ServicesDependedOn (alias=RequiredServices) properties of the System.ServiceProcess.ServiceController object that Get-Service returns, but they simplify commands and make getting this information much simpler.</span></span>

<span data-ttu-id="ff0d5-121">Приведенная ниже команда получает службы, необходимые службе LanmanWorkstation.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-121">The following command gets the services that the LanmanWorkstation service requires.</span></span>

```powershell
PS> Get-Service -Name LanmanWorkstation -RequiredServices

Status   Name               DisplayName
------   ----               -----------
Running  MRxSmb20           SMB 2.0 MiniRedirector
Running  bowser             Bowser
Running  MRxSmb10           SMB 1.x MiniRedirector
Running  NSI                Network Store Interface Service
```

<span data-ttu-id="ff0d5-122">Приведенная ниже команда получает службы, которым требуется служба LanmanWorkstation.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-122">The following command gets the services that require the LanmanWorkstation service.</span></span>

```powershell
PS> Get-Service -Name LanmanWorkstation -DependentServices

Status   Name               DisplayName
------   ----               -----------
Running  SessionEnv         Terminal Services Configuration
Running  Netlogon           Netlogon
Stopped  Browser            Computer Browser
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="ff0d5-123">Вы даже можете получить все службы, имеющие зависимости.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-123">You can even get all services that have dependencies.</span></span> <span data-ttu-id="ff0d5-124">Следующая команда делает именно это, а затем она использует командлет Format-Table для отображения свойств Status, Name, RequiredServices и DependentServices для служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-124">The following command does just that, and then it uses the Format-Table cmdlet to display the Status, Name, RequiredServices and DependentServices properties of the services on the computer.</span></span>

```powershell
Get-Service -Name * | Where-Object {$_.RequiredServices -or $_.DependentServices} |
  Format-Table -Property Status, Name, RequiredServices, DependentServices -auto
```

## <a name="stopping-starting-suspending-and-restarting-services"></a><span data-ttu-id="ff0d5-125">Остановка, запуск, приостановка и перезапуск служб</span><span class="sxs-lookup"><span data-stu-id="ff0d5-125">Stopping, Starting, Suspending, and Restarting Services</span></span>

<span data-ttu-id="ff0d5-126">Все командлеты Service имеют схожую общую форму.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-126">The Service cmdlets all have the same general form.</span></span> <span data-ttu-id="ff0d5-127">Службы можно указать по общему имени или отображаемому имени, они также принимают списки и подстановочные знаки в качестве значений.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-127">Services can be specified by common name or display name, and take lists and wildcards as values.</span></span> <span data-ttu-id="ff0d5-128">Для остановки очереди печати принтера используйте:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-128">To stop the print spooler, use:</span></span>

```powershell
Stop-Service -Name spooler
```

<span data-ttu-id="ff0d5-129">Для запуска очереди печати принтера после ее остановки используйте:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-129">To start the print spooler after it is stopped, use:</span></span>

```powershell
Start-Service -Name spooler
```

<span data-ttu-id="ff0d5-130">Для приостановки очереди печати принтера используйте:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-130">To suspend the print spooler, use:</span></span>

```powershell
Suspend-Service -Name spooler
```

<span data-ttu-id="ff0d5-131">Командлет `Restart-Service` работает так же, как другие командлеты Service, но для него будет приведено несколько более сложных примеров.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-131">The `Restart-Service` cmdlet works in the same manner as the other Service cmdlets, but we will show some more complex examples for it.</span></span> <span data-ttu-id="ff0d5-132">В самом простом случае указывается имя службы:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-132">In the simplest use, you specify the name of the service:</span></span>

```powershell
PS> Restart-Service -Name spooler

WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
PS>
```

<span data-ttu-id="ff0d5-133">Вы получите повторяющееся предупреждение о запуске очереди печати принтера.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-133">You will notice that you get a repeated warning message about the Print Spooler starting up.</span></span> <span data-ttu-id="ff0d5-134">При выполнении операции службы, занимающей некоторое время, Windows PowerShell сообщит, что по-прежнему пытается выполнить задачу.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-134">When you perform a service operation that takes some time, Windows PowerShell will notify you that it is still attempting to perform the task.</span></span>

<span data-ttu-id="ff0d5-135">Если требуется перезапустить несколько служб, можно получить список служб, отфильтровать его и выполнить перезапуск:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-135">If you want to restart multiple services, you can get a list of services, filter them, and then perform the restart:</span></span>

```powershell
PS> Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service

WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
Restart-Service : Cannot stop service 'Logical Disk Manager (dmserver)' because
 it has dependent services. It can only be stopped if the Force flag is set.
At line:1 char:57
+ Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service <<<<
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
```

<span data-ttu-id="ff0d5-136">У этих командлетов Service нет параметра ComputerName, но их можно выполнить на удаленном компьютере с помощью командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-136">These Service cmdlets do not have a ComputerName parameter, but you can run them on a remote computer by using the Invoke-Command cmdlet.</span></span> <span data-ttu-id="ff0d5-137">Например, приведенная ниже команда перезапускает службу очередь печати принтера на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-137">For example, the following command restarts the Spooler service on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Restart-Service Spooler}
```

## <a name="setting-service-properties"></a><span data-ttu-id="ff0d5-138">Задание свойств служб</span><span class="sxs-lookup"><span data-stu-id="ff0d5-138">Setting Service Properties</span></span>

<span data-ttu-id="ff0d5-139">Командлет `Set-Service` изменяет свойства службы на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-139">The `Set-Service` cmdlet changes the properties of a service on a local or remote computer.</span></span> <span data-ttu-id="ff0d5-140">Так как состояние службы является свойством, этот командлет можно использовать для запуска, остановки и приостановки службы.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-140">Because the service status is a property, you can use this cmdlet to start, stop, and suspend a service.</span></span>
<span data-ttu-id="ff0d5-141">Командлет Set-Service также имеет параметр StartupType, позволяющий изменять тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ff0d5-141">The Set-Service cmdlet also has a StartupType parameter that lets you change the service startup type.</span></span>

<span data-ttu-id="ff0d5-142">Чтобы использовать командлет `Set-Service` в Windows Vista и более поздних версиях Windows, откройте среду Windows PowerShell, используя параметр "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="ff0d5-142">To use `Set-Service` on Windows Vista and later versions of Windows, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="ff0d5-143">Дополнительные сведения см. в статье о [Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service).</span><span class="sxs-lookup"><span data-stu-id="ff0d5-143">For more information, see [Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service)</span></span>

## <a name="see-also"></a><span data-ttu-id="ff0d5-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff0d5-144">See Also</span></span>

- [<span data-ttu-id="ff0d5-145">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ff0d5-145">Get-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/get-service)
- [<span data-ttu-id="ff0d5-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="ff0d5-146">Set-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/set-service)
- [<span data-ttu-id="ff0d5-147">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="ff0d5-147">Restart-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/restart-service)
- [<span data-ttu-id="ff0d5-148">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="ff0d5-148">Suspend-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/suspend-service)
