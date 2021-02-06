---
description: Описание выполнения удаленных команд в PowerShell.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: b47efbaaebdd75be5f15be449e194113a0d6ebd7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602842"
---
# <a name="about-remote"></a><span data-ttu-id="ad516-103">Об удаленной</span><span class="sxs-lookup"><span data-stu-id="ad516-103">About Remote</span></span>

## <a name="short-description"></a><span data-ttu-id="ad516-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ad516-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ad516-105">Описание выполнения удаленных команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad516-105">Describes how to run remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ad516-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ad516-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ad516-107">Удаленные команды можно выполнять на одном компьютере или на нескольких компьютерах, используя временное или постоянное подключение.</span><span class="sxs-lookup"><span data-stu-id="ad516-107">You can run remote commands on a single computer or on multiple computers by using a temporary or persistent connection.</span></span> <span data-ttu-id="ad516-108">Можно также запустить интерактивный сеанс с одним удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ad516-108">You can also start an interactive session with a single remote computer.</span></span>

<span data-ttu-id="ad516-109">В этом разделе приводится ряд примеров, демонстрирующих выполнение различных типов удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="ad516-109">This topic provides a series of examples to show you how to run different types of remote command.</span></span> <span data-ttu-id="ad516-110">После выполнения этих основных команд ознакомьтесь с разделами справки, описывающими каждый командлет, используемый в этих командах.</span><span class="sxs-lookup"><span data-stu-id="ad516-110">After you try these basic commands, read the Help topics that describe each cmdlet that is used in these commands.</span></span> <span data-ttu-id="ad516-111">В этих разделах содержатся сведения и объясняется, как можно изменить команды в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="ad516-111">The topics provide the details and explain how you can modify the commands to meet your needs.</span></span>

<span data-ttu-id="ad516-112">Примечание. чтобы использовать удаленное взаимодействие PowerShell, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="ad516-112">Note: To use PowerShell remoting, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="ad516-113">Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-113">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="how-to-start-an-interactive-session-enter-pssession"></a><span data-ttu-id="ad516-114">КАК ЗАПУСТИТЬ ИНТЕРАКТИВНЫЙ СЕАНС (ENTER-PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="ad516-114">HOW TO START AN INTERACTIVE SESSION (ENTER-PSSESSION)</span></span>

<span data-ttu-id="ad516-115">Самый простой способ запуска удаленных команд — запустить интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ad516-115">The easiest way to run remote commands is to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="ad516-116">При запуске сеанса команды, которые вы вводите, выполняются на удаленном компьютере, точно так же, как если бы они были введены непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad516-116">When the session starts, the commands that you type run on the remote computer, just as though you typed them directly on the remote computer.</span></span> <span data-ttu-id="ad516-117">В каждом интерактивном сеансе можно подключиться только к одному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ad516-117">You can connect to only one computer in each interactive session.</span></span>

<span data-ttu-id="ad516-118">Чтобы запустить интерактивный сеанс, используйте командлет Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-118">To start an interactive session, use the Enter-PSSession cmdlet.</span></span> <span data-ttu-id="ad516-119">Следующая команда запускает интерактивный сеанс с компьютером Server01:</span><span class="sxs-lookup"><span data-stu-id="ad516-119">The following command starts an interactive session with the Server01 computer:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="ad516-120">Командная строка изменится, указывая, что вы подключены к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="ad516-120">The command prompt changes to indicate that you are connected to the Server01 computer.</span></span>

```
Server01\PS>
```

<span data-ttu-id="ad516-121">Теперь можно ввести команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ad516-121">Now, you can type commands on the Server01 computer.</span></span>

<span data-ttu-id="ad516-122">Чтобы завершить интерактивный сеанс, введите:</span><span class="sxs-lookup"><span data-stu-id="ad516-122">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="ad516-123">Дополнительные сведения см. в разделе Ввод-PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-123">For more information, see Enter-PSSession.</span></span>

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a><span data-ttu-id="ad516-124">ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТОВ С ПАРАМЕТРОМ COMPUTERNAME ДЛЯ ПОЛУЧЕНИЯ УДАЛЕННЫХ ДАННЫХ</span><span class="sxs-lookup"><span data-stu-id="ad516-124">HOW TO USE CMDLETS THAT HAVE A COMPUTERNAME PARAMETER TO GET REMOTE DATA</span></span>

