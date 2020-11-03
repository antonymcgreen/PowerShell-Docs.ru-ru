---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227945"
---
# <span data-ttu-id="951a1-103">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-103">Remove-Computer</span></span>

## <span data-ttu-id="951a1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="951a1-104">SYNOPSIS</span></span>
<span data-ttu-id="951a1-105">Удаляет локальный компьютер из его домена.</span><span class="sxs-lookup"><span data-stu-id="951a1-105">Removes the local computer from its domain.</span></span>

## <span data-ttu-id="951a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="951a1-106">SYNTAX</span></span>

### <span data-ttu-id="951a1-107">Local (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="951a1-107">Local (Default)</span></span>

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="951a1-108">Удаленный доступ</span><span class="sxs-lookup"><span data-stu-id="951a1-108">Remote</span></span>

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="951a1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="951a1-109">DESCRIPTION</span></span>

<span data-ttu-id="951a1-110">`Remove-Computer`Командлет удаляет локальный компьютер и удаленные компьютеры из текущих доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-110">The `Remove-Computer` cmdlet removes the local computer and remote computers from their current domains.</span></span>

<span data-ttu-id="951a1-111">При удалении компьютера из домена `Remove-Computer` также отключает учетную запись домена компьютера.</span><span class="sxs-lookup"><span data-stu-id="951a1-111">When you remove a computer from a domain, `Remove-Computer` also disables the domain account of the computer.</span></span> <span data-ttu-id="951a1-112">Необходимо предоставить явные учетные данные, чтобы отсоединить компьютер от своего домена, даже если они являются учетными данными текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="951a1-112">You must provide explicit credentials to unjoin the computer from its domain, even when they are the credentials of the current user.</span></span> <span data-ttu-id="951a1-113">Необходимо перезагрузить компьютер, чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="951a1-113">You must restart the computer to make the change effective.</span></span> <span data-ttu-id="951a1-114">При удалении компьютера из домена необходимо переместить его в рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="951a1-114">Also, when you remove a computer from a domain, you must move it to a workgroup.</span></span> <span data-ttu-id="951a1-115">Используйте параметр **WorkgroupName** для указания рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="951a1-115">Use the **WorkgroupName** parameter to specify the workgroup.</span></span>

<span data-ttu-id="951a1-116">Чтобы переместить компьютер из рабочей группы в домен, из одной рабочей группы в другую или из одного домена в другой, используйте `Add-Computer` командлет.</span><span class="sxs-lookup"><span data-stu-id="951a1-116">To move a computer from a workgroup to a domain, from one workgroup to another, or from one domain to another, use the `Add-Computer` cmdlet.</span></span>

<span data-ttu-id="951a1-117">Чтобы получить результаты выполнения команды, используйте параметры **Verbose** и **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="951a1-117">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span> <span data-ttu-id="951a1-118">Чтобы скрыть запрос к пользователю, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="951a1-118">To suppress the user prompt, use the **Force** parameter.</span></span>

<span data-ttu-id="951a1-119">`Remove-Computer` удаляет локальный компьютер и удаленные компьютеры из доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-119">`Remove-Computer` removes the local computer and remote computers from domains.</span></span> <span data-ttu-id="951a1-120">Это включает в себя параметры учетных данных, в которых указаны альтернативные учетные данные для подключения к удаленным компьютерам и отсоединения от домена, параметр **Restart** для перезагрузки затронутых компьютеров, параметр **WorkgroupName** для указания имени рабочей группы, в которую добавляются компьютеры.</span><span class="sxs-lookup"><span data-stu-id="951a1-120">It includes credential parameters that specify alternate credentials for connecting to remote computers, and unjoining from a domain, a **Restart** parameter for restarting the affected computers, and a **WorkgroupName** parameter for specifying the name of the workgroup to which computers are added.</span></span>

## <span data-ttu-id="951a1-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="951a1-121">EXAMPLES</span></span>

### <span data-ttu-id="951a1-122">Пример 1. Удаление локального компьютера из своего домена</span><span class="sxs-lookup"><span data-stu-id="951a1-122">Example 1: Remove the local computer from its domain</span></span>

<span data-ttu-id="951a1-123">В этом примере удаляется локальный компьютер из домена, к которому он присоединен.</span><span class="sxs-lookup"><span data-stu-id="951a1-123">This example removes the local computer from the domain to which it is joined.</span></span>

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

<span data-ttu-id="951a1-124">Параметр **унжоиндомаинкредентиал** предоставляет учетные данные администратора домена.</span><span class="sxs-lookup"><span data-stu-id="951a1-124">The **UnjoinDomainCredential** parameter provides the credentials of a domain administrator.</span></span> <span data-ttu-id="951a1-125">В общих параметрах **PassThru** и **verbose** отображаются сведения об успешном или неуспешном выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="951a1-125">The **PassThru** and the **Verbose** common parameters display information about the success or failure of the command.</span></span> <span data-ttu-id="951a1-126">Параметр **перезапуска** перезапускает компьютер для завершения операции удаления.</span><span class="sxs-lookup"><span data-stu-id="951a1-126">The **Restart** parameter restarts the computer to complete the remove operation.</span></span>

