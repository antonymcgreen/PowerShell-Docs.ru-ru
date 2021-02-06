---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 4410c8f41fffcaae9c9f447af246f335033d53a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604717"
---
# <span data-ttu-id="f471d-102">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="f471d-102">Disable-PSRemoting</span></span>

## <span data-ttu-id="f471d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f471d-103">SYNOPSIS</span></span>
<span data-ttu-id="f471d-104">Предотвращает получение удаленных подключений конечными точками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-104">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="f471d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f471d-105">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f471d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f471d-106">DESCRIPTION</span></span>

<span data-ttu-id="f471d-107">`Disable-PSRemoting`Командлет блокирует удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell версии 6 и выше на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-107">The `Disable-PSRemoting` cmdlet blocks remote access to all PowerShell version 6 and greater session endpoint configurations on the local computer.</span></span> <span data-ttu-id="f471d-108">Он не влияет на конфигурации конечных точек Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-108">It does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="f471d-109">Чтобы отключить конфигурации конечных точек сеанса Windows PowerShell, выполните `Disable-PSRemoting` команду в сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-109">To disable Windows PowerShell session endpoint configurations, run `Disable-PSRemoting` command from within a Windows PowerShell session.</span></span>

<span data-ttu-id="f471d-110">Чтобы повторно включить удаленный доступ ко всем конфигурациям PowerShell версии 6 и большей конечной точки сеанса, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="f471d-110">To re-enable remote access to all PowerShell version 6 and greater session endpoint configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="f471d-111">Чтобы повторно включить удаленный доступ ко всем конфигурациям конечных точек сеанса Windows PowerShell, выполните команду `Enable-PSRemoting` из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-111">To re-enable remote access to all Windows PowerShell session endpoint configurations, run `Enable-PSRemoting` from within a Windows PowerShell session.</span></span>

> [!NOTE]
> <span data-ttu-id="f471d-112">Если вы хотите отключить весь удаленный доступ PowerShell к локальному компьютеру Windows, выполните эту команду как из сеанса PowerShell версии 6 или выше, так и из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-112">If you want to disable all PowerShell remote access to a local Windows machine, you must run this command both from a within PowerShell version 6 or greater session and from within a Windows PowerShell session.</span></span> <span data-ttu-id="f471d-113">Windows PowerShell устанавливается на всех компьютерах Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f471d-113">Windows PowerShell is installed on all Windows machines by default.</span></span>

