---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226717"
---
# <span data-ttu-id="d5007-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="d5007-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="d5007-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d5007-104">SYNOPSIS</span></span>
<span data-ttu-id="d5007-105">Предотвращает получение удаленных подключений конечными точками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5007-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="d5007-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5007-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d5007-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5007-107">DESCRIPTION</span></span>

<span data-ttu-id="d5007-108">`Disable-PSRemoting`Командлет блокирует удаленный доступ ко всем конфигурациям конечных точек сеанса Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-108">The `Disable-PSRemoting` cmdlet blocks remote access to all Windows PowerShell session endpoint configurations on the local computer.</span></span> <span data-ttu-id="d5007-109">Сюда входят все конечные точки, созданные с помощью PowerShell 6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d5007-109">This includes any endpoints created by PowerShell 6 or higher.</span></span>

<span data-ttu-id="d5007-110">Чтобы повторно включить удаленный доступ ко всем конфигурациям сеансов, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="d5007-110">To re-enable remote access to all session configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="d5007-111">Сюда входят все конечные точки, созданные с помощью PowerShell 6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d5007-111">This includes any endpoints created by PowerShell 6 or higher.</span></span> <span data-ttu-id="d5007-112">Чтобы включить удаленный доступ к выбранным конфигурациям сеанса, используйте параметр **AccessMode** `Set-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="d5007-112">To enable remote access to selected session configurations, use the **AccessMode** parameter of the `Set-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="d5007-113">Также можно использовать `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` командлеты и для включения и отключения конфигураций сеансов для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5007-113">You can also use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets to enable and disable session configurations for all users.</span></span> <span data-ttu-id="d5007-114">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-114">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d5007-115">Даже после запуска `Disable-PSRemoting` на локальном компьютере все равно можно выполнять замыкание соединений.</span><span class="sxs-lookup"><span data-stu-id="d5007-115">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="d5007-116">Подключение по обратной связи — это удаленный сеанс PowerShell, который создается и подключается к тому же локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d5007-116">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="d5007-117">Удаленные сеансы из внешних источников остаются заблокированными.</span><span class="sxs-lookup"><span data-stu-id="d5007-117">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="d5007-118">Для соединений с замыканием на себя необходимо использовать неявные учетные данные в параметре **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="d5007-118">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="d5007-119">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-119">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="d5007-120">Чтобы запустить этот командлет, запустите Windows PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="d5007-120">To run this cmdlet, start Windows PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="d5007-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5007-121">EXAMPLES</span></span>

### <span data-ttu-id="d5007-122">Пример 1. Предотвращение удаленного доступа ко всем конфигурациям сеансов</span><span class="sxs-lookup"><span data-stu-id="d5007-122">Example 1: Prevent remote access to all session configurations</span></span>

<span data-ttu-id="d5007-123">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-123">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="d5007-124">Пример 2. Предотвращение удаленного доступа ко всем конфигурациям сеансов без запроса подтверждения</span><span class="sxs-lookup"><span data-stu-id="d5007-124">Example 2: Prevent remote access to all session configurations without confirmation prompt</span></span>

<span data-ttu-id="d5007-125">В этом примере предотвращается удаленный доступ ко всем конфигурациям конечных точек сеанса PowerShell без запроса.</span><span class="sxs-lookup"><span data-stu-id="d5007-125">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="d5007-126">Пример 3. последствия выполнения этого командлета</span><span class="sxs-lookup"><span data-stu-id="d5007-126">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="d5007-127">В этом примере показан результат использования `Disable-PSRemoting` командлета.</span><span class="sxs-lookup"><span data-stu-id="d5007-127">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="d5007-128">Чтобы выполнить эту последовательность команд, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="d5007-128">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="d5007-129">После отключения конфигураций сеансов `New-PSSession` командлет пытается создать удаленный сеанс на локальном компьютере (также называемом "замыканием на себя").</span><span class="sxs-lookup"><span data-stu-id="d5007-129">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="d5007-130">Так как удаленный доступ отключен на локальном компьютере, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d5007-130">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
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

