---
ms.date: 08/21/2020
keywords: powershell,командлет
title: Выполнение удаленных команд
description: Описываются способы выполнения команд в удаленных системах с помощью PowerShell.
ms.openlocfilehash: cff18a4f51c3ed8e3ed2c1f35862a88911e7ceb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391414"
---
# <a name="running-remote-commands"></a><span data-ttu-id="3bc69-104">Выполнение удаленных команд</span><span class="sxs-lookup"><span data-stu-id="3bc69-104">Running Remote Commands</span></span>

<span data-ttu-id="3bc69-105">Одна команда Windows PowerShell позволяет запускать команды на одном или сотнях компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3bc69-105">You can run commands on one or hundreds of computers with a single PowerShell command.</span></span> <span data-ttu-id="3bc69-106">Windows PowerShell поддерживает удаленное вычисление с помощью разных технологий, включая WMI, RPC и WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3bc69-106">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

<span data-ttu-id="3bc69-107">PowerShell Core поддерживает инструментарий WMI, WS-Management и удаленное взаимодействие через SSH.</span><span class="sxs-lookup"><span data-stu-id="3bc69-107">PowerShell Core supports WMI, WS-Management, and SSH remoting.</span></span> <span data-ttu-id="3bc69-108">В PowerShell 6 RPC больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3bc69-108">In PowerShell 6, RPC is no longer supported.</span></span> <span data-ttu-id="3bc69-109">В PowerShell 7 и более поздних версиях RPC поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="3bc69-109">In PowerShell 7 and above, RPC is supported only in Windows.</span></span>

<span data-ttu-id="3bc69-110">Дополнительные сведения об удаленном взаимодействии в PowerShell Core см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3bc69-110">For more information about remoting in PowerShell Core, see the following articles:</span></span>

- <span data-ttu-id="3bc69-111">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="3bc69-111">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="3bc69-112">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="3bc69-112">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="windows-powershell-remoting-without-configuration"></a><span data-ttu-id="3bc69-113">Удаленное взаимодействие с Windows PowerShell без настройки</span><span class="sxs-lookup"><span data-stu-id="3bc69-113">Windows PowerShell Remoting Without Configuration</span></span>

<span data-ttu-id="3bc69-114">Многие командлеты Windows PowerShell имеют параметр ComputerName, который позволяет собирать данные и изменять параметры одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3bc69-114">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="3bc69-115">Эти командлеты используют разные протоколы связи и работают во всех операционных системах Windows без специальной настройки.</span><span class="sxs-lookup"><span data-stu-id="3bc69-115">These cmdlets use varying communication protocols and work on all Windows operating systems without any special configuration.</span></span>

<span data-ttu-id="3bc69-116">В эти командлеты входят следующие:</span><span class="sxs-lookup"><span data-stu-id="3bc69-116">These cmdlets include:</span></span>

