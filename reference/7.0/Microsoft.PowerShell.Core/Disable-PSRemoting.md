---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: f4fe65ec687ca39c1356dd5c9a590899c8b3789c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346009"
---
# <span data-ttu-id="3bab2-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="3bab2-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="3bab2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3bab2-104">SYNOPSIS</span></span>
<span data-ttu-id="3bab2-105">Предотвращает получение удаленных подключений конечными точками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="3bab2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3bab2-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3bab2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3bab2-107">DESCRIPTION</span></span>

<span data-ttu-id="3bab2-108">`Disable-PSRemoting`Командлет блокирует удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell версии 6 и выше на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-108">The `Disable-PSRemoting` cmdlet blocks remote access to all PowerShell version 6 and greater session endpoint configurations on the local computer.</span></span> <span data-ttu-id="3bab2-109">Он не влияет на конфигурации конечных точек Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-109">It does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="3bab2-110">Чтобы отключить конфигурации конечных точек сеанса Windows PowerShell, выполните `Disable-PSRemoting` команду в сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-110">To disable Windows PowerShell session endpoint configurations, run `Disable-PSRemoting` command from within a Windows PowerShell session.</span></span>

<span data-ttu-id="3bab2-111">Чтобы повторно включить удаленный доступ ко всем конфигурациям PowerShell версии 6 и большей конечной точки сеанса, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="3bab2-111">To re-enable remote access to all PowerShell version 6 and greater session endpoint configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="3bab2-112">Чтобы повторно включить удаленный доступ ко всем конфигурациям конечных точек сеанса Windows PowerShell, выполните команду `Enable-PSRemoting` из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-112">To re-enable remote access to all Windows PowerShell session endpoint configurations, run `Enable-PSRemoting` from within a Windows PowerShell session.</span></span>

> [!NOTE]
> <span data-ttu-id="3bab2-113">Если вы хотите отключить весь удаленный доступ PowerShell к локальному компьютеру Windows, выполните эту команду как из сеанса PowerShell версии 6 или выше, так и из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-113">If you want to disable all PowerShell remote access to a local Windows machine, you must run this command both from a within PowerShell version 6 or greater session and from within a Windows PowerShell session.</span></span> <span data-ttu-id="3bab2-114">Windows PowerShell устанавливается на всех компьютерах Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3bab2-114">Windows PowerShell is installed on all Windows machines by default.</span></span>