### <span data-ttu-id="d5007-131">Пример 4. влияние выполнения этого командлета и Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="d5007-131">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="d5007-132">В этом примере показано воздействие на конфигурации сеансов с помощью `Disable-PSRemoting` `Enable-PSRemoting` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="d5007-132">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="d5007-133">`Disable-PSRemoting` используется для отключения удаленного доступа ко всем конфигурациям конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5007-133">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="d5007-134">Параметр **Force** блокирует вывод любых запросов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5007-134">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="d5007-135">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-135">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="d5007-136">Выходные данные показывают, что всем удаленным пользователям с токеном сети отказано в доступе к конфигурациям конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d5007-136">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="d5007-137">Группе "Администраторы" на локальном компьютере разрешен доступ к конфигурациям конечных точек при условии, что они подключены локально (также называется замыканием на себя) и используют неявные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d5007-137">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="d5007-138">`Enable-PSRemoting`Командлет повторно включает удаленный доступ ко всем конфигурациям конечной точки сеанса PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-138">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="d5007-139">Параметр **Force** подавляет все запросы пользователя и перезапускает службу WinRM без запроса.</span><span class="sxs-lookup"><span data-stu-id="d5007-139">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="d5007-140">Новые выходные данные показывают, что дескрипторы безопасности **AccessDenied** были удалены из всех конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="d5007-140">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="d5007-141">Пример 5. замыкание соединений с отключенными конфигурациями конечной точки сеанса</span><span class="sxs-lookup"><span data-stu-id="d5007-141">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="d5007-142">В этом примере показано, как отключены конфигурации конечных точек, а также показано, как выполнить успешное замыкание соединения с отключенной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="d5007-142">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="d5007-143">`Disable-PSRemoting` отключает все конфигурации конечных точек сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5007-143">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="d5007-144">Первое использование `New-PSSession` пытается создать удаленный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-144">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="d5007-145">Этот тип подключения проходит через сетевой стек и не является замыканием на себя.</span><span class="sxs-lookup"><span data-stu-id="d5007-145">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="d5007-146">Следовательно, попытка подключения к отключенной конечной точке завершается сбоем с ошибкой **доступа** .</span><span class="sxs-lookup"><span data-stu-id="d5007-146">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="d5007-147">Второе использование `New-PSSession` также пытается создать удаленный сеанс для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="d5007-147">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="d5007-148">В этом случае он будет выполнен, так как это подключение с замыканием на себя, которое обходит сетевой стек.</span><span class="sxs-lookup"><span data-stu-id="d5007-148">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="d5007-149">Соединение с замыканием на себя создается при соблюдении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="d5007-149">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="d5007-150">Имя компьютера для подключения — localhost.</span><span class="sxs-lookup"><span data-stu-id="d5007-150">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="d5007-151">Учетные данные не передаются.</span><span class="sxs-lookup"><span data-stu-id="d5007-151">No credentials are passed in.</span></span> <span data-ttu-id="d5007-152">Текущий вошедший в систему пользователь (неявные учетные данные) используется для подключения.</span><span class="sxs-lookup"><span data-stu-id="d5007-152">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="d5007-153">Используется параметр ключа **EnableNetworkAccess** .</span><span class="sxs-lookup"><span data-stu-id="d5007-153">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="d5007-154">Дополнительные сведения о замыкании на себя соединений см. в разделе [New-PSSession](New-PSSession.md) Document.</span><span class="sxs-lookup"><span data-stu-id="d5007-154">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="d5007-155">Пример 6. Предотвращение удаленного доступа к конфигурациям сеансов с пользовательскими дескрипторами безопасности</span><span class="sxs-lookup"><span data-stu-id="d5007-155">Example 6: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="d5007-156">В этом примере показано, что `Disable-PSRemoting` командлет отключает удаленный доступ ко всем конфигурациям сеансов, включающим конфигурации сеансов с настраиваемыми дескрипторами безопасности.</span><span class="sxs-lookup"><span data-stu-id="d5007-156">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="d5007-157">`Register-PSSessionConfiguration` создает конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-157">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="d5007-158">Параметр **FilePath** указывает файл конфигурации сеанса, который настраивает сеанс.</span><span class="sxs-lookup"><span data-stu-id="d5007-158">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="d5007-159">Параметр **ShowSecurityDescriptorUI** отображает диалоговое окно, устанавливающее разрешения для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-159">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="d5007-160">В диалоговом окне разрешения мы создадим пользовательские разрешения на полный доступ для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5007-160">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="d5007-161">`Get-PSSessionConfiguration` `Format-Table` Командлеты и отображают конфигурации сеансов и их свойства.</span><span class="sxs-lookup"><span data-stu-id="d5007-161">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="d5007-162">Выходные данные показывают, что конфигурация **тестового** сеанса разрешает интерактивный доступ и специальные разрешения для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5007-162">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="d5007-163">`Disable-PSRemoting` отключает удаленный доступ ко всем конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="d5007-163">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="d5007-164">Теперь `Get-PSSessionConfiguration` `Format-Table` командлеты и показывают, что дескриптор безопасности **AccessDenied** для всех пользователей сети добавлен во все конфигурации сеанса, включая конфигурацию **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-164">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="d5007-165">Несмотря на то что другие дескрипторы безопасности не изменяются, дескриптор безопасности "network_deny_all" имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="d5007-165">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="d5007-166">Это продемонстрировано попыткой использования `New-PSSession` для подключения к конфигурации **тестового** сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-166">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="d5007-167">Пример 7. Повторное включение удаленного доступа для выбранных конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="d5007-167">Example 7: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="d5007-168">В этом примере показано, как повторно включить удаленный доступ к определенным конфигурациям сеансов.</span><span class="sxs-lookup"><span data-stu-id="d5007-168">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="d5007-169">После отключения всех конфигураций сеансов мы повторно включили конкретный сеанс.</span><span class="sxs-lookup"><span data-stu-id="d5007-169">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="d5007-170">`Set-PSSessionConfiguration`Командлет используется для изменения **Microsoft.** Конфигурация сеанса ServerManager.</span><span class="sxs-lookup"><span data-stu-id="d5007-170">The `Set-PSSessionConfiguration` cmdlet is used to change the **microsoft.ServerManager** session configuration.</span></span> <span data-ttu-id="d5007-171">Параметр **AccessMode** со значением **Remote** повторно включает удаленный доступ к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d5007-171">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
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

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## <span data-ttu-id="d5007-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5007-172">PARAMETERS</span></span>

