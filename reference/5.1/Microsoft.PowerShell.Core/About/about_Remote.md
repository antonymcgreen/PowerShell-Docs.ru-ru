---
description: Описание выполнения удаленных команд в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: ce75863c616bebcdb4a8273c287271b9feea3396
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232321"
---
# <a name="about-remote"></a><span data-ttu-id="3fa90-104">Об удаленной</span><span class="sxs-lookup"><span data-stu-id="3fa90-104">About Remote</span></span>

## <a name="short-description"></a><span data-ttu-id="3fa90-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3fa90-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="3fa90-106">Описание выполнения удаленных команд в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa90-106">Describes how to run remote commands in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3fa90-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3fa90-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3fa90-108">Удаленные команды можно выполнять на одном компьютере или на нескольких компьютерах, используя временное или постоянное подключение.</span><span class="sxs-lookup"><span data-stu-id="3fa90-108">You can run remote commands on a single computer or on multiple computers by using a temporary or persistent connection.</span></span> <span data-ttu-id="3fa90-109">Можно также запустить интерактивный сеанс с одним удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="3fa90-109">You can also start an interactive session with a single remote computer.</span></span>

<span data-ttu-id="3fa90-110">В этом разделе приводится ряд примеров, демонстрирующих выполнение различных типов удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="3fa90-110">This topic provides a series of examples to show you how to run different types of remote command.</span></span> <span data-ttu-id="3fa90-111">После выполнения этих основных команд ознакомьтесь с разделами справки, описывающими каждый командлет, используемый в этих командах.</span><span class="sxs-lookup"><span data-stu-id="3fa90-111">After you try these basic commands, read the Help topics that describe each cmdlet that is used in these commands.</span></span> <span data-ttu-id="3fa90-112">В этих разделах содержатся сведения и объясняется, как можно изменить команды в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="3fa90-112">The topics provide the details and explain how you can modify the commands to meet your needs.</span></span>

<span data-ttu-id="3fa90-113">Примечание. чтобы использовать удаленное взаимодействие Windows PowerShell, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="3fa90-113">Note: To use Windows PowerShell remoting, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="3fa90-114">Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-114">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="how-to-start-an-interactive-session-enter-pssession"></a><span data-ttu-id="3fa90-115">КАК ЗАПУСТИТЬ ИНТЕРАКТИВНЫЙ СЕАНС (ENTER-PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="3fa90-115">HOW TO START AN INTERACTIVE SESSION (ENTER-PSSESSION)</span></span>

<span data-ttu-id="3fa90-116">Самый простой способ запуска удаленных команд — запустить интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="3fa90-116">The easiest way to run remote commands is to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="3fa90-117">При запуске сеанса команды, которые вы вводите, выполняются на удаленном компьютере, точно так же, как если бы они были введены непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3fa90-117">When the session starts, the commands that you type run on the remote computer, just as though you typed them directly on the remote computer.</span></span> <span data-ttu-id="3fa90-118">В каждом интерактивном сеансе можно подключиться только к одному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3fa90-118">You can connect to only one computer in each interactive session.</span></span>

<span data-ttu-id="3fa90-119">Чтобы запустить интерактивный сеанс, используйте командлет Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-119">To start an interactive session, use the Enter-PSSession cmdlet.</span></span> <span data-ttu-id="3fa90-120">Следующая команда запускает интерактивный сеанс с компьютером Server01:</span><span class="sxs-lookup"><span data-stu-id="3fa90-120">The following command starts an interactive session with the Server01 computer:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="3fa90-121">Командная строка изменится, указывая, что вы подключены к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="3fa90-121">The command prompt changes to indicate that you are connected to the Server01 computer.</span></span>

```
Server01\PS>
```

<span data-ttu-id="3fa90-122">Теперь можно ввести команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="3fa90-122">Now, you can type commands on the Server01 computer.</span></span>

<span data-ttu-id="3fa90-123">Чтобы завершить интерактивный сеанс, введите:</span><span class="sxs-lookup"><span data-stu-id="3fa90-123">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="3fa90-124">Дополнительные сведения см. в разделе Ввод-PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-124">For more information, see Enter-PSSession.</span></span>

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a><span data-ttu-id="3fa90-125">ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТОВ С ПАРАМЕТРОМ COMPUTERNAME ДЛЯ ПОЛУЧЕНИЯ УДАЛЕННЫХ ДАННЫХ</span><span class="sxs-lookup"><span data-stu-id="3fa90-125">HOW TO USE CMDLETS THAT HAVE A COMPUTERNAME PARAMETER TO GET REMOTE DATA</span></span>