<span data-ttu-id="ad516-125">Несколько командлетов имеют параметр ComputerName, позволяющий получать объекты с удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="ad516-125">Several cmdlets have a ComputerName parameter that lets you get objects from remote computers.</span></span>

<span data-ttu-id="ad516-126">Поскольку эти командлеты не используют удаленное взаимодействие PowerShell на основе WS-Management, можно использовать параметр ComputerName этих командлетов на любом компьютере с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad516-126">Because these cmdlets do not use WS-Management-based PowerShell remoting, you can use the ComputerName parameter of these cmdlets on any computer that is running PowerShell.</span></span> <span data-ttu-id="ad516-127">Компьютеры не обязательно должны быть настроены для удаленного взаимодействия PowerShell, и компьютеры не должны отвечать требованиям к системе для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ad516-127">The computers do not have to be configured for PowerShell remoting, and the computers do not have to meet the system requirements for remoting.</span></span>

<span data-ttu-id="ad516-128">Следующие командлеты имеют параметр ComputerName:</span><span class="sxs-lookup"><span data-stu-id="ad516-128">The following cmdlets have a ComputerName parameter:</span></span>

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

<span data-ttu-id="ad516-129">Например, следующая команда получает службы на удаленном компьютере Server01:</span><span class="sxs-lookup"><span data-stu-id="ad516-129">For example, the following command gets the services on the Server01 remote computer:</span></span>

```powershell
Get-Service -ComputerName Server01
```

<span data-ttu-id="ad516-130">Как правило, командлеты, поддерживающие удаленное взаимодействие без специальной настройки, имеют параметр **ComputerName** и не имеют параметра **сеанса** .</span><span class="sxs-lookup"><span data-stu-id="ad516-130">Typically, cmdlets that support remoting without special configuration have a **ComputerName** parameter and do not have a **Session** parameter.</span></span> <span data-ttu-id="ad516-131">Чтобы найти эти командлеты в сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="ad516-131">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a><span data-ttu-id="ad516-132">ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ</span><span class="sxs-lookup"><span data-stu-id="ad516-132">HOW TO RUN A REMOTE COMMAND</span></span>

<span data-ttu-id="ad516-133">Чтобы выполнить другие команды на удаленных компьютерах, используйте командлет Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="ad516-133">To run other commands on remote computers, use the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="ad516-134">Чтобы выполнить одну команду или несколько несвязанных команд, используйте параметр ComputerName параметра Invoke-Command, чтобы указать удаленные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="ad516-134">To run a single command or a few unrelated commands, use the ComputerName parameter of Invoke-Command to specify the remote computers.</span></span> <span data-ttu-id="ad516-135">Используйте параметр ScriptBlock для указания команды.</span><span class="sxs-lookup"><span data-stu-id="ad516-135">Use the ScriptBlock parameter to specify the command.</span></span>

<span data-ttu-id="ad516-136">Например, следующая команда выполняет команду Get-Culture на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ad516-136">For example, the following command runs a Get-Culture command on the Server01 computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="ad516-137">Параметр ComputerName предназначен для ситуации, когда на одном или нескольких компьютерах выполняется одна команда или несколько несвязанных команд.</span><span class="sxs-lookup"><span data-stu-id="ad516-137">The ComputerName parameter is designed for situation in which you run a single command or several unrelated commands on one or many computers.</span></span> <span data-ttu-id="ad516-138">Чтобы установить постоянное подключение к удаленному компьютеру, используйте параметр Session.</span><span class="sxs-lookup"><span data-stu-id="ad516-138">To establish a persistent connection to a remote computer, use the Session parameter.</span></span>

## <a name="how-to-create-a-persistent-connection-pssession"></a><span data-ttu-id="ad516-139">СОЗДАНИЕ ПОСТОЯННОГО ПОДКЛЮЧЕНИЯ (PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="ad516-139">HOW TO CREATE A PERSISTENT CONNECTION (PSSESSION)</span></span>

<span data-ttu-id="ad516-140">При использовании параметра ComputerName командлета Invoke-Command Windows PowerShell устанавливает соединение только для команды.</span><span class="sxs-lookup"><span data-stu-id="ad516-140">When you use the ComputerName parameter of the Invoke-Command cmdlet, Windows PowerShell establishes a connection just for the command.</span></span> <span data-ttu-id="ad516-141">Затем по завершении команды она закрывает подключение.</span><span class="sxs-lookup"><span data-stu-id="ad516-141">Then, it closes the connection when the command is complete.</span></span> <span data-ttu-id="ad516-142">Все переменные или функции, определенные в команде, теряются.</span><span class="sxs-lookup"><span data-stu-id="ad516-142">Any variables or functions that are defined in the command are lost.</span></span>