### <span data-ttu-id="d5007-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d5007-173">-Confirm</span></span>

<span data-ttu-id="d5007-174">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d5007-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d5007-175">-Force</span><span class="sxs-lookup"><span data-stu-id="d5007-175">-Force</span></span>
<span data-ttu-id="d5007-176">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="d5007-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d5007-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d5007-177">-WhatIf</span></span>

<span data-ttu-id="d5007-178">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d5007-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d5007-179">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d5007-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d5007-180">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d5007-180">CommonParameters</span></span>

<span data-ttu-id="d5007-181">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5007-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5007-182">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5007-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5007-183">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d5007-183">INPUTS</span></span>

### <span data-ttu-id="d5007-184">Нет</span><span class="sxs-lookup"><span data-stu-id="d5007-184">None</span></span>

<span data-ttu-id="d5007-185">В этот командлет нельзя передать по конвейеру ни один объект.</span><span class="sxs-lookup"><span data-stu-id="d5007-185">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="d5007-186">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d5007-186">OUTPUTS</span></span>

### <span data-ttu-id="d5007-187">Нет</span><span class="sxs-lookup"><span data-stu-id="d5007-187">None</span></span>

<span data-ttu-id="d5007-188">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d5007-188">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d5007-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d5007-189">NOTES</span></span>