<span data-ttu-id="3fa90-126">Несколько командлетов имеют параметр ComputerName, позволяющий получать объекты с удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3fa90-126">Several cmdlets have a ComputerName parameter that lets you get objects from remote computers.</span></span>

<span data-ttu-id="3fa90-127">Поскольку эти командлеты не используют удаленное взаимодействие Windows PowerShell на основе WS-Management, можно использовать параметр ComputerName этих командлетов на любом компьютере с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa90-127">Because these cmdlets do not use WS-Management-based Windows PowerShell remoting, you can use the ComputerName parameter of these cmdlets on any computer that is running Windows PowerShell.</span></span> <span data-ttu-id="3fa90-128">Компьютеры не обязательно должны быть настроены для удаленного взаимодействия Windows PowerShell, а компьютеры не должны отвечать требованиям к системе для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3fa90-128">The computers do not have to be configured for Windows PowerShell remoting, and the computers do not have to meet the system requirements for remoting.</span></span>

<span data-ttu-id="3fa90-129">Следующие командлеты имеют параметр ComputerName:</span><span class="sxs-lookup"><span data-stu-id="3fa90-129">The following cmdlets have a ComputerName parameter:</span></span>

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

<span data-ttu-id="3fa90-130">Например, следующая команда получает службы на удаленном компьютере Server01:</span><span class="sxs-lookup"><span data-stu-id="3fa90-130">For example, the following command gets the services on the Server01 remote computer:</span></span>

```powershell
Get-Service -ComputerName Server01
```

<span data-ttu-id="3fa90-131">Как правило, командлеты, поддерживающие удаленное взаимодействие без специальной настройки, имеют параметр **ComputerName** и не имеют параметра **сеанса** .</span><span class="sxs-lookup"><span data-stu-id="3fa90-131">Typically, cmdlets that support remoting without special configuration have a **ComputerName** parameter and do not have a **Session** parameter.</span></span> <span data-ttu-id="3fa90-132">Чтобы найти эти командлеты в сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="3fa90-132">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a><span data-ttu-id="3fa90-133">ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ</span><span class="sxs-lookup"><span data-stu-id="3fa90-133">HOW TO RUN A REMOTE COMMAND</span></span>

<span data-ttu-id="3fa90-134">Чтобы выполнить другие команды на удаленных компьютерах, используйте командлет Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="3fa90-134">To run other commands on remote computers, use the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="3fa90-135">Чтобы выполнить одну команду или несколько несвязанных команд, используйте параметр ComputerName параметра Invoke-Command, чтобы указать удаленные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="3fa90-135">To run a single command or a few unrelated commands, use the ComputerName parameter of Invoke-Command to specify the remote computers.</span></span> <span data-ttu-id="3fa90-136">Используйте параметр ScriptBlock для указания команды.</span><span class="sxs-lookup"><span data-stu-id="3fa90-136">Use the ScriptBlock parameter to specify the command.</span></span>

<span data-ttu-id="3fa90-137">Например, следующая команда выполняет команду Get-Culture на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="3fa90-137">For example, the following command runs a Get-Culture command on the Server01 computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="3fa90-138">Параметр ComputerName предназначен для ситуации, когда на одном или нескольких компьютерах выполняется одна команда или несколько несвязанных команд.</span><span class="sxs-lookup"><span data-stu-id="3fa90-138">The ComputerName parameter is designed for situation in which you run a single command or several unrelated commands on one or many computers.</span></span> <span data-ttu-id="3fa90-139">Чтобы установить постоянное подключение к удаленному компьютеру, используйте параметр Session.</span><span class="sxs-lookup"><span data-stu-id="3fa90-139">To establish a persistent connection to a remote computer, use the Session parameter.</span></span>

## <a name="how-to-create-a-persistent-connection-pssession"></a><span data-ttu-id="3fa90-140">СОЗДАНИЕ ПОСТОЯННОГО ПОДКЛЮЧЕНИЯ (PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="3fa90-140">HOW TO CREATE A PERSISTENT CONNECTION (PSSESSION)</span></span>

<span data-ttu-id="3fa90-141">При использовании параметра ComputerName командлета Invoke-Command Windows PowerShell устанавливает соединение только для команды.</span><span class="sxs-lookup"><span data-stu-id="3fa90-141">When you use the ComputerName parameter of the Invoke-Command cmdlet, Windows PowerShell establishes a connection just for the command.</span></span> <span data-ttu-id="3fa90-142">Затем по завершении команды она закрывает подключение.</span><span class="sxs-lookup"><span data-stu-id="3fa90-142">Then, it closes the connection when the command is complete.</span></span> <span data-ttu-id="3fa90-143">Все переменные или функции, определенные в команде, теряются.</span><span class="sxs-lookup"><span data-stu-id="3fa90-143">Any variables or functions that are defined in the command are lost.</span></span>