<span data-ttu-id="ad516-143">Чтобы создать постоянное подключение к удаленному компьютеру, используйте командлет New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-143">To create a persistent connection to a remote computer, use the New-PSSession cmdlet.</span></span> <span data-ttu-id="ad516-144">Например, следующая команда создает PSSession на компьютерах Server01 и Server02, а затем сохраняет PSSession в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="ad516-144">For example, the following command creates PSSessions on the Server01 and Server02 computers and then saves the PSSessions in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="ad516-145">ВЫПОЛНЕНИЕ КОМАНД В PSSESSION</span><span class="sxs-lookup"><span data-stu-id="ad516-145">HOW TO RUN COMMANDS IN A PSSESSION</span></span>

<span data-ttu-id="ad516-146">С помощью PSSession можно выполнять ряд удаленных команд, которые совместно используют данные, такие как функции, псевдонимы и значения переменных.</span><span class="sxs-lookup"><span data-stu-id="ad516-146">With a PSSession, you can run a series of remote commands that share data, like functions, aliases, and the values of variables.</span></span> <span data-ttu-id="ad516-147">Для выполнения команд в PSSession используйте параметр Session командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="ad516-147">To run commands in a PSSession, use the Session parameter of the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="ad516-148">Например, следующая команда использует командлет Invoke-Command для выполнения команды Get-Process в PSSession на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="ad516-148">For example, the following command uses the Invoke-Command cmdlet to run a Get-Process command in the PSSessions on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="ad516-149">Команда сохраняет процессы в переменной $p в каждом сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-149">The command saves the processes in a $p variable in each PSSession.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

<span data-ttu-id="ad516-150">Так как сеанс PSSession использует постоянное подключение, можно выполнить другую команду в том же сеансе PSSession, который использует переменную $p.</span><span class="sxs-lookup"><span data-stu-id="ad516-150">Because the PSSession uses a persistent connection, you can run another command in the same PSSession that uses the $p variable.</span></span> <span data-ttu-id="ad516-151">Следующая команда подсчитывает количество процессов, сохраненных в $p.</span><span class="sxs-lookup"><span data-stu-id="ad516-151">The following command counts the number of processes saved in $p.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a><span data-ttu-id="ad516-152">ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ НА НЕСКОЛЬКИХ КОМПЬЮТЕРАХ</span><span class="sxs-lookup"><span data-stu-id="ad516-152">HOW TO RUN A REMOTE COMMAND ON MULTIPLE COMPUTERS</span></span>

<span data-ttu-id="ad516-153">Чтобы выполнить удаленную команду на нескольких компьютерах, введите все имена компьютеров в значении параметра ComputerName команды Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="ad516-153">To run a remote command on multiple computers, type all of the computer names in the value of the ComputerName parameter of Invoke-Command.</span></span> <span data-ttu-id="ad516-154">Разделяйте имена запятыми.</span><span class="sxs-lookup"><span data-stu-id="ad516-154">Separate the names with commas.</span></span>

<span data-ttu-id="ad516-155">Например, следующая команда выполняет команду Get-Culture на трех компьютерах:</span><span class="sxs-lookup"><span data-stu-id="ad516-155">For example, the following command runs a Get-Culture command on three computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="ad516-156">Можно также выполнить команду в нескольких PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-156">You can also run a command in multiple PSSessions.</span></span> <span data-ttu-id="ad516-157">Следующие команды создают PSSession на компьютерах Server01, Server02 и Server03, а затем выполняют Get-Cultureную команду в каждом из PSSession.</span><span class="sxs-lookup"><span data-stu-id="ad516-157">The following commands create PSSessions on the Server01, Server02, and Server03 computers and then run a Get-Culture command in each of the PSSessions.</span></span>

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="ad516-158">Чтобы включить список компьютеров локального компьютера, введите имя локального компьютера, введите точку (.) или введите localhost.</span><span class="sxs-lookup"><span data-stu-id="ad516-158">To include the local computer list of computers, type the name of the local computer, type a dot (.), or type  "localhost".</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a><span data-ttu-id="ad516-159">ЗАПУСК СЦЕНАРИЯ НА УДАЛЕННЫХ КОМПЬЮТЕРАХ</span><span class="sxs-lookup"><span data-stu-id="ad516-159">HOW TO RUN A SCRIPT ON REMOTE COMPUTERS</span></span>