<span data-ttu-id="951a1-127">Если имя рабочей группы не указано, компьютер перемещается в рабочую группу с именем после удаления из домена.</span><span class="sxs-lookup"><span data-stu-id="951a1-127">When no workgroup name is specified, the computer is moved to the workgroup named after it is removed from its domain.</span></span>

### <span data-ttu-id="951a1-128">Пример 2. Перемещение нескольких компьютеров в устаревшую рабочую группу</span><span class="sxs-lookup"><span data-stu-id="951a1-128">Example 2: Move several computers to a legacy workgroup</span></span>

<span data-ttu-id="951a1-129">Этот пример удаляет все компьютеры, перечисленные в `OldServers.txt` файле, из их доменов и перемещает их в **устаревшую** рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="951a1-129">This example removes all the computers listed in the `OldServers.txt` file from their domains and moves them into the **Legacy** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

<span data-ttu-id="951a1-130">Параметр **локалкредентиал** предоставляет учетные данные пользователя, имеющего разрешение на подключение к удаленным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="951a1-130">The **LocalCredential** parameter provides the credentials of a user who has permission to connect to remote computers.</span></span> <span data-ttu-id="951a1-131">Параметр **унжоиндомаинкредентиал** предоставляет учетные данные пользователя, имеющего разрешение на удаление компьютеров из их доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-131">The **UnjoinDomainCredential** parameter provides the credentials of a user who has permission to remove the computers from their domains.</span></span> <span data-ttu-id="951a1-132">Параметр **Force** подавляет запросы на подтверждение для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="951a1-132">The **Force** parameter suppresses the confirmation prompts for each computer.</span></span> <span data-ttu-id="951a1-133">Параметр **перезапуска** перезапускает все компьютеры после удаления из своего домена.</span><span class="sxs-lookup"><span data-stu-id="951a1-133">The **Restart** parameter restarts each of the computers after it is removed from its domain.</span></span>

### <span data-ttu-id="951a1-134">Пример 3. Удаление компьютеров из рабочей группы без подтверждения</span><span class="sxs-lookup"><span data-stu-id="951a1-134">Example 3: Remove computers from a workgroup without confirmation</span></span>

<span data-ttu-id="951a1-135">В этом примере удаляется удаленный компьютер, Server01 и локальный компьютер из своих доменов, а затем они добавляются в **локальную** рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="951a1-135">This example removes the remote computer, Server01, and the local computer from their domains and adds them to the **Local** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

<span data-ttu-id="951a1-136">Параметр **Force** подавляет запрос на подтверждение для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="951a1-136">The **Force** parameter suppresses the confirmation prompt for each computer.</span></span> <span data-ttu-id="951a1-137">Параметр **перезапуска** перезапускает компьютеры, чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="951a1-137">The **Restart** parameter restarts the computers to make the change effective.</span></span>

## <span data-ttu-id="951a1-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="951a1-138">PARAMETERS</span></span>

### <span data-ttu-id="951a1-139">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="951a1-139">-ComputerName</span></span>

<span data-ttu-id="951a1-140">Указывает компьютеры, удаляемые из своих доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-140">Specifies the computers to be removed from their domains.</span></span> <span data-ttu-id="951a1-141">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="951a1-141">The default is the local computer.</span></span>

