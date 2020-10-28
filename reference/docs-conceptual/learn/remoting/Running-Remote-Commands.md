---
ms.date: 08/21/2020
keywords: powershell,командлет
title: Выполнение удаленных команд
description: Описываются способы выполнения команд в удаленных системах с помощью PowerShell.
ms.openlocfilehash: e9e07fec96cbd93d3bf06be2a1f98ec7aa7d8f19
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501360"
---
# <a name="running-remote-commands"></a><span data-ttu-id="8eab8-104">Выполнение удаленных команд</span><span class="sxs-lookup"><span data-stu-id="8eab8-104">Running Remote Commands</span></span>

<span data-ttu-id="8eab8-105">Одна команда Windows PowerShell позволяет запускать команды на одном или сотнях компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8eab8-105">You can run commands on one or hundreds of computers with a single PowerShell command.</span></span> <span data-ttu-id="8eab8-106">Windows PowerShell поддерживает удаленное вычисление с помощью разных технологий, включая WMI, RPC и WS-Management.</span><span class="sxs-lookup"><span data-stu-id="8eab8-106">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

<span data-ttu-id="8eab8-107">PowerShell Core поддерживает инструментарий WMI, WS-Management и удаленное взаимодействие через SSH.</span><span class="sxs-lookup"><span data-stu-id="8eab8-107">PowerShell Core supports WMI, WS-Management, and SSH remoting.</span></span> <span data-ttu-id="8eab8-108">В PowerShell 6 RPC больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8eab8-108">In PowerShell 6, RPC is no longer supported.</span></span> <span data-ttu-id="8eab8-109">В PowerShell 7 и более поздних версиях RPC поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="8eab8-109">In PowerShell 7 and above, RPC is supported only in Windows.</span></span>

<span data-ttu-id="8eab8-110">Дополнительные сведения об удаленном взаимодействии в PowerShell Core см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="8eab8-110">For more information about remoting in PowerShell Core, see the following articles:</span></span>

- <span data-ttu-id="8eab8-111">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="8eab8-111">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="8eab8-112">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="8eab8-112">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="windows-powershell-remoting-without-configuration"></a><span data-ttu-id="8eab8-113">Удаленное взаимодействие с Windows PowerShell без настройки</span><span class="sxs-lookup"><span data-stu-id="8eab8-113">Windows PowerShell Remoting Without Configuration</span></span>

<span data-ttu-id="8eab8-114">Многие командлеты Windows PowerShell имеют параметр ComputerName, который позволяет собирать данные и изменять параметры одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8eab8-114">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="8eab8-115">Эти командлеты используют разные протоколы связи и работают во всех операционных системах Windows без специальной настройки.</span><span class="sxs-lookup"><span data-stu-id="8eab8-115">These cmdlets use varying communication protocols and work on all Windows operating systems without any special configuration.</span></span>

<span data-ttu-id="8eab8-116">В эти командлеты входят следующие:</span><span class="sxs-lookup"><span data-stu-id="8eab8-116">These cmdlets include:</span></span>