<span data-ttu-id="ad516-160">Чтобы запустить локальный скрипт на удаленных компьютерах, используйте параметр FilePath командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="ad516-160">To run a local script on remote computers, use the FilePath parameter of Invoke-Command.</span></span>

<span data-ttu-id="ad516-161">Например, следующая команда запускает сценарий Sample.ps1 на компьютерах S1 и S2:</span><span class="sxs-lookup"><span data-stu-id="ad516-161">For example, the following command runs the Sample.ps1 script on the S1 and S2 computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

<span data-ttu-id="ad516-162">Результаты сценария возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="ad516-162">The results of the script are returned to the local computer.</span></span> <span data-ttu-id="ad516-163">Нет необходимости копировать файлы.</span><span class="sxs-lookup"><span data-stu-id="ad516-163">You do not need to copy any files.</span></span>

## <a name="how-to-stop-a-remote-command"></a><span data-ttu-id="ad516-164">КАК ПРЕРЫВАТЬ УДАЛЕННУЮ КОМАНДУ</span><span class="sxs-lookup"><span data-stu-id="ad516-164">HOW TO STOP A REMOTE COMMAND</span></span>

<span data-ttu-id="ad516-165">Чтобы прервать выполнение команды, нажмите клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="ad516-165">To interrupt a command, press CTRL+C.</span></span> <span data-ttu-id="ad516-166">Запрос на прерывание передается на удаленный компьютер, на котором завершается Удаленная команда.</span><span class="sxs-lookup"><span data-stu-id="ad516-166">The interrupt request is passed to the remote computer where it terminates the remote command.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="ad516-167">ДОПОЛНИТЕЛЬНЫЕ СВЕДЕНИЯ</span><span class="sxs-lookup"><span data-stu-id="ad516-167">FOR MORE INFORMATION</span></span>

- <span data-ttu-id="ad516-168">Сведения о требованиях к системе для удаленного взаимодействия см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-168">For information about the system requirements for remoting, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

- <span data-ttu-id="ad516-169">Справку по форматированию удаленных выходных данных см. в разделе [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-169">For help in formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

- <span data-ttu-id="ad516-170">Сведения о принципах работы удаленного взаимодействия, об управлении удаленными данными, специальных конфигурациях, проблемах безопасности и других часто задаваемых вопросах см. в разделе [about_Remote_FAQ](about_Remote_FAQ.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-170">For information about how remoting works, how to manage remote data, special configurations, security issues, and other frequently asked questions, see [about_Remote_FAQ](about_Remote_FAQ.md).</span></span>

- <span data-ttu-id="ad516-171">Дополнительные сведения об устранении ошибок удаленного взаимодействия см. в разделе about_Remote_Troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="ad516-171">For help in resolving remoting errors, see about_Remote_Troubleshooting.</span></span>

- <span data-ttu-id="ad516-172">Дополнительные сведения о PSSession и постоянных подключениях см. в разделе [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-172">For information about PSSessions and persistent connections, see [about_PSSessions](about_PSSessions.md).</span></span>

- <span data-ttu-id="ad516-173">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ad516-173">For information about PowerShell background jobs, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="ad516-174">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="ad516-174">KEYWORDS</span></span>

<span data-ttu-id="ad516-175">about_Remoting</span><span class="sxs-lookup"><span data-stu-id="ad516-175">about_Remoting</span></span>

## <a name="see-also"></a><span data-ttu-id="ad516-176">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ad516-176">SEE ALSO</span></span>

[<span data-ttu-id="ad516-177">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="ad516-177">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="ad516-178">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="ad516-178">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="ad516-179">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="ad516-179">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="ad516-180">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="ad516-180">about_Remote_FAQ</span></span>](about_Remote_FAQ.md)

[<span data-ttu-id="ad516-181">about_Remote_TroubleShooting</span><span class="sxs-lookup"><span data-stu-id="ad516-181">about_Remote_TroubleShooting</span></span>](about_Remote_TroubleShooting.md)

[<span data-ttu-id="ad516-182">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="ad516-182">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="ad516-183">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="ad516-183">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="ad516-184">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ad516-184">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="ad516-185">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="ad516-185">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