<span data-ttu-id="f471d-114">Чтобы отключить и снова включить удаленный доступ к конкретным конфигурациям конечной точки сеанса, используйте `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="f471d-114">To disable and re-enable remote access to specific session endpoint configurations, use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="f471d-115">Чтобы задать конкретные конфигурации доступа для отдельных конечных точек, используйте `Set-PSSessionConfiguration` командлет вместе с параметром **AccessMode** .</span><span class="sxs-lookup"><span data-stu-id="f471d-115">To set specific access configurations of individual endpoints, use the `Set-PSSessionConfiguration` cmdlet along with the **AccessMode** parameter.</span></span> <span data-ttu-id="f471d-116">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f471d-116">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f471d-117">Даже после запуска `Disable-PSRemoting` на локальном компьютере все равно можно выполнять замыкание соединений.</span><span class="sxs-lookup"><span data-stu-id="f471d-117">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="f471d-118">Подключение по обратной связи — это удаленный сеанс PowerShell, который создается и подключается к тому же локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f471d-118">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="f471d-119">Удаленные сеансы из внешних источников остаются заблокированными.</span><span class="sxs-lookup"><span data-stu-id="f471d-119">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="f471d-120">Для соединений с замыканием на себя необходимо использовать неявные учетные данные в параметре **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="f471d-120">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="f471d-121">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="f471d-121">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="f471d-122">Этот командлет доступен только на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="f471d-122">This cmdlet is only available on the Windows platform.</span></span> <span data-ttu-id="f471d-123">Эта версия недоступна в Linux и macOS версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-123">It is not available on Linux or macOS versions of PowerShell.</span></span> <span data-ttu-id="f471d-124">Чтобы запустить этот командлет, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="f471d-124">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="f471d-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="f471d-125">EXAMPLES</span></span>

### <span data-ttu-id="f471d-126">Пример 1. Предотвращение удаленного доступа ко всем конфигурациям сеансов PowerShell</span><span class="sxs-lookup"><span data-stu-id="f471d-126">Example 1: Prevent remote access to all PowerShell session configurations</span></span>

<span data-ttu-id="f471d-127">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-127">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

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

### <span data-ttu-id="f471d-128">Пример 2. Предотвращение удаленного доступа ко всем конфигурациям сеансов PowerShell без запроса подтверждения</span><span class="sxs-lookup"><span data-stu-id="f471d-128">Example 2: Prevent remote access to all PowerShell session configurations without confirmation prompt</span></span>

<span data-ttu-id="f471d-129">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечных точек сеанса PowerShell без запроса.</span><span class="sxs-lookup"><span data-stu-id="f471d-129">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

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

### <span data-ttu-id="f471d-130">Пример 3. последствия выполнения этого командлета</span><span class="sxs-lookup"><span data-stu-id="f471d-130">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="f471d-131">В этом примере показан результат использования `Disable-PSRemoting` командлета.</span><span class="sxs-lookup"><span data-stu-id="f471d-131">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="f471d-132">Чтобы выполнить эту последовательность команд, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="f471d-132">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="f471d-133">После отключения конфигураций сеансов `New-PSSession` командлет пытается создать удаленный сеанс на локальном компьютере (также называемом "замыканием на себя").</span><span class="sxs-lookup"><span data-stu-id="f471d-133">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="f471d-134">Так как удаленный доступ отключен на локальном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f471d-134">Because remote access is disabled on the local machine, the command fails.</span></span>

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

### <span data-ttu-id="f471d-135">Пример 4. влияние выполнения этого командлета и Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="f471d-135">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="f471d-136">В этом примере показано воздействие на конфигурации сеансов с помощью `Disable-PSRemoting` `Enable-PSRemoting` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="f471d-136">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="f471d-137">`Disable-PSRemoting` используется для отключения удаленного доступа ко всем конфигурациям конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-137">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="f471d-138">Параметр **Force** блокирует вывод любых запросов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f471d-138">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="f471d-139">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-139">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="f471d-140">Выходные данные показывают, что всем удаленным пользователям с токеном сети отказано в доступе к конфигурациям конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f471d-140">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="f471d-141">Группе "Администраторы" на локальном компьютере разрешен доступ к конфигурациям конечных точек при условии, что они подключены локально (также называется замыканием на себя) и используют неявные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f471d-141">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

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

<span data-ttu-id="f471d-142">`Enable-PSRemoting`Командлет повторно включает удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-142">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="f471d-143">Параметр **Force** подавляет все запросы пользователя и перезапускает службу WinRM без запроса.</span><span class="sxs-lookup"><span data-stu-id="f471d-143">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="f471d-144">Новые выходные данные показывают, что дескрипторы безопасности **AccessDenied** были удалены из всех конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="f471d-144">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="f471d-145">Пример 5. замыкание соединений с отключенными конфигурациями конечной точки сеанса</span><span class="sxs-lookup"><span data-stu-id="f471d-145">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="f471d-146">В этом примере показано, как отключены конфигурации конечных точек, а также показано, как выполнить успешное замыкание соединения с отключенной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="f471d-146">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="f471d-147">`Disable-PSRemoting` отключает все конфигурации конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-147">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

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

<span data-ttu-id="f471d-148">Первое использование `New-PSSession` пытается создать удаленный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-148">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="f471d-149">Параметр **configurationName** используется для указания отключенной конечной точки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-149">The **ConfigurationName** parameter is used to specify a disabled PowerShell endpoint.</span></span> <span data-ttu-id="f471d-150">Учетные данные явно передаются в команду через параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="f471d-150">Credentials are explicitly passed to the command through the **Credential** parameter.</span></span> <span data-ttu-id="f471d-151">Этот тип подключения проходит через сетевой стек и не является замыканием на себя.</span><span class="sxs-lookup"><span data-stu-id="f471d-151">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="f471d-152">Следовательно, попытка подключения к отключенной конечной точке завершается сбоем с ошибкой **доступа** .</span><span class="sxs-lookup"><span data-stu-id="f471d-152">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="f471d-153">Второе использование `New-PSSession` также пытается создать удаленный сеанс для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="f471d-153">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="f471d-154">В этом случае он будет выполнен, так как это подключение с замыканием на себя, которое обходит сетевой стек.</span><span class="sxs-lookup"><span data-stu-id="f471d-154">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="f471d-155">Соединение с замыканием на себя создается при соблюдении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="f471d-155">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="f471d-156">Имя компьютера для подключения — localhost.</span><span class="sxs-lookup"><span data-stu-id="f471d-156">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="f471d-157">Учетные данные не передаются.</span><span class="sxs-lookup"><span data-stu-id="f471d-157">No credentials are passed in.</span></span> <span data-ttu-id="f471d-158">Текущий вошедший в систему пользователь (неявные учетные данные) используется для подключения.</span><span class="sxs-lookup"><span data-stu-id="f471d-158">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="f471d-159">Используется параметр ключа **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="f471d-159">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="f471d-160">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md) Document.</span><span class="sxs-lookup"><span data-stu-id="f471d-160">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="f471d-161">Пример 6. Отключение всех конфигураций конечных точек удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="f471d-161">Example 6: Disabling all PowerShell remoting endpoint configurations</span></span>

<span data-ttu-id="f471d-162">В этом примере показано, как выполнение `Disable-PSRemoting` команды не влияет на конфигурации конечных точек Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-162">This example demonstrates how running the `Disable-PSRemoting` command does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="f471d-163">`Get-PSSessionConfiguration` в Windows PowerShell отображаются все конфигурации конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f471d-163">`Get-PSSessionConfiguration` run within Windows PowerShell shows all endpoint configurations.</span></span> <span data-ttu-id="f471d-164">Мы видим, что конфигурации конечных точек Windows PowerShell не отключены.</span><span class="sxs-lookup"><span data-stu-id="f471d-164">We see that the Windows PowerShell endpoint configurations are not disabled.</span></span>

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

<span data-ttu-id="f471d-165">Чтобы отключить эти конфигурации конечных точек, `Disable-PSRemoting` необходимо запустить команду из сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f471d-165">To disable these endpoint configurations, the `Disable-PSRemoting` command must be run from within a Windows PowerShell session.</span></span> <span data-ttu-id="f471d-166">Теперь `Get-PSSessionConfiguration` при запуске в Windows PowerShell показывается, что все конфигурации конечных точек отключены.</span><span class="sxs-lookup"><span data-stu-id="f471d-166">Now, `Get-PSSessionConfiguration` run from within Windows PowerShell shows that all endpoint configurations are disabled.</span></span>

### <span data-ttu-id="f471d-167">Пример 7. Предотвращение удаленного доступа к конфигурациям сеансов с пользовательскими дескрипторами безопасности</span><span class="sxs-lookup"><span data-stu-id="f471d-167">Example 7: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="f471d-168">В этом примере показано, что `Disable-PSRemoting` командлет отключает удаленный доступ ко всем конфигурациям сеансов, включающим конфигурации сеансов с настраиваемыми дескрипторами безопасности.</span><span class="sxs-lookup"><span data-stu-id="f471d-168">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="f471d-169">`Register-PSSessionConfiguration` создает конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="f471d-169">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="f471d-170">Параметр **FilePath** указывает файл конфигурации сеанса, который настраивает сеанс.</span><span class="sxs-lookup"><span data-stu-id="f471d-170">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="f471d-171">Параметр **ShowSecurityDescriptorUI** отображает диалоговое окно, устанавливающее разрешения для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f471d-171">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="f471d-172">В диалоговом окне разрешения мы создадим пользовательские разрешения на полный доступ для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f471d-172">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="f471d-173">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеансов и их свойства.</span><span class="sxs-lookup"><span data-stu-id="f471d-173">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="f471d-174">Выходные данные показывают, что конфигурация **тестового** сеанса разрешает интерактивный доступ и специальные разрешения для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f471d-174">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="f471d-175">`Disable-PSRemoting` отключает удаленный доступ ко всем конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="f471d-175">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

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

<span data-ttu-id="f471d-176">Теперь `Get-PSSessionConfiguration` `Format-Table` командлеты и показывают, что дескриптор безопасности **AccessDenied** для всех пользователей сети добавлен во все конфигурации сеанса, включая конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="f471d-176">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="f471d-177">Несмотря на то что другие дескрипторы безопасности не изменяются, дескриптор безопасности "network_deny_all" имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f471d-177">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="f471d-178">Это продемонстрировано попыткой использования `New-PSSession` для подключения к конфигурации **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="f471d-178">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="f471d-179">Пример 8. Повторное включение удаленного доступа для выбранных конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="f471d-179">Example 8: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="f471d-180">В этом примере показано, как повторно включить удаленный доступ к определенным конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="f471d-180">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="f471d-181">После отключения всех конфигураций сеансов мы повторно включили конкретный сеанс.</span><span class="sxs-lookup"><span data-stu-id="f471d-181">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="f471d-182">`Set-PSSessionConfiguration`Командлет используется для изменения конфигурации сеанса **PowerShell. 6** .</span><span class="sxs-lookup"><span data-stu-id="f471d-182">The `Set-PSSessionConfiguration` cmdlet is used to change the **PowerShell.6** session configuration.</span></span> <span data-ttu-id="f471d-183">Параметр **AccessMode** со значением **Remote** повторно включает удаленный доступ к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f471d-183">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

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

## <span data-ttu-id="f471d-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f471d-184">PARAMETERS</span></span>

### <span data-ttu-id="f471d-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f471d-185">-Confirm</span></span>

<span data-ttu-id="f471d-186">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f471d-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f471d-187">-Force</span><span class="sxs-lookup"><span data-stu-id="f471d-187">-Force</span></span>

<span data-ttu-id="f471d-188">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="f471d-188">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="f471d-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f471d-189">-WhatIf</span></span>

<span data-ttu-id="f471d-190">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f471d-190">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f471d-191">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f471d-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f471d-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f471d-192">CommonParameters</span></span>

<span data-ttu-id="f471d-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f471d-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f471d-194">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f471d-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f471d-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f471d-195">INPUTS</span></span>

### <span data-ttu-id="f471d-196">None</span><span class="sxs-lookup"><span data-stu-id="f471d-196">None</span></span>

<span data-ttu-id="f471d-197">В этот командлет нельзя передать по конвейеру ни один объект.</span><span class="sxs-lookup"><span data-stu-id="f471d-197">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="f471d-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f471d-198">OUTPUTS</span></span>

### <span data-ttu-id="f471d-199">None</span><span class="sxs-lookup"><span data-stu-id="f471d-199">None</span></span>

<span data-ttu-id="f471d-200">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f471d-200">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f471d-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f471d-201">NOTES</span></span>

<span data-ttu-id="f471d-202">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="f471d-202">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="f471d-203">Отключение конфигураций сеансов не отменяет все изменения, внесенные `Enable-PSRemoting` `Enable-PSSessionConfiguration` командлетами или.</span><span class="sxs-lookup"><span data-stu-id="f471d-203">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="f471d-204">Вам может потребоваться отменить указанные ниже изменения вручную.</span><span class="sxs-lookup"><span data-stu-id="f471d-204">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="f471d-205">Остановка и отключение службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="f471d-205">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="f471d-206">Удаление прослушивателя, принимающего запросы по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="f471d-206">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="f471d-207">Отключение исключений брандмауэра для соединений WS-Management.</span><span class="sxs-lookup"><span data-stu-id="f471d-207">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="f471d-208">Восстановление нулевого значения параметра LocalAccountTokenFilterPolicy, при котором удаленный доступ на компьютере получают только участники группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="f471d-208">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

- <span data-ttu-id="f471d-209">Конфигурация конечной точки сеанса — это группа параметров, определяющих среду для сеанса.</span><span class="sxs-lookup"><span data-stu-id="f471d-209">A session endpoint configuration is a group of settings that define the environment for a session.</span></span>
  <span data-ttu-id="f471d-210">Каждый сеанс, подключающийся к компьютеру, должен использовать одну из конфигураций конечной точки сеанса, зарегистрированных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f471d-210">Every session that connects to the computer must use one of the session endpoint configurations that are registered on the computer.</span></span> <span data-ttu-id="f471d-211">Запрет удаленного доступа ко всем конфигурациям конечных точек сеанса позволяет удаленным пользователям предотвращать установку сеансов, подключающихся к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f471d-211">By denying remote access to all session endpoint configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

## <span data-ttu-id="f471d-212">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f471d-212">RELATED LINKS</span></span>

[<span data-ttu-id="f471d-213">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f471d-213">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f471d-214">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="f471d-214">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="f471d-215">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f471d-215">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f471d-216">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f471d-216">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f471d-217">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f471d-217">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f471d-218">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f471d-218">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f471d-219">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f471d-219">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f471d-220">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="f471d-220">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