<span data-ttu-id="3fa90-144">Чтобы создать постоянное подключение к удаленному компьютеру, используйте командлет New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-144">To create a persistent connection to a remote computer, use the New-PSSession cmdlet.</span></span> <span data-ttu-id="3fa90-145">Например, следующая команда создает PSSession на компьютерах Server01 и Server02, а затем сохраняет PSSession в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="3fa90-145">For example, the following command creates PSSessions on the Server01 and Server02 computers and then saves the PSSessions in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="3fa90-146">ВЫПОЛНЕНИЕ КОМАНД В PSSESSION</span><span class="sxs-lookup"><span data-stu-id="3fa90-146">HOW TO RUN COMMANDS IN A PSSESSION</span></span>

<span data-ttu-id="3fa90-147">С помощью PSSession можно выполнять ряд удаленных команд, которые совместно используют данные, такие как функции, псевдонимы и значения переменных.</span><span class="sxs-lookup"><span data-stu-id="3fa90-147">With a PSSession, you can run a series of remote commands that share data, like functions, aliases, and the values of variables.</span></span> <span data-ttu-id="3fa90-148">Для выполнения команд в PSSession используйте параметр Session командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="3fa90-148">To run commands in a PSSession, use the Session parameter of the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="3fa90-149">Например, следующая команда использует командлет Invoke-Command для выполнения команды Get-Process в PSSession на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="3fa90-149">For example, the following command uses the Invoke-Command cmdlet to run a Get-Process command in the PSSessions on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="3fa90-150">Команда сохраняет процессы в переменной $p в каждом сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-150">The command saves the processes in a $p variable in each PSSession.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

<span data-ttu-id="3fa90-151">Так как сеанс PSSession использует постоянное подключение, можно выполнить другую команду в том же сеансе PSSession, который использует переменную $p.</span><span class="sxs-lookup"><span data-stu-id="3fa90-151">Because the PSSession uses a persistent connection, you can run another command in the same PSSession that uses the $p variable.</span></span> <span data-ttu-id="3fa90-152">Следующая команда подсчитывает количество процессов, сохраненных в $p.</span><span class="sxs-lookup"><span data-stu-id="3fa90-152">The following command counts the number of processes saved in $p.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a><span data-ttu-id="3fa90-153">ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ НА НЕСКОЛЬКИХ КОМПЬЮТЕРАХ</span><span class="sxs-lookup"><span data-stu-id="3fa90-153">HOW TO RUN A REMOTE COMMAND ON MULTIPLE COMPUTERS</span></span>

<span data-ttu-id="3fa90-154">Чтобы выполнить удаленную команду на нескольких компьютерах, введите все имена компьютеров в значении параметра ComputerName команды Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="3fa90-154">To run a remote command on multiple computers, type all of the computer names in the value of the ComputerName parameter of Invoke-Command.</span></span> <span data-ttu-id="3fa90-155">Разделяйте имена запятыми.</span><span class="sxs-lookup"><span data-stu-id="3fa90-155">Separate the names with commas.</span></span>

<span data-ttu-id="3fa90-156">Например, следующая команда выполняет команду Get-Culture на трех компьютерах:</span><span class="sxs-lookup"><span data-stu-id="3fa90-156">For example, the following command runs a Get-Culture command on three computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="3fa90-157">Можно также выполнить команду в нескольких PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-157">You can also run a command in multiple PSSessions.</span></span> <span data-ttu-id="3fa90-158">Следующие команды создают PSSession на компьютерах Server01, Server02 и Server03, а затем выполняют Get-Cultureную команду в каждом из PSSession.</span><span class="sxs-lookup"><span data-stu-id="3fa90-158">The following commands create PSSessions on the Server01, Server02, and Server03 computers and then run a Get-Culture command in each of the PSSessions.</span></span>

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="3fa90-159">Чтобы включить список компьютеров локального компьютера, введите имя локального компьютера, введите точку (.) или введите localhost.</span><span class="sxs-lookup"><span data-stu-id="3fa90-159">To include the local computer list of computers, type the name of the local computer, type a dot (.), or type  "localhost".</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a><span data-ttu-id="3fa90-160">ЗАПУСК СЦЕНАРИЯ НА УДАЛЕННЫХ КОМПЬЮТЕРАХ</span><span class="sxs-lookup"><span data-stu-id="3fa90-160">HOW TO RUN A SCRIPT ON REMOTE COMPUTERS</span></span>