- [<span data-ttu-id="8eab8-117">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8eab8-117">Restart-Computer</span></span>](/powershell/module/microsoft.powershell.management/restart-computer)
- [<span data-ttu-id="8eab8-118">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="8eab8-118">Test-Connection</span></span>](/powershell/module/microsoft.powershell.management/test-connection)
- [<span data-ttu-id="8eab8-119">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="8eab8-119">Clear-EventLog</span></span>](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [<span data-ttu-id="8eab8-120">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="8eab8-120">Get-EventLog</span></span>](/powershell/module/microsoft.powershell.management/get-eventlog)
- [<span data-ttu-id="8eab8-121">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="8eab8-121">Get-HotFix</span></span>](/powershell/module/microsoft.powershell.management/get-hotfix)
- [<span data-ttu-id="8eab8-122">Get-Process</span><span class="sxs-lookup"><span data-stu-id="8eab8-122">Get-Process</span></span>](/powershell/module/microsoft.powershell.management/get-process)
- [<span data-ttu-id="8eab8-123">Get-Service</span><span class="sxs-lookup"><span data-stu-id="8eab8-123">Get-Service</span></span>](/powershell/module/microsoft.powershell.management/get-service)
- [<span data-ttu-id="8eab8-124">Set-Service</span><span class="sxs-lookup"><span data-stu-id="8eab8-124">Set-Service</span></span>](/powershell/module/microsoft.powershell.management/set-service)
- [<span data-ttu-id="8eab8-125">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="8eab8-125">Get-WinEvent</span></span>](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [<span data-ttu-id="8eab8-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="8eab8-126">Get-WmiObject</span></span>](/powershell/module/microsoft.powershell.management/get-wmiobject)

<span data-ttu-id="8eab8-127">Обычно командлеты, которые поддерживают удаленное взаимодействие без специальной настройки, имеют параметр ComputerName, но не имеют параметра Session.</span><span class="sxs-lookup"><span data-stu-id="8eab8-127">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and don't have the Session parameter.</span></span> <span data-ttu-id="8eab8-128">Чтобы найти эти командлеты в сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="8eab8-128">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="8eab8-129">Служба удаленного взаимодействия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8eab8-129">Windows PowerShell Remoting</span></span>

<span data-ttu-id="8eab8-130">Благодаря использованию протокола WS-Management служба удаленного взаимодействия Windows PowerShell позволяет запустить любую команду Windows PowerShell на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8eab8-130">Using the WS-Management protocol, Windows PowerShell remoting lets you run any Windows PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="8eab8-131">Вы можете устанавливать постоянные подключения, запускать интерактивные сеансы и выполнять скрипты на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8eab8-131">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

<span data-ttu-id="8eab8-132">Чтобы использовать службу удаленного взаимодействия Windows PowerShell, удаленный компьютер должен быть настроен для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="8eab8-132">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="8eab8-133">Дополнительные сведения, в том числе инструкции, см. в разделе [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span><span class="sxs-lookup"><span data-stu-id="8eab8-133">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="8eab8-134">После настройки службы удаленного взаимодействия Windows PowerShell вы получите доступ ко многим стратегиям удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8eab8-134">Once you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span>
<span data-ttu-id="8eab8-135">В этой статье перечислены только некоторые из них.</span><span class="sxs-lookup"><span data-stu-id="8eab8-135">This article lists just a few of them.</span></span> <span data-ttu-id="8eab8-136">См. дополнительные сведения об [удаленном взаимодействии](/powershell/module/microsoft.powershell.core/about/about_remote).</span><span class="sxs-lookup"><span data-stu-id="8eab8-136">For more information, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="8eab8-137">Запуск интерактивного сеанса</span><span class="sxs-lookup"><span data-stu-id="8eab8-137">Start an Interactive Session</span></span>

<span data-ttu-id="8eab8-138">Чтобы запустить интерактивный сеанс с одним удаленным компьютером, используйте командлет [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="8eab8-138">To start an interactive session with a single remote computer, use the [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlet.</span></span> <span data-ttu-id="8eab8-139">Например, чтобы запустить интерактивный сеанс с удаленным компьютером Server01, введите:</span><span class="sxs-lookup"><span data-stu-id="8eab8-139">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="8eab8-140">В командной строке отобразится имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="8eab8-140">The command prompt changes to display the name of the remote computer.</span></span> <span data-ttu-id="8eab8-141">Все команды, введенные в командной строке, запускаются на удаленном компьютере, а результаты отображаются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8eab8-141">Any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="8eab8-142">Чтобы завершить интерактивный сеанс, введите:</span><span class="sxs-lookup"><span data-stu-id="8eab8-142">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="8eab8-143">См. дополнительные сведения о командлетах Enter-PSSession и Exit-PSSession:</span><span class="sxs-lookup"><span data-stu-id="8eab8-143">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see:</span></span>

- [<span data-ttu-id="8eab8-144">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="8eab8-144">Enter-PSSession</span></span>](/powershell/module/microsoft.powershell.core/enter-pssession)
- [<span data-ttu-id="8eab8-145">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="8eab8-145">Exit-PSSession</span></span>](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a><span data-ttu-id="8eab8-146">Выполнение удаленной команды</span><span class="sxs-lookup"><span data-stu-id="8eab8-146">Run a Remote Command</span></span>

<span data-ttu-id="8eab8-147">Чтобы выполнить команду на одном или нескольких компьютерах, используйте командлет [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="8eab8-147">To run a command on one or more computers, use the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span> <span data-ttu-id="8eab8-148">Например, чтобы выполнить команду [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) на удаленных компьютерах Server01 и Server02, введите:</span><span class="sxs-lookup"><span data-stu-id="8eab8-148">For example, to run a [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="8eab8-149">Выходные данные будут возвращены на ваш компьютер.</span><span class="sxs-lookup"><span data-stu-id="8eab8-149">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a><span data-ttu-id="8eab8-150">Запуск сценария</span><span class="sxs-lookup"><span data-stu-id="8eab8-150">Run a Script</span></span>

<span data-ttu-id="8eab8-151">Чтобы запустить скрипт на одном или нескольких удаленных компьютерах, используйте параметр FilePath командлета `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="8eab8-151">To run a script on one or many remote computers, use the FilePath parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="8eab8-152">Сценарий должен быть включен или доступен для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="8eab8-152">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="8eab8-153">Результаты будут возвращены на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8eab8-153">The results are returned to your local computer.</span></span>

<span data-ttu-id="8eab8-154">Например, следующая команда выполняет скрипт DiskCollect.ps1 на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="8eab8-154">For example, the following command runs the DiskCollect.ps1 script on the remote computers, Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="8eab8-155">Установка постоянного подключения</span><span class="sxs-lookup"><span data-stu-id="8eab8-155">Establish a Persistent Connection</span></span>

<span data-ttu-id="8eab8-156">Используйте командлет `New-PSSession` для создания постоянного сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8eab8-156">Use the `New-PSSession` cmdlet to create a persistent session on a remote computer.</span></span> <span data-ttu-id="8eab8-157">В следующем примере создаются удаленные сеансы на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="8eab8-157">The following example creates remote sessions on Server01 and Server02.</span></span> <span data-ttu-id="8eab8-158">Объекты сеанса хранятся в переменной `$s`.</span><span class="sxs-lookup"><span data-stu-id="8eab8-158">The session objects are stored in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="8eab8-159">После установки сеансов в них можно выполнить любую команду.</span><span class="sxs-lookup"><span data-stu-id="8eab8-159">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="8eab8-160">Так как сеансы являются постоянными, вы можете собирать данные из одной команды и использовать их в другой.</span><span class="sxs-lookup"><span data-stu-id="8eab8-160">And because the sessions are persistent, you can collect data from one command and use it in another command.</span></span>

<span data-ttu-id="8eab8-161">Например, следующая команда выполняет команду Get-Hotfix в сеансах в переменной $s и сохраняет результаты в переменной $h.</span><span class="sxs-lookup"><span data-stu-id="8eab8-161">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="8eab8-162">Переменная $h создается в каждом сеансе в переменной $s, но она не существует в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="8eab8-162">The $h variable is created in each of the sessions in $s, but it doesn't exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="8eab8-163">Теперь вы можете использовать данные в переменной `$h` с другими командами в том же сеансе.</span><span class="sxs-lookup"><span data-stu-id="8eab8-163">Now you can use the data in the `$h` variable with other commands in the same session.</span></span> <span data-ttu-id="8eab8-164">Результаты отобразятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8eab8-164">The results are displayed on the local computer.</span></span> <span data-ttu-id="8eab8-165">Пример:</span><span class="sxs-lookup"><span data-stu-id="8eab8-165">For example:</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="8eab8-166">Расширенная служба удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8eab8-166">Advanced Remoting</span></span>

<span data-ttu-id="8eab8-167">Это и есть служба удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8eab8-167">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="8eab8-168">Используя командлеты, установленные с Windows PowerShell, можно установить и настроить удаленные сеансы с локальных и удаленных компьютеров, создать настраиваемые и ограниченные сеансы, разрешить пользователям импортировать команды из удаленного сеанса, которые могут неявно выполняться в удаленном сеансе, настроить безопасность удаленного сеанса и многое другое.</span><span class="sxs-lookup"><span data-stu-id="8eab8-168">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="8eab8-169">Windows PowerShell включает поставщик WSMan.</span><span class="sxs-lookup"><span data-stu-id="8eab8-169">Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="8eab8-170">Поставщик создает диск `WSMAN:`, который позволяет перемещаться по иерархии параметров конфигурации на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8eab8-170">The provider creates a `WSMAN:` drive that lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>

<span data-ttu-id="8eab8-171">См. дополнительные сведения о [поставщике WSMan](https://technet.microsoft.com/library/dd819476.aspx) и [командлетах WS-Management](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets) или введите команду `Get-Help wsman` в консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8eab8-171">For more information about the WSMan provider, see [WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) and [About WS-Management Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets), or in the Windows PowerShell console, type `Get-Help wsman`.</span></span>

<span data-ttu-id="8eab8-172">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="8eab8-172">For more information, see:</span></span>

- [<span data-ttu-id="8eab8-173">Часто задаваемые вопросы об удаленном взаимодействии</span><span class="sxs-lookup"><span data-stu-id="8eab8-173">About Remote FAQ</span></span>](https://technet.microsoft.com/library/dd315359.aspx)
- [<span data-ttu-id="8eab8-174">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8eab8-174">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="8eab8-175">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="8eab8-175">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)

<span data-ttu-id="8eab8-176">Справку по ошибкам службы удаленного взаимодействия см. в разделе [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span><span class="sxs-lookup"><span data-stu-id="8eab8-176">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="8eab8-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="8eab8-177">See Also</span></span>

- [<span data-ttu-id="8eab8-178">about_Remote</span><span class="sxs-lookup"><span data-stu-id="8eab8-178">about_Remote</span></span>](https://technet.microsoft.com/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="8eab8-179">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="8eab8-179">about_Remote_FAQ</span></span>](https://technet.microsoft.com/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="8eab8-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="8eab8-180">about_Remote_Requirements</span></span>](https://technet.microsoft.com/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="8eab8-181">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="8eab8-181">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="8eab8-182">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="8eab8-182">about_PSSessions</span></span>](https://technet.microsoft.com/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="8eab8-183">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8eab8-183">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="8eab8-184">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8eab8-184">Invoke-Command</span></span>](/powershell/module/microsoft.powershell.core/invoke-command)
- [<span data-ttu-id="8eab8-185">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="8eab8-185">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)
- [<span data-ttu-id="8eab8-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="8eab8-186">New-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821498)
- [<span data-ttu-id="8eab8-187">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8eab8-187">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="8eab8-188">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="8eab8-188">WSMan Provider</span></span>](https://technet.microsoft.com/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