- <span data-ttu-id="d5007-190">Отключение конфигураций сеансов не отменяет все изменения, внесенные `Enable-PSRemoting` `Enable-PSSessionConfiguration` командлетами или.</span><span class="sxs-lookup"><span data-stu-id="d5007-190">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="d5007-191">Вам может потребоваться отменить указанные ниже изменения вручную.</span><span class="sxs-lookup"><span data-stu-id="d5007-191">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="d5007-192">Остановка и отключение службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="d5007-192">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="d5007-193">Удаление прослушивателя, принимающего запросы по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="d5007-193">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="d5007-194">Отключение исключений брандмауэра для соединений WS-Management.</span><span class="sxs-lookup"><span data-stu-id="d5007-194">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="d5007-195">Восстановление нулевого значения параметра LocalAccountTokenFilterPolicy, при котором удаленный доступ на компьютере получают только участники группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="d5007-195">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

  <span data-ttu-id="d5007-196">Конфигурация сеанса — это набор параметров, определяющих среду для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-196">A session configuration is a group of settings that define the environment for a session.</span></span> <span data-ttu-id="d5007-197">Каждый сеанс подключения к компьютеру должен использовать одну из конфигураций сеансов, зарегистрированных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-197">Every session that connects to the computer must use one of the session configurations that are registered on the computer.</span></span> <span data-ttu-id="d5007-198">Запрещая удаленный доступ ко всем конфигурациям сеансов, вы в итоге запрещаете удаленным пользователям создавать сеансы подключения к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d5007-198">By denying remote access to all session configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

  <span data-ttu-id="d5007-199">В Windows PowerShell 2,0 `Disable-PSRemoting` добавляет запись Deny_All в дескрипторы безопасности всех конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-199">In Windows PowerShell 2.0, `Disable-PSRemoting` adds a Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="d5007-200">Этот параметр запрещает всем пользователям создавать управляемые пользователем сеансы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5007-200">This setting prevents all users from creating user-managed sessions to the local computer.</span></span> <span data-ttu-id="d5007-201">В Windows PowerShell 3,0 `Disable-PSRemoting` добавляет запись Network_Deny_All в дескрипторы безопасности всех конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5007-201">In Windows PowerShell 3.0, `Disable-PSRemoting` adds a Network_Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="d5007-202">Этот параметр запрещает пользователям на других компьютерах создавать управляемые пользователем сеансы на локальном компьютере, но позволяет пользователям локального компьютера создавать управляемые пользователем сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="d5007-202">This setting prevents users on other computers from creating user-managed sessions on the local computer, but allows users of the local computer to create user-managed loopback sessions.</span></span>

  <span data-ttu-id="d5007-203">В Windows PowerShell 2,0 `Disable-PSRemoting` является аналогом `Disable-PSSessionConfiguration -Name *` .</span><span class="sxs-lookup"><span data-stu-id="d5007-203">In Windows PowerShell 2.0, `Disable-PSRemoting` is the equivalent of `Disable-PSSessionConfiguration -Name *`.</span></span> <span data-ttu-id="d5007-204">В Windows PowerShell 3,0 и более поздних версиях `Disable-PSRemoting` является аналогом `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span><span class="sxs-lookup"><span data-stu-id="d5007-204">In Windows PowerShell 3.0 and later releases, `Disable-PSRemoting` is the equivalent of `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span></span>

## <span data-ttu-id="d5007-205">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d5007-205">RELATED LINKS</span></span>

[<span data-ttu-id="d5007-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5007-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="d5007-207">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="d5007-207">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="d5007-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5007-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="d5007-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5007-209">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d5007-210">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5007-210">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="d5007-211">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5007-211">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="d5007-212">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5007-212">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="d5007-213">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="d5007-213">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