- [<span data-ttu-id="3bc69-117">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3bc69-117">Restart-Computer</span></span>](/powershell/module/microsoft.powershell.management/restart-computer)
- [<span data-ttu-id="3bc69-118">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="3bc69-118">Test-Connection</span></span>](/powershell/module/microsoft.powershell.management/test-connection)
- [<span data-ttu-id="3bc69-119">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="3bc69-119">Clear-EventLog</span></span>](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [<span data-ttu-id="3bc69-120">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="3bc69-120">Get-EventLog</span></span>](/powershell/module/microsoft.powershell.management/get-eventlog)
- [<span data-ttu-id="3bc69-121">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="3bc69-121">Get-HotFix</span></span>](/powershell/module/microsoft.powershell.management/get-hotfix)
- [<span data-ttu-id="3bc69-122">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3bc69-122">Get-Process</span></span>](/powershell/module/microsoft.powershell.management/get-process)
- [<span data-ttu-id="3bc69-123">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3bc69-123">Get-Service</span></span>](/powershell/module/microsoft.powershell.management/get-service)
- [<span data-ttu-id="3bc69-124">Set-Service</span><span class="sxs-lookup"><span data-stu-id="3bc69-124">Set-Service</span></span>](/powershell/module/microsoft.powershell.management/set-service)
- [<span data-ttu-id="3bc69-125">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="3bc69-125">Get-WinEvent</span></span>](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [<span data-ttu-id="3bc69-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="3bc69-126">Get-WmiObject</span></span>](/powershell/module/microsoft.powershell.management/get-wmiobject)

<span data-ttu-id="3bc69-127">Обычно командлеты, которые поддерживают удаленное взаимодействие без специальной настройки, имеют параметр ComputerName, но не имеют параметра Session.</span><span class="sxs-lookup"><span data-stu-id="3bc69-127">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and don't have the Session parameter.</span></span> <span data-ttu-id="3bc69-128">Чтобы найти эти командлеты в сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="3bc69-128">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="3bc69-129">Служба удаленного взаимодействия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bc69-129">Windows PowerShell Remoting</span></span>

<span data-ttu-id="3bc69-130">Благодаря использованию протокола WS-Management служба удаленного взаимодействия Windows PowerShell позволяет запустить любую команду Windows PowerShell на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3bc69-130">Using the WS-Management protocol, Windows PowerShell remoting lets you run any Windows PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="3bc69-131">Вы можете устанавливать постоянные подключения, запускать интерактивные сеансы и выполнять скрипты на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3bc69-131">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

<span data-ttu-id="3bc69-132">Чтобы использовать службу удаленного взаимодействия Windows PowerShell, удаленный компьютер должен быть настроен для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="3bc69-132">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="3bc69-133">Дополнительные сведения, в том числе инструкции, см. в разделе [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span><span class="sxs-lookup"><span data-stu-id="3bc69-133">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="3bc69-134">После настройки службы удаленного взаимодействия Windows PowerShell вы получите доступ ко многим стратегиям удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3bc69-134">Once you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span>
<span data-ttu-id="3bc69-135">В этой статье перечислены только некоторые из них.</span><span class="sxs-lookup"><span data-stu-id="3bc69-135">This article lists just a few of them.</span></span> <span data-ttu-id="3bc69-136">См. дополнительные сведения об [удаленном взаимодействии](/powershell/module/microsoft.powershell.core/about/about_remote).</span><span class="sxs-lookup"><span data-stu-id="3bc69-136">For more information, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="3bc69-137">Запуск интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="3bc69-137">Start an Interactive Session</span></span>

<span data-ttu-id="3bc69-138">Чтобы запустить интерактивный сеанс с одним удаленным компьютером, используйте командлет [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="3bc69-138">To start an interactive session with a single remote computer, use the [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlet.</span></span> <span data-ttu-id="3bc69-139">Например, чтобы запустить интерактивный сеанс с удаленным компьютером Server01, введите:</span><span class="sxs-lookup"><span data-stu-id="3bc69-139">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="3bc69-140">В командной строке отобразится имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="3bc69-140">The command prompt changes to display the name of the remote computer.</span></span> <span data-ttu-id="3bc69-141">Все команды, введенные в командной строке, запускаются на удаленном компьютере, а результаты отображаются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bc69-141">Any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="3bc69-142">Чтобы завершить интерактивный сеанс, введите:</span><span class="sxs-lookup"><span data-stu-id="3bc69-142">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="3bc69-143">См. дополнительные сведения о командлетах Enter-PSSession и Exit-PSSession:</span><span class="sxs-lookup"><span data-stu-id="3bc69-143">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see:</span></span>

- [<span data-ttu-id="3bc69-144">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3bc69-144">Enter-PSSession</span></span>](/powershell/module/microsoft.powershell.core/enter-pssession)
- [<span data-ttu-id="3bc69-145">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="3bc69-145">Exit-PSSession</span></span>](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a><span data-ttu-id="3bc69-146">Выполнение удаленной команды</span><span class="sxs-lookup"><span data-stu-id="3bc69-146">Run a Remote Command</span></span>

<span data-ttu-id="3bc69-147">Чтобы выполнить команду на одном или нескольких компьютерах, используйте командлет [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="3bc69-147">To run a command on one or more computers, use the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span> <span data-ttu-id="3bc69-148">Например, чтобы выполнить команду [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) на удаленных компьютерах Server01 и Server02, введите:</span><span class="sxs-lookup"><span data-stu-id="3bc69-148">For example, to run a [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="3bc69-149">Выходные данные будут возвращены на ваш компьютер.</span><span class="sxs-lookup"><span data-stu-id="3bc69-149">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a><span data-ttu-id="3bc69-150">Запуск сценария</span><span class="sxs-lookup"><span data-stu-id="3bc69-150">Run a Script</span></span>

<span data-ttu-id="3bc69-151">Чтобы запустить скрипт на одном или нескольких удаленных компьютерах, используйте параметр FilePath командлета `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="3bc69-151">To run a script on one or many remote computers, use the FilePath parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="3bc69-152">Сценарий должен быть включен или доступен для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3bc69-152">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="3bc69-153">Результаты будут возвращены на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3bc69-153">The results are returned to your local computer.</span></span>

<span data-ttu-id="3bc69-154">Например, следующая команда выполняет скрипт DiskCollect.ps1 на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="3bc69-154">For example, the following command runs the DiskCollect.ps1 script on the remote computers, Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="3bc69-155">Установка постоянного подключения</span><span class="sxs-lookup"><span data-stu-id="3bc69-155">Establish a Persistent Connection</span></span>

<span data-ttu-id="3bc69-156">Используйте командлет `New-PSSession` для создания постоянного сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bc69-156">Use the `New-PSSession` cmdlet to create a persistent session on a remote computer.</span></span> <span data-ttu-id="3bc69-157">В следующем примере создаются удаленные сеансы на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="3bc69-157">The following example creates remote sessions on Server01 and Server02.</span></span> <span data-ttu-id="3bc69-158">Объекты сеанса хранятся в переменной `$s`.</span><span class="sxs-lookup"><span data-stu-id="3bc69-158">The session objects are stored in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="3bc69-159">После установки сеансов в них можно выполнить любую команду.</span><span class="sxs-lookup"><span data-stu-id="3bc69-159">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="3bc69-160">Так как сеансы являются постоянными, вы можете собирать данные из одной команды и использовать их в другой.</span><span class="sxs-lookup"><span data-stu-id="3bc69-160">And because the sessions are persistent, you can collect data from one command and use it in another command.</span></span>

<span data-ttu-id="3bc69-161">Например, следующая команда выполняет команду Get-Hotfix в сеансах в переменной $s и сохраняет результаты в переменной $h.</span><span class="sxs-lookup"><span data-stu-id="3bc69-161">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="3bc69-162">Переменная $h создается в каждом сеансе в переменной $s, но она не существует в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="3bc69-162">The $h variable is created in each of the sessions in $s, but it doesn't exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="3bc69-163">Теперь вы можете использовать данные в переменной `$h` с другими командами в том же сеансе.</span><span class="sxs-lookup"><span data-stu-id="3bc69-163">Now you can use the data in the `$h` variable with other commands in the same session.</span></span> <span data-ttu-id="3bc69-164">Результаты отобразятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bc69-164">The results are displayed on the local computer.</span></span> <span data-ttu-id="3bc69-165">Пример:</span><span class="sxs-lookup"><span data-stu-id="3bc69-165">For example:</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="3bc69-166">Расширенная служба удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="3bc69-166">Advanced Remoting</span></span>

<span data-ttu-id="3bc69-167">Это и есть служба удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bc69-167">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="3bc69-168">Используя командлеты, установленные с Windows PowerShell, можно установить и настроить удаленные сеансы с локальных и удаленных компьютеров, создать настраиваемые и ограниченные сеансы, разрешить пользователям импортировать команды из удаленного сеанса, которые могут неявно выполняться в удаленном сеансе, настроить безопасность удаленного сеанса и многое другое.</span><span class="sxs-lookup"><span data-stu-id="3bc69-168">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="3bc69-169">Windows PowerShell включает поставщик WSMan.</span><span class="sxs-lookup"><span data-stu-id="3bc69-169">Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="3bc69-170">Поставщик создает диск `WSMAN:`, который позволяет перемещаться по иерархии параметров конфигурации на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3bc69-170">The provider creates a `WSMAN:` drive that lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>

<span data-ttu-id="3bc69-171">См. дополнительные сведения о [поставщике WSMan](/powershell/module/microsoft.wsman.management/about/about_wsman_provider) и [командлетах WS-Management](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets) или введите команду `Get-Help wsman` в консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bc69-171">For more information about the WSMan provider, see [WSMan Provider](/powershell/module/microsoft.wsman.management/about/about_wsman_provider) and [About WS-Management Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets), or in the Windows PowerShell console, type `Get-Help wsman`.</span></span>

<span data-ttu-id="3bc69-172">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="3bc69-172">For more information, see:</span></span>

- [<span data-ttu-id="3bc69-173">Часто задаваемые вопросы об удаленном взаимодействии</span><span class="sxs-lookup"><span data-stu-id="3bc69-173">About Remote FAQ</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [<span data-ttu-id="3bc69-174">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bc69-174">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)
- [<span data-ttu-id="3bc69-175">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="3bc69-175">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

<span data-ttu-id="3bc69-176">Справку по ошибкам службы удаленного взаимодействия см. в разделе [about_Remote_Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_Remote_Troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="3bc69-176">For help with remoting errors, see [about_Remote_Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_Remote_Troubleshooting).</span></span>

## <a name="see-also"></a><span data-ttu-id="3bc69-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="3bc69-177">See Also</span></span>

- [<span data-ttu-id="3bc69-178">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3bc69-178">about_Remote</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [<span data-ttu-id="3bc69-179">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="3bc69-179">about_Remote_FAQ</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [<span data-ttu-id="3bc69-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="3bc69-180">about_Remote_Requirements</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)
- [<span data-ttu-id="3bc69-181">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="3bc69-181">about_Remote_Troubleshooting</span></span>](/powershell/module/microsoft.powershell.core/about/about_Remote_Troubleshooting)
- [<span data-ttu-id="3bc69-182">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3bc69-182">about_PSSessions</span></span>](/powershell/module/microsoft.powershell.core/about/about_PSSessions)
- [<span data-ttu-id="3bc69-183">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3bc69-183">about_WS-Management_Cmdlets</span></span>](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets)
- [<span data-ttu-id="3bc69-184">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3bc69-184">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="3bc69-185">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="3bc69-185">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)
- [<span data-ttu-id="3bc69-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3bc69-186">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="3bc69-187">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bc69-187">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)
- [<span data-ttu-id="3bc69-188">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="3bc69-188">WSMan Provider</span></span>](/powershell/module/microsoft.wsman.management/about/about_wsman_provider)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
