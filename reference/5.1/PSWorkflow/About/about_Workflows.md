---
description: Краткое введение в функцию рабочего процесса PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231589"
---
# <a name="about-workflows"></a><span data-ttu-id="515bf-104">О рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="515bf-104">About Workflows</span></span>

## <a name="short-description"></a><span data-ttu-id="515bf-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="515bf-105">Short description</span></span>

<span data-ttu-id="515bf-106">Краткое введение в функцию рабочего процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="515bf-106">Provides a brief introduction to the PowerShell Workflow feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="515bf-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="515bf-107">Long description</span></span>

<span data-ttu-id="515bf-108">Рабочий процесс PowerShell предоставляет преимущества [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) в PowerShell и позволяет создавать и запускать рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="515bf-108">PowerShell Workflow brings the benefits of the [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) to PowerShell and enables you to write and run workflows.</span></span>

<span data-ttu-id="515bf-109">Рабочий процесс PowerShell появился в PowerShell 3,0, а модуль доступен для PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="515bf-109">PowerShell Workflow was introduced in PowerShell 3.0 and the module is available up to PowerShell 5.1.</span></span> <span data-ttu-id="515bf-110">Дополнительные сведения о рабочем процессе PowerShell см. в [руководствах по рабочим](/previous-versions/powershell/scripting/components/workflows-guide) процессам и [написании рабочего процесса Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span><span class="sxs-lookup"><span data-stu-id="515bf-110">For more information about PowerShell Workflow, see the [Workflows Guide](/previous-versions/powershell/scripting/components/workflows-guide) and [Writing a Windows PowerShell Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span></span>

## <a name="about-workflows"></a><span data-ttu-id="515bf-111">О рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="515bf-111">About workflows</span></span>

<span data-ttu-id="515bf-112">Рабочие процессы — это команды, состоящие из упорядоченной последовательности связанных действий.</span><span class="sxs-lookup"><span data-stu-id="515bf-112">Workflows are commands that consist of an ordered sequence of related activities.</span></span> <span data-ttu-id="515bf-113">Как правило, они выполняются в течение продолжительного периода времени, сбор данных и внесение изменений в сотни компьютеров, часто в разнородных средах.</span><span class="sxs-lookup"><span data-stu-id="515bf-113">Typically, they run for an extended period of time, gathering data from and making changes to hundreds of computers, often in heterogeneous environments.</span></span>

<span data-ttu-id="515bf-114">Рабочие процессы можно написать на языке XAML, на языке, используемом в Windows Workflow Foundation, или на языке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="515bf-114">Workflows can be written in XAML, the language used in Windows Workflow Foundation, or in the PowerShell language.</span></span> <span data-ttu-id="515bf-115">Рабочие процессы обычно упаковываются в модули и включают разделы справки.</span><span class="sxs-lookup"><span data-stu-id="515bf-115">Workflows are typically packaged in modules and include help topics.</span></span> <span data-ttu-id="515bf-116">Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span><span class="sxs-lookup"><span data-stu-id="515bf-116">For more information, see [XAML Overview (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span></span>

<span data-ttu-id="515bf-117">Рабочие процессы являются критически важными в ИТ-среде, так как они могут выдерживать перезагрузку и автоматически восстанавливать из распространенных сбоев.</span><span class="sxs-lookup"><span data-stu-id="515bf-117">Workflows are critical in an IT environment because they can survive reboots and recover automatically from common failures.</span></span> <span data-ttu-id="515bf-118">Вы можете отключить и повторно подключиться к сеансам и компьютерам, на которых выполняются рабочие процессы, не прерывая обработку рабочего процесса, а также приостанавливать и возобновлять рабочие процессы без потери данных.</span><span class="sxs-lookup"><span data-stu-id="515bf-118">You can disconnect and reconnect from sessions and computers running workflows without interrupting workflow processing, and suspend and resume workflows transparently without data loss.</span></span> <span data-ttu-id="515bf-119">Каждое действие в рабочем процессе можно регистрировать и подвергать аудиту для справки.</span><span class="sxs-lookup"><span data-stu-id="515bf-119">Each activity in a workflow can be logged and audited for reference.</span></span>
<span data-ttu-id="515bf-120">Рабочие процессы можно запускать в качестве заданий и планировать с помощью функции запланированных заданий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="515bf-120">Workflows can run as jobs and can be scheduled by using the Scheduled Jobs feature of PowerShell.</span></span>

<span data-ttu-id="515bf-121">Состояние и данные в рабочем процессе сохраняются или сохраняются в начале и в конце рабочего процесса и в указанных точках.</span><span class="sxs-lookup"><span data-stu-id="515bf-121">The state and data in a workflow is saved or persisted at the beginning and end of the workflow and at points that you specify.</span></span> <span data-ttu-id="515bf-122">Точки сохранения рабочих процессов работают подобно моментальным снимкам базы данных или программам, чтобы защитить рабочий процесс от влияния прерываний и сбоев.</span><span class="sxs-lookup"><span data-stu-id="515bf-122">Workflow persistence points work like database snapshots or program checkpoints to protect the workflow from the effects of interruptions and failures.</span></span> <span data-ttu-id="515bf-123">Если рабочему процессу не удается выполнить восстановление после сбоя, можно использовать сохраненные данные и возобновить работу из последней точки сохранения, а не выполнять большой рабочий процесс с самого начала.</span><span class="sxs-lookup"><span data-stu-id="515bf-123">If the workflow is unable to recover from a failure, you can use the persisted data and resume from the last persistence point, instead of rerunning an extensive workflow from the beginning.</span></span>

## <a name="workflow-requirements-and-configuration"></a><span data-ttu-id="515bf-124">Требования и конфигурация рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="515bf-124">Workflow requirements and configuration</span></span>

<span data-ttu-id="515bf-125">Конфигурация рабочего процесса PowerShell состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="515bf-125">A PowerShell Workflow configuration consists of the following elements:</span></span>

- <span data-ttu-id="515bf-126">Клиентский компьютер, на котором выполняется рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="515bf-126">A client computer, which runs the workflow.</span></span>
- <span data-ttu-id="515bf-127">Сеанс рабочего процесса **PSSession** на клиентском компьютере или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="515bf-127">A workflow session, **PSSession** , on the client computer or on a remote computer.</span></span>
- <span data-ttu-id="515bf-128">Управляемые узлы — целевые компьютеры, на которые влияют действия рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="515bf-128">Managed nodes, the target computers that are affected by the workflow activities.</span></span>

<span data-ttu-id="515bf-129">Сеанс рабочего процесса не требуется, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="515bf-129">The workflow session isn't required, but is recommended.</span></span> <span data-ttu-id="515bf-130">**PSSession** может воспользоваться возможностями надежного восстановления и отключенных сеансов PowerShell для восстановления отключенных сеансов рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="515bf-130">**PSSessions** can take advantage of the robust recovery and Disconnected Sessions features of PowerShell to recover disconnected workflow sessions.</span></span> <span data-ttu-id="515bf-131">Дополнительные сведения см. в разделе [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span><span class="sxs-lookup"><span data-stu-id="515bf-131">For more information, see [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span></span>

<span data-ttu-id="515bf-132">Так как клиентский компьютер и компьютер, на котором выполняется сеанс рабочего процесса, могут быть управляемыми узлами, Рабочий процесс можно запустить на одном компьютере, выполняющем все роли.</span><span class="sxs-lookup"><span data-stu-id="515bf-132">Because the client computer and the computer on which the workflow session runs can be managed nodes, you can run a workflow on a single computer that fulfills all roles.</span></span>

<span data-ttu-id="515bf-133">Клиентский компьютер и компьютер, на котором запущен сеанс рабочего процесса, должны работать под управлением PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="515bf-133">The client computer and the computer on which the workflow session runs must be running PowerShell 3.0.</span></span> <span data-ttu-id="515bf-134">Поддерживаются все подходящие системы, включая варианты установки основных серверных компонентов для операционных систем Windows Server.</span><span class="sxs-lookup"><span data-stu-id="515bf-134">All eligible systems are supported, including the Server Core installation options of Windows Server operating systems.</span></span>

<span data-ttu-id="515bf-135">Для запуска рабочих процессов, включающих командлеты, на управляемых узлах должен быть установлен Windows PowerShell 2,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="515bf-135">To run workflows that include cmdlets, the managed nodes must have Windows PowerShell 2.0 or later.</span></span> <span data-ttu-id="515bf-136">Управляемые узлы не нуждаются в PowerShell, если только рабочий процесс не включает командлеты.</span><span class="sxs-lookup"><span data-stu-id="515bf-136">Managed nodes don't require PowerShell unless the workflow includes cmdlets.</span></span> <span data-ttu-id="515bf-137">Рабочие процессы, содержащие команды инструментарий управления Windows (WMI) (WMI) и модель CIM (CIM), можно запускать на компьютерах без PowerShell.</span><span class="sxs-lookup"><span data-stu-id="515bf-137">You can run workflows that include Windows Management Instrumentation (WMI) and Common Information Model (CIM) commands on computers that don't have PowerShell.</span></span>

## <a name="how-to-get-workflows"></a><span data-ttu-id="515bf-138">Как получить рабочие процессы</span><span class="sxs-lookup"><span data-stu-id="515bf-138">How to get workflows</span></span>

<span data-ttu-id="515bf-139">Рабочие процессы обычно упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="515bf-139">Workflows are typically packaged in modules.</span></span> <span data-ttu-id="515bf-140">Чтобы импортировать модуль, включающий рабочий процесс, используйте любую команду в модуле или используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="515bf-140">To import the module that includes a workflow, use any command in the module or use the `Import-Module` cmdlet.</span></span>
<span data-ttu-id="515bf-141">Модули импортируются автоматически при первом использовании любой команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="515bf-141">Modules are imported automatically on first use of any command in the module.</span></span>

<span data-ttu-id="515bf-142">Чтобы найти рабочие процессы в модулях, установленных на компьютере, используйте `Get-Command` параметр **CommandType** командлета.</span><span class="sxs-lookup"><span data-stu-id="515bf-142">To find the workflows in modules installed on your computer, use the `Get-Command` cmdlet's **CommandType** parameter.</span></span>

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a><span data-ttu-id="515bf-143">Запуск рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="515bf-143">How to run workflows</span></span>

<span data-ttu-id="515bf-144">Для запуска рабочего процесса используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="515bf-144">To run a workflow, use the following procedure.</span></span>

1. <span data-ttu-id="515bf-145">Если управляемый узел является локальным компьютером, этот шаг не требуется.</span><span class="sxs-lookup"><span data-stu-id="515bf-145">When the managed node is the local computer, this step isn't required.</span></span>
   <span data-ttu-id="515bf-146">В противном случае на клиентском компьютере запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="515bf-146">Otherwise, on the client computer, start PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. <span data-ttu-id="515bf-147">Включите удаленное взаимодействие PowerShell на компьютере, на котором запущен сеанс рабочего процесса, и на управляемых узлах, затронутых рабочими процессами, включающими командлеты.</span><span class="sxs-lookup"><span data-stu-id="515bf-147">Enable PowerShell remoting on the computer that runs the workflow session and on managed nodes affected by workflows that include cmdlets.</span></span>

   <span data-ttu-id="515bf-148">Этот шаг необходимо выполнить только один раз на каждом компьютере, участвующем в работе.</span><span class="sxs-lookup"><span data-stu-id="515bf-148">You only need to do this step once on each participating computer.</span></span>

   <span data-ttu-id="515bf-149">Этот шаг необходим только при выполнении рабочих процессов, включающих командлеты.</span><span class="sxs-lookup"><span data-stu-id="515bf-149">This step is required only when running workflows that include cmdlets.</span></span> <span data-ttu-id="515bf-150">Не требуется включать удаленное взаимодействие на клиентском компьютере, если сеанс рабочих процессов не выполняется на клиентском компьютере или на управляемых узлах, на которых выполняется PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="515bf-150">You don't need to enable remoting on the client computer, unless the workflows session runs on the client computer, or on any managed nodes that are running PowerShell 3.0.</span></span>

   <span data-ttu-id="515bf-151">Чтобы включить удаленное взаимодействие, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="515bf-151">To enable remoting, use the `Enable-PSRemoting` cmdlet.</span></span>

   ```powershell
   Enable-PSRemoting -Force
   ```

   <span data-ttu-id="515bf-152">Включить удаленное взаимодействие можно с помощью параметра **включить выполнение скрипта** групповая политика.</span><span class="sxs-lookup"><span data-stu-id="515bf-152">You can enable remoting by using the **Turn on Script Execution** Group Policy setting.</span></span> <span data-ttu-id="515bf-153">Дополнительные сведения см. в разделе [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) и [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="515bf-153">For more information, see [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) and [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

1. <span data-ttu-id="515bf-154">Используйте `New-PSWorkflowSession` `New-PSSession` командлеты или для создания сеанса рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="515bf-154">Use the `New-PSWorkflowSession` or `New-PSSession` cmdlets to create the workflow session.</span></span>

   <span data-ttu-id="515bf-155">`New-PSWorkflowSession`Командлет запускает сеанс, использующий встроенную конфигурацию сеанса **Microsoft. PowerShell. Workflow** на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="515bf-155">The `New-PSWorkflowSession` cmdlet starts a session that uses the built-in **Microsoft.PowerShell.Workflow** session configuration on the destination computer.</span></span> <span data-ttu-id="515bf-156">Эта конфигурация сеанса включает в себя сценарии, файлы типов и форматирования, а также параметры, предназначенные для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="515bf-156">This session configuration includes scripts, type and formatting files, and options that are designed for workflows.</span></span>

   <span data-ttu-id="515bf-157">Или используйте `New-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="515bf-157">Or, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="515bf-158">Используйте параметр **configurationName** , чтобы указать конфигурацию сеанса **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="515bf-158">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span> <span data-ttu-id="515bf-159">Эта команда аналогична использованию `New-PSWorkflowSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="515bf-159">This command is the same as using the `New-PSWorkflowSession` cmdlet.</span></span>

   <span data-ttu-id="515bf-160">Альтернативой является использование `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="515bf-160">An alternative is to use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="515bf-161">Используйте параметр **configurationName** , чтобы указать конфигурацию сеанса **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="515bf-161">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

   <span data-ttu-id="515bf-162">На локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="515bf-162">On the local computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   <span data-ttu-id="515bf-163">На удаленном компьютере:</span><span class="sxs-lookup"><span data-stu-id="515bf-163">On a remote computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   <span data-ttu-id="515bf-164">Если вы являетесь администратором на компьютере сеанса рабочего процесса, можно использовать `New-PSWorkflowExecutionOption` командлет для создания настраиваемых параметров для конфигурации сеанса рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="515bf-164">If you are an Administrator on the workflow session computer, you can use the `New-PSWorkflowExecutionOption` cmdlet to create custom option settings for the workflow session configuration.</span></span> <span data-ttu-id="515bf-165">И с помощью `Set-PSSessionConfiguration` командлета измените конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="515bf-165">And, use the `Set-PSSessionConfiguration` cmdlet to change the session configuration.</span></span>

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. <span data-ttu-id="515bf-166">Запустите рабочий процесс в сеансе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="515bf-166">Run the workflow in the workflow session.</span></span> <span data-ttu-id="515bf-167">Чтобы указать имена управляемых узлов (конечных компьютеров), используйте общий параметр рабочего процесса **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="515bf-167">To specify the names of the managed nodes, target computers, use the **PSComputerName** workflow common parameter.</span></span>

   <span data-ttu-id="515bf-168">В следующих примерах выполняется рабочий процесс с именем **Test-Workflow**.</span><span class="sxs-lookup"><span data-stu-id="515bf-168">The following examples run the workflow named **Test-Workflow**.</span></span>

   <span data-ttu-id="515bf-169">Где управляемый узел — это компьютер, на котором размещается сеанс рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="515bf-169">Where the managed node is the computer that hosts the workflow session:</span></span>

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   <span data-ttu-id="515bf-170">Где управляемые узлы являются удаленными компьютерами.</span><span class="sxs-lookup"><span data-stu-id="515bf-170">Where the managed nodes are remote computers.</span></span>

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   <span data-ttu-id="515bf-171">В следующем примере запускается **тестовый рабочий процесс** на сотнях компьютеров.</span><span class="sxs-lookup"><span data-stu-id="515bf-171">The following example runs the **Test-Workflow** on hundreds of computers.</span></span> <span data-ttu-id="515bf-172">`Get-Content`Командлет получает имена компьютеров из текстового файла и сохраняет их в `$Servers` переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="515bf-172">The `Get-Content` cmdlet gets the computer names from a text file and saves them in the `$Servers` variable on the local computer.</span></span>

   <span data-ttu-id="515bf-173">`Invoke-Command` использует `$Using` Модификатор области для определения `$Servers` переменной в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="515bf-173">`Invoke-Command` uses the `$Using` scope modifier to define the `$Servers` variable in the local session.</span></span> <span data-ttu-id="515bf-174">Дополнительные сведения об `$Using` модификаторе области см. в разделе [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="515bf-174">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a><span data-ttu-id="515bf-175">Использование общих параметров рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="515bf-175">Using workflow common parameters</span></span>

<span data-ttu-id="515bf-176">Общие параметры рабочего процесса — это набор параметров, которые PowerShell автоматически добавляет ко всем рабочим процессам.</span><span class="sxs-lookup"><span data-stu-id="515bf-176">The workflow common parameters are a set of parameters that PowerShell adds automatically to all workflows.</span></span> <span data-ttu-id="515bf-177">PowerShell добавляет общие параметры командлета для всех рабочих процессов, даже если рабочий процесс не использует атрибут **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="515bf-177">PowerShell adds the cmdlet common parameters to all workflows, even if the workflow doesn't use the **CmdletBinding** attribute.</span></span>

<span data-ttu-id="515bf-178">Например, следующий рабочий процесс не определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="515bf-178">For example, the following workflow defines no parameters.</span></span> <span data-ttu-id="515bf-179">Однако при запуске рабочего процесса у него есть и **общиепараметры** , и **воркфловкоммонпараметерс**.</span><span class="sxs-lookup"><span data-stu-id="515bf-179">However, when you run the workflow, it has both the **CommonParameters** and **WorkflowCommonParameters**.</span></span>

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

<span data-ttu-id="515bf-180">Общие параметры рабочего процесса включают несколько параметров, необходимых для выполнения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="515bf-180">The workflow common parameters include several parameters that are essential to running workflows.</span></span> <span data-ttu-id="515bf-181">Например, общий параметр **PSComputerName** указывает управляемые узлы, на которые влияет рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="515bf-181">For example, the **PSComputerName** common parameter specifies the managed nodes that the workflow affects.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

<span data-ttu-id="515bf-182">Общий параметр рабочего процесса **псперсист** определяет, когда сохраняются данные рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="515bf-182">The **PSPersist** workflow common parameter determines when workflow data is persisted.</span></span> <span data-ttu-id="515bf-183">Он позволяет добавлять точки сохранения между действиями в рабочие процессы, которые не определяют точки сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="515bf-183">It enables you to add persistence point between activities to workflows that don't define persistence points.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

<span data-ttu-id="515bf-184">Другие общие параметры рабочего процесса позволяют указать характеристики удаленного подключения к управляемым узлам.</span><span class="sxs-lookup"><span data-stu-id="515bf-184">Other workflow common parameters let you specify the characteristics of the remote connection to the managed nodes.</span></span> <span data-ttu-id="515bf-185">Их имена и функциональные возможности похожи на параметры командлетов удаленного взаимодействия, включая `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="515bf-185">Their names and functionality are similar to the parameters of remoting cmdlets, including `Invoke-Command`.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

<span data-ttu-id="515bf-186">Следите за тем, чтобы отличать параметры удаленного взаимодействия, определяющие подключение для сеанса рабочего процесса, из общих параметров рабочего процесса с **префиксом PS** , определяющих соединение с управляемыми узлами.</span><span class="sxs-lookup"><span data-stu-id="515bf-186">Take care to distinguish the remoting parameters that define the connection for the workflow session from the **PS-prefixed** workflow common parameters that define the connection to the managed nodes.</span></span>

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

<span data-ttu-id="515bf-187">Некоторые общие параметры рабочего процесса являются уникальными для рабочих процессов, например параметр **пспараметерколлектион** , позволяющий указывать различные значения общих параметров рабочего процесса для разных удаленных узлов.</span><span class="sxs-lookup"><span data-stu-id="515bf-187">Some workflow common parameters are unique to workflows, such as the **PSParameterCollection** parameter that lets you specify different workflow common parameter values for different remote nodes.</span></span> <span data-ttu-id="515bf-188">Список и описание общих параметров рабочего процесса см. в разделе [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="515bf-188">For a list and description of the workflow common parameters, see [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="515bf-189">См. также статью</span><span class="sxs-lookup"><span data-stu-id="515bf-189">See also</span></span>

[<span data-ttu-id="515bf-190">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="515bf-190">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[<span data-ttu-id="515bf-191">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="515bf-191">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

<span data-ttu-id="515bf-192">Командлеты [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="515bf-192">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="515bf-193">Руководство по рабочим процессам</span><span class="sxs-lookup"><span data-stu-id="515bf-193">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="515bf-194">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="515bf-194">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