<span data-ttu-id="3bab2-115">Чтобы отключить и снова включить удаленный доступ к конкретным конфигурациям конечной точки сеанса, используйте `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="3bab2-115">To disable and re-enable remote access to specific session endpoint configurations, use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="3bab2-116">Чтобы задать конкретные конфигурации доступа для отдельных конечных точек, используйте `Set-PSSessionConfiguration` командлет вместе с параметром **AccessMode** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-116">To set specific access configurations of individual endpoints, use the `Set-PSSessionConfiguration` cmdlet along with the **AccessMode** parameter.</span></span> <span data-ttu-id="3bab2-117">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="3bab2-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3bab2-118">Даже после запуска `Disable-PSRemoting` на локальном компьютере все равно можно выполнять замыкание соединений.</span><span class="sxs-lookup"><span data-stu-id="3bab2-118">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="3bab2-119">Подключение по обратной связи — это удаленный сеанс PowerShell, который создается и подключается к тому же локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3bab2-119">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="3bab2-120">Удаленные сеансы из внешних источников остаются заблокированными.</span><span class="sxs-lookup"><span data-stu-id="3bab2-120">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="3bab2-121">Для соединений с замыканием на себя необходимо использовать неявные учетные данные в параметре **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-121">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="3bab2-122">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="3bab2-122">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="3bab2-123">Этот командлет доступен только на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="3bab2-123">This cmdlet is only available on the Windows platform.</span></span> <span data-ttu-id="3bab2-124">Эта версия недоступна в Linux и macOS версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-124">It is not available on Linux or macOS versions of PowerShell.</span></span> <span data-ttu-id="3bab2-125">Чтобы запустить этот командлет, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-125">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="3bab2-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="3bab2-126">EXAMPLES</span></span>

### <span data-ttu-id="3bab2-127">Пример 1. Предотвращение удаленного доступа ко всем конфигурациям сеансов PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bab2-127">Example 1: Prevent remote access to all PowerShell session configurations</span></span>

<span data-ttu-id="3bab2-128">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-128">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="3bab2-129">Пример 2. Предотвращение удаленного доступа ко всем конфигурациям сеансов PowerShell без запроса подтверждения</span><span class="sxs-lookup"><span data-stu-id="3bab2-129">Example 2: Prevent remote access to all PowerShell session configurations without confirmation prompt</span></span>

<span data-ttu-id="3bab2-130">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечных точек сеанса PowerShell без запроса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-130">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="3bab2-131">Пример 3. последствия выполнения этого командлета</span><span class="sxs-lookup"><span data-stu-id="3bab2-131">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="3bab2-132">В этом примере показан результат использования `Disable-PSRemoting` командлета.</span><span class="sxs-lookup"><span data-stu-id="3bab2-132">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="3bab2-133">Чтобы выполнить эту последовательность команд, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-133">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="3bab2-134">После отключения конфигураций сеансов `New-PSSession` командлет пытается создать удаленный сеанс на локальном компьютере (также называемом "замыканием на себя").</span><span class="sxs-lookup"><span data-stu-id="3bab2-134">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="3bab2-135">Так как удаленный доступ отключен на локальном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3bab2-135">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### <span data-ttu-id="3bab2-136">Пример 4. влияние выполнения этого командлета и Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="3bab2-136">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="3bab2-137">В этом примере показано воздействие на конфигурации сеансов с помощью `Disable-PSRemoting` `Enable-PSRemoting` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="3bab2-137">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="3bab2-138">`Disable-PSRemoting` используется для отключения удаленного доступа ко всем конфигурациям конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-138">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="3bab2-139">Параметр **Force** блокирует вывод любых запросов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3bab2-139">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="3bab2-140">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-140">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="3bab2-141">Выходные данные показывают, что всем удаленным пользователям с токеном сети отказано в доступе к конфигурациям конечных точек.</span><span class="sxs-lookup"><span data-stu-id="3bab2-141">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="3bab2-142">Группе "Администраторы" на локальном компьютере разрешен доступ к конфигурациям конечных точек при условии, что они подключены локально (также называется замыканием на себя) и используют неявные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3bab2-142">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

<span data-ttu-id="3bab2-143">`Enable-PSRemoting`Командлет повторно включает удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-143">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="3bab2-144">Параметр **Force** подавляет все запросы пользователя и перезапускает службу WinRM без запроса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-144">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="3bab2-145">Новые выходные данные показывают, что дескрипторы безопасности **AccessDenied** были удалены из всех конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="3bab2-145">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="3bab2-146">Пример 5. замыкание соединений с отключенными конфигурациями конечной точки сеанса</span><span class="sxs-lookup"><span data-stu-id="3bab2-146">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="3bab2-147">В этом примере показано, как отключены конфигурации конечных точек, а также показано, как выполнить успешное замыкание соединения с отключенной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="3bab2-147">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="3bab2-148">`Disable-PSRemoting` отключает все конфигурации конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-148">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="3bab2-149">Первое использование `New-PSSession` пытается создать удаленный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-149">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="3bab2-150">Параметр **configurationName** используется для указания отключенной конечной точки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-150">The **ConfigurationName** parameter is used to specify a disabled PowerShell endpoint.</span></span> <span data-ttu-id="3bab2-151">Учетные данные явно передаются в команду через параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-151">Credentials are explicitly passed to the command through the **Credential** parameter.</span></span> <span data-ttu-id="3bab2-152">Этот тип подключения проходит через сетевой стек и не является замыканием на себя.</span><span class="sxs-lookup"><span data-stu-id="3bab2-152">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="3bab2-153">Следовательно, попытка подключения к отключенной конечной точке завершается сбоем с ошибкой **доступа** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-153">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="3bab2-154">Второе использование `New-PSSession` также пытается создать удаленный сеанс для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3bab2-154">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="3bab2-155">В этом случае он будет выполнен, так как это подключение с замыканием на себя, которое обходит сетевой стек.</span><span class="sxs-lookup"><span data-stu-id="3bab2-155">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="3bab2-156">Соединение с замыканием на себя создается при соблюдении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="3bab2-156">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="3bab2-157">Имя компьютера для подключения — localhost.</span><span class="sxs-lookup"><span data-stu-id="3bab2-157">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="3bab2-158">Учетные данные не передаются.</span><span class="sxs-lookup"><span data-stu-id="3bab2-158">No credentials are passed in.</span></span> <span data-ttu-id="3bab2-159">Текущий вошедший в систему пользователь (неявные учетные данные) используется для подключения.</span><span class="sxs-lookup"><span data-stu-id="3bab2-159">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="3bab2-160">Используется параметр ключа **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-160">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="3bab2-161">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md) Document.</span><span class="sxs-lookup"><span data-stu-id="3bab2-161">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="3bab2-162">Пример 6. Отключение всех конфигураций конечных точек удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bab2-162">Example 6: Disabling all PowerShell remoting endpoint configurations</span></span>

<span data-ttu-id="3bab2-163">В этом примере показано, как выполнение `Disable-PSRemoting` команды не влияет на конфигурации конечных точек Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-163">This example demonstrates how running the `Disable-PSRemoting` command does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="3bab2-164">`Get-PSSessionConfiguration` в Windows PowerShell отображаются все конфигурации конечных точек.</span><span class="sxs-lookup"><span data-stu-id="3bab2-164">`Get-PSSessionConfiguration` run within Windows PowerShell shows all endpoint configurations.</span></span> <span data-ttu-id="3bab2-165">Мы видим, что конфигурации конечных точек Windows PowerShell не отключены.</span><span class="sxs-lookup"><span data-stu-id="3bab2-165">We see that the Windows PowerShell endpoint configurations are not disabled.</span></span>

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

<span data-ttu-id="3bab2-166">Чтобы отключить эти конфигурации конечных точек, `Disable-PSRemoting` необходимо запустить команду из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bab2-166">To disable these endpoint configurations, the `Disable-PSRemoting` command must be run from within a Windows PowerShell session.</span></span> <span data-ttu-id="3bab2-167">Теперь `Get-PSSessionConfiguration` при запуске в Windows PowerShell показывается, что все конфигурации конечных точек отключены.</span><span class="sxs-lookup"><span data-stu-id="3bab2-167">Now, `Get-PSSessionConfiguration` run from within Windows PowerShell shows that all endpoint configurations are disabled.</span></span>

### <span data-ttu-id="3bab2-168">Пример 7. Предотвращение удаленного доступа к конфигурациям сеансов с пользовательскими дескрипторами безопасности</span><span class="sxs-lookup"><span data-stu-id="3bab2-168">Example 7: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="3bab2-169">В этом примере показано, что `Disable-PSRemoting` командлет отключает удаленный доступ ко всем конфигурациям сеансов, включающим конфигурации сеансов с настраиваемыми дескрипторами безопасности.</span><span class="sxs-lookup"><span data-stu-id="3bab2-169">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="3bab2-170">`Register-PSSessionConfiguration` создает конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-170">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="3bab2-171">Параметр **FilePath** указывает файл конфигурации сеанса, который настраивает сеанс.</span><span class="sxs-lookup"><span data-stu-id="3bab2-171">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="3bab2-172">Параметр **ShowSecurityDescriptorUI** отображает диалоговое окно, устанавливающее разрешения для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-172">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="3bab2-173">В диалоговом окне разрешения мы создадим пользовательские разрешения на полный доступ для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="3bab2-173">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="3bab2-174">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеансов и их свойства.</span><span class="sxs-lookup"><span data-stu-id="3bab2-174">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="3bab2-175">Выходные данные показывают, что конфигурация **тестового** сеанса разрешает интерактивный доступ и специальные разрешения для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="3bab2-175">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="3bab2-176">`Disable-PSRemoting` отключает удаленный доступ ко всем конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="3bab2-176">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

<span data-ttu-id="3bab2-177">Теперь `Get-PSSessionConfiguration` `Format-Table` командлеты и показывают, что дескриптор безопасности **AccessDenied** для всех пользователей сети добавлен во все конфигурации сеанса, включая конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-177">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="3bab2-178">Несмотря на то что другие дескрипторы безопасности не изменяются, дескриптор безопасности "network_deny_all" имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="3bab2-178">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="3bab2-179">Это продемонстрировано попыткой использования `New-PSSession` для подключения к конфигурации **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-179">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="3bab2-180">Пример 8. Повторное включение удаленного доступа для выбранных конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="3bab2-180">Example 8: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="3bab2-181">В этом примере показано, как повторно включить удаленный доступ к определенным конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="3bab2-181">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="3bab2-182">После отключения всех конфигураций сеансов мы повторно включили конкретный сеанс.</span><span class="sxs-lookup"><span data-stu-id="3bab2-182">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="3bab2-183">`Set-PSSessionConfiguration`Командлет используется для изменения конфигурации сеанса **PowerShell. 6** .</span><span class="sxs-lookup"><span data-stu-id="3bab2-183">The `Set-PSSessionConfiguration` cmdlet is used to change the **PowerShell.6** session configuration.</span></span> <span data-ttu-id="3bab2-184">Параметр **AccessMode** со значением **Remote** повторно включает удаленный доступ к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bab2-184">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

## <span data-ttu-id="3bab2-185">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3bab2-185">PARAMETERS</span></span>

### <span data-ttu-id="3bab2-186">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3bab2-186">-Confirm</span></span>

<span data-ttu-id="3bab2-187">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3bab2-187">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3bab2-188">-Force</span><span class="sxs-lookup"><span data-stu-id="3bab2-188">-Force</span></span>

<span data-ttu-id="3bab2-189">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="3bab2-189">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="3bab2-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3bab2-190">-WhatIf</span></span>

<span data-ttu-id="3bab2-191">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3bab2-191">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3bab2-192">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3bab2-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3bab2-193">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3bab2-193">CommonParameters</span></span>

<span data-ttu-id="3bab2-194">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3bab2-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3bab2-195">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3bab2-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3bab2-196">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3bab2-196">INPUTS</span></span>

### <span data-ttu-id="3bab2-197">Нет</span><span class="sxs-lookup"><span data-stu-id="3bab2-197">None</span></span>

<span data-ttu-id="3bab2-198">В этот командлет нельзя передать по конвейеру ни один объект.</span><span class="sxs-lookup"><span data-stu-id="3bab2-198">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="3bab2-199">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3bab2-199">OUTPUTS</span></span>

### <span data-ttu-id="3bab2-200">Нет</span><span class="sxs-lookup"><span data-stu-id="3bab2-200">None</span></span>

<span data-ttu-id="3bab2-201">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3bab2-201">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3bab2-202">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3bab2-202">NOTES</span></span>

<span data-ttu-id="3bab2-203">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="3bab2-203">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="3bab2-204">Отключение конфигураций сеансов не отменяет все изменения, внесенные `Enable-PSRemoting` `Enable-PSSessionConfiguration` командлетами или.</span><span class="sxs-lookup"><span data-stu-id="3bab2-204">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="3bab2-205">Вам может потребоваться отменить указанные ниже изменения вручную.</span><span class="sxs-lookup"><span data-stu-id="3bab2-205">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="3bab2-206">Остановка и отключение службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="3bab2-206">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="3bab2-207">Удаление прослушивателя, принимающего запросы по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="3bab2-207">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="3bab2-208">Отключение исключений брандмауэра для соединений WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3bab2-208">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="3bab2-209">Восстановление нулевого значения параметра LocalAccountTokenFilterPolicy, при котором удаленный доступ на компьютере получают только участники группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="3bab2-209">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

- <span data-ttu-id="3bab2-210">Конфигурация конечной точки сеанса — это группа параметров, определяющих среду для сеанса.</span><span class="sxs-lookup"><span data-stu-id="3bab2-210">A session endpoint configuration is a group of settings that define the environment for a session.</span></span>
  <span data-ttu-id="3bab2-211">Каждый сеанс, подключающийся к компьютеру, должен использовать одну из конфигураций конечной точки сеанса, зарегистрированных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bab2-211">Every session that connects to the computer must use one of the session endpoint configurations that are registered on the computer.</span></span> <span data-ttu-id="3bab2-212">Запрет удаленного доступа ко всем конфигурациям конечных точек сеанса позволяет удаленным пользователям предотвращать установку сеансов, подключающихся к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3bab2-212">By denying remote access to all session endpoint configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

## <span data-ttu-id="3bab2-213">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3bab2-213">RELATED LINKS</span></span>

[<span data-ttu-id="3bab2-214">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bab2-214">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="3bab2-215">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="3bab2-215">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="3bab2-216">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bab2-216">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="3bab2-217">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3bab2-217">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="3bab2-218">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bab2-218">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="3bab2-219">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bab2-219">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="3bab2-220">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bab2-220">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="3bab2-221">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="3bab2-221">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