<span data-ttu-id="3fa90-161">Чтобы запустить локальный скрипт на удаленных компьютерах, используйте параметр FilePath командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="3fa90-161">To run a local script on remote computers, use the FilePath parameter of Invoke-Command.</span></span>

<span data-ttu-id="3fa90-162">Например, следующая команда запускает сценарий Sample.ps1 на компьютерах S1 и S2:</span><span class="sxs-lookup"><span data-stu-id="3fa90-162">For example, the following command runs the Sample.ps1 script on the S1 and S2 computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

<span data-ttu-id="3fa90-163">Результаты сценария возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3fa90-163">The results of the script are returned to the local computer.</span></span> <span data-ttu-id="3fa90-164">Нет необходимости копировать файлы.</span><span class="sxs-lookup"><span data-stu-id="3fa90-164">You do not need to copy any files.</span></span>

## <a name="how-to-stop-a-remote-command"></a><span data-ttu-id="3fa90-165">КАК ПРЕРЫВАТЬ УДАЛЕННУЮ КОМАНДУ</span><span class="sxs-lookup"><span data-stu-id="3fa90-165">HOW TO STOP A REMOTE COMMAND</span></span>

<span data-ttu-id="3fa90-166">Чтобы прервать выполнение команды, нажмите клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="3fa90-166">To interrupt a command, press CTRL+C.</span></span> <span data-ttu-id="3fa90-167">Запрос на прерывание передается на удаленный компьютер, на котором завершается Удаленная команда.</span><span class="sxs-lookup"><span data-stu-id="3fa90-167">The interrupt request is passed to the remote computer where it terminates the remote command.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3fa90-168">ДОПОЛНИТЕЛЬНЫЕ СВЕДЕНИЯ</span><span class="sxs-lookup"><span data-stu-id="3fa90-168">FOR MORE INFORMATION</span></span>

- <span data-ttu-id="3fa90-169">Сведения о требованиях к системе для удаленного взаимодействия см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-169">For information about the system requirements for remoting, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

- <span data-ttu-id="3fa90-170">Справку по форматированию удаленных выходных данных см. в разделе [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-170">For help in formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

- <span data-ttu-id="3fa90-171">Сведения о принципах работы удаленного взаимодействия, об управлении удаленными данными, специальных конфигурациях, проблемах безопасности и других часто задаваемых вопросах см. в разделе [about_Remote_FAQ](about_Remote_FAQ.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-171">For information about how remoting works, how to manage remote data, special configurations, security issues, and other frequently asked questions, see [about_Remote_FAQ](about_Remote_FAQ.md).</span></span>

- <span data-ttu-id="3fa90-172">Дополнительные сведения об устранении ошибок удаленного взаимодействия см. в разделе about_Remote_Troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="3fa90-172">For help in resolving remoting errors, see about_Remote_Troubleshooting.</span></span>

- <span data-ttu-id="3fa90-173">Дополнительные сведения о PSSession и постоянных подключениях см. в разделе [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-173">For information about PSSessions and persistent connections, see [about_PSSessions](about_PSSessions.md).</span></span>

- <span data-ttu-id="3fa90-174">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-174">For information about Windows PowerShell background jobs, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="3fa90-175">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="3fa90-175">KEYWORDS</span></span>

<span data-ttu-id="3fa90-176">about_Remoting</span><span class="sxs-lookup"><span data-stu-id="3fa90-176">about_Remoting</span></span>

## <a name="see-also"></a><span data-ttu-id="3fa90-177">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="3fa90-177">SEE ALSO</span></span>

[<span data-ttu-id="3fa90-178">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3fa90-178">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="3fa90-179">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="3fa90-179">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="3fa90-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="3fa90-180">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="3fa90-181">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="3fa90-181">about_Remote_FAQ</span></span>](about_Remote_FAQ.md)

[<span data-ttu-id="3fa90-182">about_Remote_TroubleShooting</span><span class="sxs-lookup"><span data-stu-id="3fa90-182">about_Remote_TroubleShooting</span></span>](about_Remote_TroubleShooting.md)

[<span data-ttu-id="3fa90-183">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="3fa90-183">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="3fa90-184">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3fa90-184">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="3fa90-185">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3fa90-185">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="3fa90-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3fa90-186">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