<span data-ttu-id="951a1-142">Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="951a1-142">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of the remote computers.</span></span> <span data-ttu-id="951a1-143">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="951a1-143">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="951a1-144">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="951a1-144">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="951a1-145">Параметр **ComputerName** можно использовать, `Remove-Computer` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="951a1-145">You can use the **ComputerName** parameter of `Remove-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="951a1-146">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="951a1-146">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="951a1-147">-Force</span><span class="sxs-lookup"><span data-stu-id="951a1-147">-Force</span></span>

<span data-ttu-id="951a1-148">Скрывает запрос к пользователю.</span><span class="sxs-lookup"><span data-stu-id="951a1-148">Suppresses the user prompt.</span></span> <span data-ttu-id="951a1-149">По умолчанию `Remove-Computer` запрашивает подтверждение перед удалением каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="951a1-149">By default, `Remove-Computer` prompts you for confirmation before removing each computer.</span></span>

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

### <span data-ttu-id="951a1-150">-Локалкредентиал</span><span class="sxs-lookup"><span data-stu-id="951a1-150">-LocalCredential</span></span>

<span data-ttu-id="951a1-151">Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютерам, указанному параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="951a1-151">Specifies a user account that has permission to connect to the computers that the **ComputerName** parameter specifies.</span></span> <span data-ttu-id="951a1-152">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="951a1-152">The default is the current user.</span></span>

<span data-ttu-id="951a1-153">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="951a1-153">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="951a1-154">При вводе имени пользователя командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="951a1-154">If you type a user name, the cmdlet prompts you for a password.</span></span> <span data-ttu-id="951a1-155">Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютера из текущего домена, используйте параметр **UnjoinDomainCredential** .</span><span class="sxs-lookup"><span data-stu-id="951a1-155">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="951a1-156">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="951a1-156">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="951a1-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="951a1-157">-PassThru</span></span>

<span data-ttu-id="951a1-158">Возвращает результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="951a1-158">Returns the results of the command.</span></span> <span data-ttu-id="951a1-159">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="951a1-159">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="951a1-160">-Restart</span><span class="sxs-lookup"><span data-stu-id="951a1-160">-Restart</span></span>

<span data-ttu-id="951a1-161">Указывает, что этот командлет перезапускает удаляемые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="951a1-161">Indicates that this cmdlet restarts the computers that are being removed.</span></span> <span data-ttu-id="951a1-162">Чтобы изменения вступили в силу, часто требуется перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="951a1-162">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="951a1-163">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="951a1-163">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="951a1-164">-Унжоиндомаинкредентиал</span><span class="sxs-lookup"><span data-stu-id="951a1-164">-UnjoinDomainCredential</span></span>

<span data-ttu-id="951a1-165">Указывает учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущих доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-165">Specifies a user account that has permission to remove the computers from their current domains.</span></span>
<span data-ttu-id="951a1-166">Требуются явные учетные данные, как указано в этом параметре, для удаления удаленных компьютеров из домена, даже если это учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="951a1-166">Explicit credentials, as provided by this parameter, are required to remove remote computers from a domain, even when the value is the credentials of the current user.</span></span>

<span data-ttu-id="951a1-167">Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="951a1-167">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by `Get-Credential`.</span></span> <span data-ttu-id="951a1-168">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="951a1-168">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="951a1-169">Чтобы указать учетную запись пользователя, имеющую разрешение на подключение к удаленным компьютерам, используйте параметр **LocalCredential** .</span><span class="sxs-lookup"><span data-stu-id="951a1-169">To specify a user account that has permission to connect to the remote computers, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="951a1-170">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="951a1-170">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="951a1-171">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="951a1-171">-WorkgroupName</span></span>

<span data-ttu-id="951a1-172">Указывает имя рабочей группы, в которую добавляются компьютеры после удаления из их доменов.</span><span class="sxs-lookup"><span data-stu-id="951a1-172">Specifies the name of a workgroup to which the computers are added when they are removed from their domains.</span></span> <span data-ttu-id="951a1-173">Значение по умолчанию — **Workgroup** .</span><span class="sxs-lookup"><span data-stu-id="951a1-173">The default value is **WORKGROUP** .</span></span> <span data-ttu-id="951a1-174">При удалении компьютера из домена необходимо добавить его в рабочую группу.</span><span class="sxs-lookup"><span data-stu-id="951a1-174">When you remove a computer from a domain, you must add it to a workgroup.</span></span>

<span data-ttu-id="951a1-175">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="951a1-175">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="951a1-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="951a1-176">-Confirm</span></span>

<span data-ttu-id="951a1-177">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="951a1-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="951a1-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="951a1-178">-WhatIf</span></span>

<span data-ttu-id="951a1-179">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="951a1-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="951a1-180">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="951a1-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="951a1-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="951a1-181">CommonParameters</span></span>

<span data-ttu-id="951a1-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="951a1-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="951a1-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="951a1-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="951a1-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="951a1-184">INPUTS</span></span>

### <span data-ttu-id="951a1-185">System.String</span><span class="sxs-lookup"><span data-stu-id="951a1-185">System.String</span></span>

<span data-ttu-id="951a1-186">Имена компьютеров можно передать в сискмдлет.</span><span class="sxs-lookup"><span data-stu-id="951a1-186">You can pipe computer names to thiscmdlet.</span></span>

## <span data-ttu-id="951a1-187">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="951a1-187">OUTPUTS</span></span>

### <span data-ttu-id="951a1-188">Microsoft. PowerShell. Commands. Компутерчанжеинфо</span><span class="sxs-lookup"><span data-stu-id="951a1-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="951a1-189">При использовании параметра **PassThru** `Remove-Computer` возвращает объект **компутерчанжеинфо** .</span><span class="sxs-lookup"><span data-stu-id="951a1-189">When you use the **PassThru** parameter, `Remove-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="951a1-190">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="951a1-190">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="951a1-191">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="951a1-191">NOTES</span></span>

<span data-ttu-id="951a1-192">Этот командлет не удаляет компьютеры из рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="951a1-192">This cmdlet does not remove computers from workgroups.</span></span>

## <span data-ttu-id="951a1-193">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="951a1-193">RELATED LINKS</span></span>

[<span data-ttu-id="951a1-194">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-194">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="951a1-195">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-195">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="951a1-196">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-196">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="951a1-197">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-197">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="951a1-198">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-198">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="951a1-199">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-199">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="951a1-200">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="951a1-200">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="951a1-201">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="951a1-201">Test-Connection</span></span>](Test-Connection.md)
