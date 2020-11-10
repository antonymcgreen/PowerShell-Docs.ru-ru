---
description: Описание параметров, которые рабочий процесс Windows PowerShell добавляет к действиям.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: 93fdcdb9c5afe0b73e843baf2474ec7d3f96a6cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387810"
---
# <a name="about-activitycommonparameters"></a><span data-ttu-id="d1d93-104">О Активитикоммонпараметерс</span><span class="sxs-lookup"><span data-stu-id="d1d93-104">About ActivityCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="d1d93-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d1d93-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="d1d93-106">Описание параметров, которые рабочий процесс Windows PowerShell добавляет к действиям.</span><span class="sxs-lookup"><span data-stu-id="d1d93-106">Describes the parameters that Windows PowerShell Workflow adds to activities.</span></span>

## <a name="long-description"></a><span data-ttu-id="d1d93-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d1d93-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d1d93-108">Рабочий процесс Windows PowerShell добавляет общие параметры действия к действиям, производным от базового класса Псактивити.</span><span class="sxs-lookup"><span data-stu-id="d1d93-108">Windows PowerShell Workflow adds the activity common parameters to activities that are derived from the PSActivity base class.</span></span> <span data-ttu-id="d1d93-109">В эту категорию входит действие InlineScript и командлеты Windows PowerShell, которые реализуются как действия, такие как Get-Process и Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="d1d93-109">This category includes the InlineScript activity and Windows PowerShell cmdlets that are implemented as activities, such as Get-Process and Get-WinEvent.</span></span>

<span data-ttu-id="d1d93-110">Общие параметры действия недопустимы для действий Suspend-Workflow и Checkpoint-Workflow и не добавляются в командлеты или выражения, которые рабочий процесс Windows PowerShell автоматически запускает в блоке сценария InlineScript или аналогичном действии.</span><span class="sxs-lookup"><span data-stu-id="d1d93-110">The activity common parameters are not valid on the Suspend-Workflow and Checkpoint-Workflow activities and they are not added to cmdlets or expressions that Windows PowerShell Workflow automatically runs in an InlineScript script block or similar activity.</span></span> <span data-ttu-id="d1d93-111">Общие параметры действий доступны в действии InlineScript, но не в командах в блоке сценария InlineScript.</span><span class="sxs-lookup"><span data-stu-id="d1d93-111">The activity common parameters are available on the InlineScript activity, but not on commands in the InlineScript script block.</span></span>

<span data-ttu-id="d1d93-112">Некоторые общие параметры действия также представляют собой общие параметры рабочего процесса или общие параметры Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-112">Several of the activity common parameters are also workflow common parameters or Windows PowerShell common parameters.</span></span> <span data-ttu-id="d1d93-113">Другие общие параметры действия являются уникальными для действий.</span><span class="sxs-lookup"><span data-stu-id="d1d93-113">Other activity common parameters are unique to activities.</span></span>

<span data-ttu-id="d1d93-114">Дополнительные сведения об общих параметрах рабочих процессов см. в статье about_WorkflowCommonParameters.</span><span class="sxs-lookup"><span data-stu-id="d1d93-114">For information about the workflow common parameters, see about_WorkflowCommonParameters.</span></span> <span data-ttu-id="d1d93-115">Дополнительные сведения о стандартных параметрах Windows PowerShell см. в разделе about_CommonParameters.</span><span class="sxs-lookup"><span data-stu-id="d1d93-115">For information about the Windows PowerShell common parameters, see about_CommonParameters.</span></span>

### <a name="list-of-activity-common-parameters"></a><span data-ttu-id="d1d93-116">СПИСОК ОБЩИХ ПАРАМЕТРОВ ДЕЙСТВИЯ</span><span class="sxs-lookup"><span data-stu-id="d1d93-116">LIST OF ACTIVITY COMMON PARAMETERS</span></span>

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a><span data-ttu-id="d1d93-117">ОПИСАНИЯ ПАРАМЕТРОВ</span><span class="sxs-lookup"><span data-stu-id="d1d93-117">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="d1d93-118">В этом разделе описываются общие параметры действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-118">This section describes the activity common parameters.</span></span>

#### <a name="appendoutput-boolean"></a><span data-ttu-id="d1d93-119">аппендаутпут \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-119">AppendOutput \<Boolean\></span></span>

<span data-ttu-id="d1d93-120">Значение `$True` добавляет выходные данные действия в значение переменной.</span><span class="sxs-lookup"><span data-stu-id="d1d93-120">A value of `$True` adds the output of the activity to the value of the variable.</span></span>
<span data-ttu-id="d1d93-121">Значение параметра `$False` не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="d1d93-121">A value of `$False` has no effect.</span></span> <span data-ttu-id="d1d93-122">По умолчанию присвоение переменной значения заменяет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="d1d93-122">By default, assigning a value to a variable replaces the variable value.</span></span>

<span data-ttu-id="d1d93-123">Например, следующие команды добавляют объект Process в объект службы в `$x` переменной.</span><span class="sxs-lookup"><span data-stu-id="d1d93-123">For example, the following commands add a process object to the service object in the `$x` variable.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

<span data-ttu-id="d1d93-124">Этот параметр предназначен для рабочих процессов на основе XAML.</span><span class="sxs-lookup"><span data-stu-id="d1d93-124">This parameter is designed for XAML-based workflows.</span></span> <span data-ttu-id="d1d93-125">В рабочих процессах скрипта можно также использовать оператор присваивания + = для добавления выходных данных к значению переменной, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-125">In script workflows, you can also use the += assignment operator to add output to the value of a variable, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a><span data-ttu-id="d1d93-126">См \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d1d93-126">Debug \<SwitchParameter\></span></span>

<span data-ttu-id="d1d93-127">Отображает сведения на уровне программиста об операции, выполняемой командой.</span><span class="sxs-lookup"><span data-stu-id="d1d93-127">Displays programmer-level detail about the operation performed by the command.</span></span>
<span data-ttu-id="d1d93-128">Параметр debug переопределяет значение переменной $DebugPreference для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-128">The Debug parameter overrides the value of the $DebugPreference variable for the current command.</span></span> <span data-ttu-id="d1d93-129">Этот параметр работает только в том случае, если команда создает сообщения отладки.</span><span class="sxs-lookup"><span data-stu-id="d1d93-129">This parameter works only when the command generates debugging messages.</span></span> <span data-ttu-id="d1d93-130">Этот параметр также является общим параметром Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-130">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="displayname-string"></a><span data-ttu-id="d1d93-131">DisplayName \<String\></span><span class="sxs-lookup"><span data-stu-id="d1d93-131">DisplayName \<String\></span></span>

<span data-ttu-id="d1d93-132">Указывает понятное имя действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-132">Specifies a friendly name for the activity.</span></span> <span data-ttu-id="d1d93-133">Значение DisplayName отображается на индикаторе выполнения во время выполнения рабочего процесса и в значении свойства Progress задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-133">The DisplayName value appears in the progress bar while the workflow runs and in the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="d1d93-134">Если параметр Пспрогрессмессаже также включен в команду, содержимое индикатора выполнения отображается в \<DisplayName\> \<PSProgressMessage\> формате: format.</span><span class="sxs-lookup"><span data-stu-id="d1d93-134">When the PSProgressMessage parameter is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

#### <a name="erroraction-actionpreference"></a><span data-ttu-id="d1d93-135">ErrorAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="d1d93-135">ErrorAction \<ActionPreference\></span></span>

<span data-ttu-id="d1d93-136">Определяет, как действие реагирует на устранимую ошибку команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-136">Determines how the activity responds to a non-terminating error from the command.</span></span> <span data-ttu-id="d1d93-137">Он не влияет на ошибки завершения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-137">It has no effect on termination errors.</span></span> <span data-ttu-id="d1d93-138">Этот параметр работает только в том случае, если команда создает неустранимую ошибку, например из командлета Write-Error.</span><span class="sxs-lookup"><span data-stu-id="d1d93-138">This parameter works only when the command generates a non-terminating error, such as those from the Write-Error cmdlet.</span></span> <span data-ttu-id="d1d93-139">Параметр ErrorAction переопределяет значение переменной $ErrorActionPreference для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-139">The ErrorAction parameter overrides the value of the $ErrorActionPreference variable for the current command.</span></span> <span data-ttu-id="d1d93-140">Этот параметр также является общим параметром Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-140">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="d1d93-141">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1d93-141">Valid values:</span></span>

- <span data-ttu-id="d1d93-142">Продолжения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-142">Continue.</span></span> <span data-ttu-id="d1d93-143">Отображает сообщение об ошибке и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-143">Displays the error message and continues executing the command.</span></span> <span data-ttu-id="d1d93-144">По умолчанию используется значение Continue.</span><span class="sxs-lookup"><span data-stu-id="d1d93-144">"Continue" is the default value.</span></span>

- <span data-ttu-id="d1d93-145">ограничение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d1d93-145">Ignore.</span></span> <span data-ttu-id="d1d93-146">Подавляет сообщение об ошибке и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-146">Suppresses the error message and continues executing the command.</span></span>
  <span data-ttu-id="d1d93-147">В отличие от SilentlyContinue, Ignore не добавляет сообщение об ошибке в автоматическую переменную $Error.</span><span class="sxs-lookup"><span data-stu-id="d1d93-147">Unlike SilentlyContinue, Ignore does not add the error message to the $Error automatic variable.</span></span> <span data-ttu-id="d1d93-148">Значение ignore введено в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d1d93-148">The Ignore value is introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="d1d93-149">INQUIRE.</span><span class="sxs-lookup"><span data-stu-id="d1d93-149">Inquire.</span></span> <span data-ttu-id="d1d93-150">Отображает сообщение об ошибке и запрашивает подтверждение перед продолжением выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-150">Displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="d1d93-151">Это значение используется редко.</span><span class="sxs-lookup"><span data-stu-id="d1d93-151">This value is rarely used.</span></span>

- <span data-ttu-id="d1d93-152">Анализируем.</span><span class="sxs-lookup"><span data-stu-id="d1d93-152">Suspend.</span></span> <span data-ttu-id="d1d93-153">Автоматически приостанавливает задание рабочего процесса, чтобы обеспечить дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="d1d93-153">Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="d1d93-154">После изучения рабочий процесс можно возобновить.</span><span class="sxs-lookup"><span data-stu-id="d1d93-154">After investigation, the workflow can be resumed.</span></span>

- <span data-ttu-id="d1d93-155">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="d1d93-155">SilentlyContinue.</span></span> <span data-ttu-id="d1d93-156">Подавляет сообщение об ошибке и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-156">Suppresses the error message and continues executing the command.</span></span>

- <span data-ttu-id="d1d93-157">Остановка.</span><span class="sxs-lookup"><span data-stu-id="d1d93-157">Stop.</span></span> <span data-ttu-id="d1d93-158">Отображает сообщение об ошибке и останавливает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-158">Displays the error message and stops executing the command.</span></span>

#### <a name="input-object"></a><span data-ttu-id="d1d93-159">Входной \<Object[]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-159">Input \<Object[]\></span></span>

<span data-ttu-id="d1d93-160">Отправляет коллекцию объектов в действие.</span><span class="sxs-lookup"><span data-stu-id="d1d93-160">Submits a collection of objects to an activity.</span></span> <span data-ttu-id="d1d93-161">Этот режим является альтернативой конвейерной передаче объектов по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="d1d93-161">This is an alternative to piping objects to the activity one at a time.</span></span>

#### <a name="mergeerrortooutput-boolean"></a><span data-ttu-id="d1d93-162">мержееррортуутпут \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-162">MergeErrorToOutput \<Boolean\></span></span>

<span data-ttu-id="d1d93-163">Значение `$True` добавляет ошибки в выходной поток.</span><span class="sxs-lookup"><span data-stu-id="d1d93-163">A value of `$True` adds errors to the output stream.</span></span> <span data-ttu-id="d1d93-164">Значение параметра `$False` не действует.</span><span class="sxs-lookup"><span data-stu-id="d1d93-164">A value of `$False` has not effect.</span></span> <span data-ttu-id="d1d93-165">Используйте этот параметр совместно с `ForEach -Parallel` ключевыми словами Parallel и для сбора ошибок и выходных данных из нескольких параллельных команд в одной коллекции.</span><span class="sxs-lookup"><span data-stu-id="d1d93-165">Use this parameter with the Parallel and `ForEach -Parallel` keywords to collect errors and output from multiple parallel commands in a single collection.</span></span>

#### <a name="psactionretrycount-int32"></a><span data-ttu-id="d1d93-166">псактионретрикаунт \<Int32\></span><span class="sxs-lookup"><span data-stu-id="d1d93-166">PSActionRetryCount \<Int32\></span></span>

<span data-ttu-id="d1d93-167">Повторно пытается выполнить действие в случае неудачной первой попытки.</span><span class="sxs-lookup"><span data-stu-id="d1d93-167">Tries repeatedly to run the activity if the first attempt fails.</span></span> <span data-ttu-id="d1d93-168">При использовании нулевого значения по умолчанию повторная попытка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d1d93-168">The default value, 0, does not retry.</span></span>

#### <a name="psactionretryintervalsec-int32"></a><span data-ttu-id="d1d93-169">псактионретринтервалсек \<Int32\></span><span class="sxs-lookup"><span data-stu-id="d1d93-169">PSActionRetryIntervalSec \<Int32\></span></span>

<span data-ttu-id="d1d93-170">Определяет интервал между повторными попытками действия в секундах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-170">Determines the interval between action retries in seconds.</span></span> <span data-ttu-id="d1d93-171">Нулевое значение по умолчанию повторяет действие немедленно.</span><span class="sxs-lookup"><span data-stu-id="d1d93-171">The default value, 0, retries the action immediately.</span></span> <span data-ttu-id="d1d93-172">Этот параметр допустим только в том случае, если параметр Псактионретрикаунт также используется в команде.</span><span class="sxs-lookup"><span data-stu-id="d1d93-172">This parameter is valid only when the PSActionRetryCount parameter is also used in the command.</span></span>

#### <a name="psactionrunningtimeoutsec-int32"></a><span data-ttu-id="d1d93-173">псактионруннингтимеаутсек \<Int32\></span><span class="sxs-lookup"><span data-stu-id="d1d93-173">PSActionRunningTimeoutSec \<Int32\></span></span>

<span data-ttu-id="d1d93-174">Определяет, как долго действие может выполняться на каждом целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-174">Determines how long the activity can run on each target computer.</span></span> <span data-ttu-id="d1d93-175">Если действие не завершится до истечения времени ожидания, Рабочий процесс Windows PowerShell выдаст ошибку завершения и прекратит обработку рабочего процесса на затронутом целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-175">If the activity does not complete before the timeout expires, Windows PowerShell Workflow generates a terminating error and stops processing the workflow on the affected target computer.</span></span>

#### <a name="psallowredirection-boolean"></a><span data-ttu-id="d1d93-176">псалловредиректион \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-176">PSAllowRedirection \<Boolean\></span></span>

<span data-ttu-id="d1d93-177">Значение $True позволяет перенаправление подключения к конечным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="d1d93-177">A value of $True allows redirection of the connection to the target computers.</span></span>
<span data-ttu-id="d1d93-178">Значение $False не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="d1d93-178">A value of $False has no effect.</span></span> <span data-ttu-id="d1d93-179">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-179">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-180">При использовании параметра Псконнектионури удаленное назначение может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="d1d93-180">When you use the PSConnectionURI parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="d1d93-181">По умолчанию Windows PowerShell не перенаправляет подключения, но можно использовать параметр Псалловредиректион со значением $True, чтобы разрешить перенаправление соединения с конечным компьютером.</span><span class="sxs-lookup"><span data-stu-id="d1d93-181">By default, Windows PowerShell does not redirect connections, but you can use the PSAllowRedirection parameter with a value of $True to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="d1d93-182">Можно также ограничить число перенаправлений подключения, задав свойство MaximumConnectionRedirectionCount для `$PSSessionOption` переменной предпочтений или свойство MaximumConnectionRedirectionCount значения параметра ссессионоптион командлетов, которые создают сеанс.</span><span class="sxs-lookup"><span data-stu-id="d1d93-182">You can also limit the number of times that the connection is redirected by setting the MaximumConnectionRedirectionCount property of the `$PSSessionOption` preference variable, or the MaximumConnectionRedirectionCount property of the value of the SSessionOption parameter of cmdlets that create a session.</span></span> <span data-ttu-id="d1d93-183">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="d1d93-183">The default value is 5.</span></span>

#### <a name="psapplicationname-string"></a><span data-ttu-id="d1d93-184">псаппликатионнаме \<String\></span><span class="sxs-lookup"><span data-stu-id="d1d93-184">PSApplicationName \<String\></span></span>

<span data-ttu-id="d1d93-185">Указывает сегмент имени приложения универсального кода ресурса (URI) соединения, используемого для подключения к конечным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="d1d93-185">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="d1d93-186">Этот параметр позволяет указать имя приложения, если в команде не используется параметр ConnectionURI.</span><span class="sxs-lookup"><span data-stu-id="d1d93-186">Use this parameter to specify the application name when you are not using the ConnectionURI parameter in the command.</span></span> <span data-ttu-id="d1d93-187">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-187">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-188">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-188">The default value is the value of the `$PSSessionApplicationName` preference variable on the target computer.</span></span> <span data-ttu-id="d1d93-189">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="d1d93-189">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="d1d93-190">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="d1d93-190">This value is appropriate for most uses.</span></span> <span data-ttu-id="d1d93-191">Дополнительные сведения см. в разделе [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d1d93-191">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="d1d93-192">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="d1d93-192">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="d1d93-193">Значение этого параметра должно совпадать со значением свойства URLPrefix прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-193">The value of this parameter should match the value of the URLPrefix property of a listener on the remote computer.</span></span>

#### <a name="psauthentication-authenticationmechanism"></a><span data-ttu-id="d1d93-194">псаусентикатион \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="d1d93-194">PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="d1d93-195">Указывает механизм, используемый для проверки подлинности учетных данных пользователя при подключении к конечным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="d1d93-195">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span> <span data-ttu-id="d1d93-196">Допустимые значения: Default, Basic, Credssp, Digest, Kerberos, Negotiate и NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="d1d93-196">Valid values are Default, Basic, Credssp, Digest, Kerberos, Negotiate, and NegotiateWithImplicitCredential.</span></span> <span data-ttu-id="d1d93-197">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="d1d93-197">The default value is Default.</span></span> <span data-ttu-id="d1d93-198">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-198">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-199">Сведения о значениях этого параметра см. в описании перечисления **System. Management. Automation. пространства. AuthenticationMechanism** в пакете SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-199">For information about the values of this parameter, see the description of the **System.Management.Automation.Runspaces.AuthenticationMechanism** enumeration in the PowerShell SDK.</span></span>

> [!WARNING]
> <span data-ttu-id="d1d93-200">Проверка подлинности CredSSP, при применении которой учетные данные пользователя передаются на удаленный компьютер, предназначена для команд, требующих проверки подлинности для нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="d1d93-200">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d1d93-201">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="d1d93-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d1d93-202">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="d1d93-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="pscertificatethumbprint-string"></a><span data-ttu-id="d1d93-203">псцертификатесумбпринт \<String\></span><span class="sxs-lookup"><span data-stu-id="d1d93-203">PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="d1d93-204">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-204">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="d1d93-205">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="d1d93-205">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="d1d93-206">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-206">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-207">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="d1d93-207">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d1d93-208">Они могут быть сопоставлены только с локальными учетными записями пользователей; они не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="d1d93-208">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d1d93-209">Чтобы получить сертификат, используйте командлеты [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) или [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) на диске CERT: Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-209">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="pscomputername-string"></a><span data-ttu-id="d1d93-210">PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-210">PSComputerName \<String[]\></span></span>

<span data-ttu-id="d1d93-211">Указывает целевые компьютеры, на которых выполняется действие.</span><span class="sxs-lookup"><span data-stu-id="d1d93-211">Specifies the target computers on which the activity run.</span></span> <span data-ttu-id="d1d93-212">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="d1d93-212">The default is the local computer.</span></span> <span data-ttu-id="d1d93-213">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-213">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-214">Введите имя NETBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="d1d93-214">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="d1d93-215">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="d1d93-215">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="d1d93-216">Чтобы включить локальный компьютер в значение параметра PSComputerName, откройте Windows PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="d1d93-216">To include the local computer in the value of the PSComputerName parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="d1d93-217">Если этот параметр не указан в команде или имеет значение $null или является пустой строкой, целевой объект рабочего процесса является локальным компьютером, а удаленное взаимодействие Windows PowerShell не используется для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-217">If this parameter is omitted from the command, or it value is $null or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="d1d93-218">Чтобы использовать IP-адрес в значении параметра ComputerName, команда должна включать параметр PSCredential.</span><span class="sxs-lookup"><span data-stu-id="d1d93-218">To use an IP address in the value of the ComputerName parameter, the command must include the PSCredential parameter.</span></span> <span data-ttu-id="d1d93-219">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-219">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="d1d93-220">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d1d93-220">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="psconfigurationname-string"></a><span data-ttu-id="d1d93-221">псконфигуратионнаме \<String\></span><span class="sxs-lookup"><span data-stu-id="d1d93-221">PSConfigurationName \<String\></span></span>

<span data-ttu-id="d1d93-222">Указывает конфигурации сеанса, используемые для создания сеансов на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-222">Specifies the session configurations that are used to create sessions on the target computers.</span></span> <span data-ttu-id="d1d93-223">Введите имя конфигурации сеанса на конечных компьютерах (не на компьютере, на котором работает рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="d1d93-223">Enter the name of a session configuration on the target computers (not on the computer that is running the workflow.</span></span> <span data-ttu-id="d1d93-224">Значение по умолчанию — Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-224">The default is Microsoft.PowerShell.</span></span> <span data-ttu-id="d1d93-225">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-225">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretrycount-uint"></a><span data-ttu-id="d1d93-226">псконнектионретрикаунт \<UInt\></span><span class="sxs-lookup"><span data-stu-id="d1d93-226">PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="d1d93-227">Указывает максимальное число попыток подключения к каждому целевому компьютеру, если первая попытка соединения завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="d1d93-227">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="d1d93-228">Введите число от 1 до 4 294 967 295 (UInt. MaxValue).</span><span class="sxs-lookup"><span data-stu-id="d1d93-228">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="d1d93-229">Значение по умолчанию, равное нулю (0), не представляет повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="d1d93-229">The default value, zero (0), represents no retry attempts.</span></span>
<span data-ttu-id="d1d93-230">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-230">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretryintervalsec-uint"></a><span data-ttu-id="d1d93-231">псконнектионретринтервалсек \<UInt\></span><span class="sxs-lookup"><span data-stu-id="d1d93-231">PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="d1d93-232">Указывает задержку между попытками повтора подключения в секундах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-232">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="d1d93-233">Значение по умолчанию равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="d1d93-233">The default value is zero (0).</span></span> <span data-ttu-id="d1d93-234">Этот параметр допустим только в том случае, если значение Псконнектионретрикаунт равно по меньшей мере 1.</span><span class="sxs-lookup"><span data-stu-id="d1d93-234">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span> <span data-ttu-id="d1d93-235">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-235">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionuri-systemuri"></a><span data-ttu-id="d1d93-236">псконнектионури \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="d1d93-236">PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="d1d93-237">Указывает универсальный код ресурса (URI), определяющий конечную точку подключения для действия на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-237">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the activity on the target computer.</span></span> <span data-ttu-id="d1d93-238">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="d1d93-238">The URI must be fully qualified.</span></span> <span data-ttu-id="d1d93-239">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-239">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-240">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d1d93-240">The format of this string is as follows:</span></span>

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

<span data-ttu-id="d1d93-241">Значение по умолчанию — `http://localhost:5985/WSMAN`.</span><span class="sxs-lookup"><span data-stu-id="d1d93-241">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="d1d93-242">Если не указать Псконнектионури, можно использовать параметры Псусессл, PSComputerName, Пспорт и Псаппликатионнаме, чтобы указать значения Псконнектионури.</span><span class="sxs-lookup"><span data-stu-id="d1d93-242">If you do not specify a PSConnectionURI, you can use the PSUseSSL, PSComputerName, PSPort, and PSApplicationName parameters to specify the PSConnectionURI values.</span></span>

<span data-ttu-id="d1d93-243">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1d93-243">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d1d93-244">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1d93-244">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d1d93-245">Чтобы использовать порты по умолчанию для удаленного взаимодействия Windows PowerShell, укажите порт 5985 для протокола HTTP и 5986 для протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1d93-245">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="pscredential-pscredential"></a><span data-ttu-id="d1d93-246">PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="d1d93-246">PSCredential \<PSCredential\></span></span>

<span data-ttu-id="d1d93-247">Указывает учетную запись пользователя, имеющую разрешение на запуск действия на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-247">Specifies a user account that has permission to run the activity on the target computer.</span></span> <span data-ttu-id="d1d93-248">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="d1d93-248">The default is the current user.</span></span> <span data-ttu-id="d1d93-249">Этот параметр допустим только в том случае, если параметр PSComputerName включен в команду.</span><span class="sxs-lookup"><span data-stu-id="d1d93-249">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span> <span data-ttu-id="d1d93-250">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-250">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-251">Введите имя пользователя, например "User01" или "Domain01\User01", или введите переменную, содержащую объект PSCredential, например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="d1d93-251">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a PSCredential object, such as one that the Get-Credential cmdlet returns.</span></span> <span data-ttu-id="d1d93-252">Если ввести только имя пользователя, появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="d1d93-252">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="psdebug-psdatacollectiondebugrecord"></a><span data-ttu-id="d1d93-253">PSDebug \<PSDataCollection[DebugRecord]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-253">PSDebug \<PSDataCollection[DebugRecord]\></span></span>

<span data-ttu-id="d1d93-254">Добавляет сообщения отладки из действия в указанную коллекцию записей отладки вместо записи отладочных сообщений на консоль или значения свойства Debug задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-254">Adds debug messages from the activity to the specified debug record collection, instead of writing the debug messages to the console or to the value of the Debug property of the workflow job.</span></span> <span data-ttu-id="d1d93-255">Сообщения отладки из нескольких действий можно добавить в один объект коллекции записей отладки.</span><span class="sxs-lookup"><span data-stu-id="d1d93-255">You can add debug messages from multiple activities to the same debug record collection object.</span></span>

<span data-ttu-id="d1d93-256">Чтобы использовать этот общий параметр действия, используйте командлет New-Object, чтобы создать объект Псдатаколлектион с типом Дебугрекорд и сохранить объект в переменной.</span><span class="sxs-lookup"><span data-stu-id="d1d93-256">To use this activity common parameter, use the New-Object cmdlet to create a PSDataCollection object with a type of DebugRecord and save the object in a variable.</span></span> <span data-ttu-id="d1d93-257">Затем используйте переменную в качестве значения параметра PSDebug для одного или нескольких действий, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-257">Then, use the variable as the value of the PSDebug parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a><span data-ttu-id="d1d93-258">псдисаблесериализатион \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-258">PSDisableSerialization \<Boolean\></span></span>

<span data-ttu-id="d1d93-259">Указывает действию, что в рабочий процесс необходимо вернуть "динамические" (несериализованные) объекты.</span><span class="sxs-lookup"><span data-stu-id="d1d93-259">Directs the activity to return "live" (not serialized) objects to the workflow.</span></span>
<span data-ttu-id="d1d93-260">Полученные объекты имеют методы, а также свойства, но их нельзя сохранять, когда установлена контрольная точка.</span><span class="sxs-lookup"><span data-stu-id="d1d93-260">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>

#### <a name="psdisableserializationpreference-boolean"></a><span data-ttu-id="d1d93-261">псдисаблесериализатионпреференце \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-261">PSDisableSerializationPreference \<Boolean\></span></span>

<span data-ttu-id="d1d93-262">Применяет эквивалент параметра Псдисаблесериализатион ко всему рабочему процессу, а не только к действию.</span><span class="sxs-lookup"><span data-stu-id="d1d93-262">Applies the equivalent of the PSDisableSerialization parameter to the entire workflow, not just the activity.</span></span> <span data-ttu-id="d1d93-263">Добавление этого параметра обычно не рекомендуется, так как рабочий процесс, который не сериализует его объекты, не может быть возобновлен или сохранен.</span><span class="sxs-lookup"><span data-stu-id="d1d93-263">Adding this parameter is generally not recommended, because a workflow that doesn't serialize its objects cannot be resumed or persisted.</span></span>

<span data-ttu-id="d1d93-264">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1d93-264">Valid values:</span></span>

- <span data-ttu-id="d1d93-265">Параметры Если параметр не указан и вы не добавили в действие параметры Псдисаблесериализатион, сериализуются объекты.</span><span class="sxs-lookup"><span data-stu-id="d1d93-265">(Default) If omitted, and you have also not added the PSDisableSerialization parameter to an activity, objects are serialized.</span></span>

- <span data-ttu-id="d1d93-266">`$True`.</span><span class="sxs-lookup"><span data-stu-id="d1d93-266">`$True`.</span></span> <span data-ttu-id="d1d93-267">Направляет все действия в рабочем процессе для возврата "динамических" (не сериализованных) объектов.</span><span class="sxs-lookup"><span data-stu-id="d1d93-267">Directs all activities within a workflow to return "live" (not serialized) objects.</span></span> <span data-ttu-id="d1d93-268">Полученные объекты имеют методы, а также свойства, но их нельзя сохранять, когда установлена контрольная точка.</span><span class="sxs-lookup"><span data-stu-id="d1d93-268">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>
- <span data-ttu-id="d1d93-269">`$False`.</span><span class="sxs-lookup"><span data-stu-id="d1d93-269">`$False`.</span></span> <span data-ttu-id="d1d93-270">Объекты рабочего процесса сериализуются.</span><span class="sxs-lookup"><span data-stu-id="d1d93-270">Workflow objects are serialized.</span></span>

#### <a name="pserror-psdatacollectionerrorrecord"></a><span data-ttu-id="d1d93-271">псеррор \<PSDataCollection[ErrorRecord]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-271">PSError \<PSDataCollection[ErrorRecord]\></span></span>

<span data-ttu-id="d1d93-272">Добавляет сообщения об ошибках из действия в указанную коллекцию записей ошибок вместо записи сообщений об ошибках в консоль или в значение свойства Error задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-272">Adds error messages from the activity to the specified error record collection, instead of writing the error messages to the console or to the value of the Error property of the workflow job.</span></span> <span data-ttu-id="d1d93-273">Сообщения об ошибках из нескольких действий можно добавить в один объект коллекции записей ошибок.</span><span class="sxs-lookup"><span data-stu-id="d1d93-273">You can add error messages from multiple activities to the same error record collection object.</span></span>

<span data-ttu-id="d1d93-274">Чтобы использовать этот общий параметр действия, используйте `New-Object` командлет, чтобы создать объект псдатаколлектион с типом ерроррекорд и сохранить объект в переменной.</span><span class="sxs-lookup"><span data-stu-id="d1d93-274">To use this activity common parameter, use the `New-Object` cmdlet to create a PSDataCollection object with a type of ErrorRecord and save the object in a variable.</span></span> <span data-ttu-id="d1d93-275">Затем используйте переменную в качестве значения параметра Псеррор для одного или нескольких действий, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-275">Then, use the variable as the value of the PSError parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a><span data-ttu-id="d1d93-276">псперсист \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-276">PSPersist \<Boolean\></span></span>

<span data-ttu-id="d1d93-277">Создает контрольную точку после действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-277">Takes a checkpoint after the activity.</span></span> <span data-ttu-id="d1d93-278">Эта контрольная точка находится в дополнение к любым контрольным точкам, указанным в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="d1d93-278">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span> <span data-ttu-id="d1d93-279">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-279">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-280">"Checkpoint" или "точка сохранения" — это моментальный снимок состояния рабочего процесса и данных, которые фиксируются во время выполнения рабочего процесса и сохраняются в хранилище сохраняемости на диске.</span><span class="sxs-lookup"><span data-stu-id="d1d93-280">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk.</span></span> <span data-ttu-id="d1d93-281">Рабочий процесс Windows PowerShell использует сохраненные данные для возобновления приостановленного или прерванного рабочего процесса из последней точки сохранения, а не для перезапуска рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-281">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="d1d93-282">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1d93-282">Valid values:</span></span>

- <span data-ttu-id="d1d93-283">Параметры Если опустить этот параметр, контрольные точки не добавляются.</span><span class="sxs-lookup"><span data-stu-id="d1d93-283">(Default) If you omit this parameter, no checkpoints are added.</span></span> <span data-ttu-id="d1d93-284">Контрольные точки берутся на основе параметров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-284">Checkpoints are taken based on the settings for the workflow.</span></span>

- <span data-ttu-id="d1d93-285">`$True`.</span><span class="sxs-lookup"><span data-stu-id="d1d93-285">`$True`.</span></span> <span data-ttu-id="d1d93-286">Контрольная точка устанавливается после завершения действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-286">Takes a checkpoint after the activity completes.</span></span>
  <span data-ttu-id="d1d93-287">Эта контрольная точка находится в дополнение к любым контрольным точкам, указанным в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="d1d93-287">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="d1d93-288">`$False`.</span><span class="sxs-lookup"><span data-stu-id="d1d93-288">`$False`.</span></span> <span data-ttu-id="d1d93-289">Контрольные точки не добавляются.</span><span class="sxs-lookup"><span data-stu-id="d1d93-289">No checkpoints are added.</span></span> <span data-ttu-id="d1d93-290">Контрольные точки берутся только при указании в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="d1d93-290">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="psport-int32"></a><span data-ttu-id="d1d93-291">пспорт \<Int32\></span><span class="sxs-lookup"><span data-stu-id="d1d93-291">PSPort \<Int32\></span></span>

<span data-ttu-id="d1d93-292">Указывает сетевой порт на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-292">Specifies the network port on the target computers.</span></span> <span data-ttu-id="d1d93-293">Порты по умолчанию: 5985 (порт службы удаленного управления Windows для HTTP) и 5986 (порт службы удаленного управления Windows для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d1d93-293">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span> <span data-ttu-id="d1d93-294">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-294">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-295">Не используйте параметр Пспорт, если не требуется.</span><span class="sxs-lookup"><span data-stu-id="d1d93-295">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="d1d93-296">Порт, заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d1d93-296">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d1d93-297">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-297">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="d1d93-298">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="d1d93-298">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="psprogress-psdatacollectionprogressrecord"></a><span data-ttu-id="d1d93-299">пспрогресс \<PSDataCollection[ProgressRecord]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-299">PSProgress \<PSDataCollection[ProgressRecord]\></span></span>

<span data-ttu-id="d1d93-300">Добавляет сообщения о ходе выполнения из действия в указанную коллекцию записей о ходе выполнения вместо записи сообщений о ходе выполнения в консоль или в значение свойства Progress задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-300">Adds progress messages from the activity to the specified progress record collection, instead of writing the progress messages to the console or to the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="d1d93-301">Сообщения о ходе выполнения из нескольких действий можно добавить в один объект коллекции записей хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-301">You can add progress messages from multiple activities to the same progress record collection object.</span></span>

#### <a name="psprogressmessage-string"></a><span data-ttu-id="d1d93-302">пспрогрессмессаже \<String\></span><span class="sxs-lookup"><span data-stu-id="d1d93-302">PSProgressMessage \<String\></span></span>

<span data-ttu-id="d1d93-303">Задает понятное описание действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-303">Specifies a friendly description of the activity.</span></span> <span data-ttu-id="d1d93-304">Значение Пспрогрессмессаже отображается на индикаторе выполнения во время выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-304">The PSProgressMessage value appears in the progress bar while the workflow runs.</span></span> <span data-ttu-id="d1d93-305">Если параметр DisplayName также включен в команду, содержимое индикатора выполнения отображается в \<DisplayName\> \<PSProgressMessage\> формате: format.</span><span class="sxs-lookup"><span data-stu-id="d1d93-305">When the DisplayName is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

<span data-ttu-id="d1d93-306">Этот параметр особенно полезен для идентификации действий в блоке скрипта ForEach-Parallel.</span><span class="sxs-lookup"><span data-stu-id="d1d93-306">This parameter is particularly useful for identifying activities in a ForEach -Parallel script block.</span></span> <span data-ttu-id="d1d93-307">Без этого сообщения действия во всех параллельных ветвях идентифицируются одному имени.</span><span class="sxs-lookup"><span data-stu-id="d1d93-307">Without this message, activities in all parallel branches are identified by the same name.</span></span>

#### <a name="psremotingbehavior-remotingbehavior"></a><span data-ttu-id="d1d93-308">псремотингбехавиор \<RemotingBehavior\></span><span class="sxs-lookup"><span data-stu-id="d1d93-308">PSRemotingBehavior \<RemotingBehavior\></span></span>

<span data-ttu-id="d1d93-309">Указывает, как осуществляется удаленное взаимодействие при выполнении действия на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-309">Specifies how remoting is managed when the activity is run on target computers.</span></span>
<span data-ttu-id="d1d93-310">По умолчанию используется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-310">PowerShell is the default.</span></span>

<span data-ttu-id="d1d93-311">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1d93-311">Valid values are:</span></span>

- <span data-ttu-id="d1d93-312">Нет: действие не выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-312">None: The activity is not run on remote computers.</span></span>

- <span data-ttu-id="d1d93-313">PowerShell: удаленное взаимодействие Windows PowerShell используется для выполнения действия на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d1d93-313">PowerShell: Windows PowerShell remoting is used to run the activity on target computers.</span></span>

- <span data-ttu-id="d1d93-314">Custom: действие поддерживает собственный тип удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-314">Custom: The activity supports its own type of remoting.</span></span> <span data-ttu-id="d1d93-315">Это значение допустимо, если командлет, реализуемый в качестве действия, задает значение атрибута Ремотингкапабилити равным Суппортедбикомманд, а команда включает параметр ComputerName.</span><span class="sxs-lookup"><span data-stu-id="d1d93-315">This value is valid when the cmdlet that is being implemented as an activity sets the value of the RemotingCapability attribute to SupportedByCommand and the command includes the ComputerName parameter.</span></span>

#### <a name="psrequiredmodules-string"></a><span data-ttu-id="d1d93-316">псрекуиредмодулес \<String[]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-316">PSRequiredModules \<String[]\></span></span>

<span data-ttu-id="d1d93-317">Импортирует указанные модули перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-317">Imports the specified modules before running the command.</span></span> <span data-ttu-id="d1d93-318">Введите имена модулей.</span><span class="sxs-lookup"><span data-stu-id="d1d93-318">Enter the module names.</span></span> <span data-ttu-id="d1d93-319">Модули должны быть установлены на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1d93-319">The modules must be installed on the target computer.</span></span>

<span data-ttu-id="d1d93-320">Модули, которые устанавливаются в пути, указанном в переменной среды PSModulePath, автоматически импортируются при первом использовании любой команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="d1d93-320">Modules that are installed in a path specified in the PSModulePath environment variable are automatically imported on first use of any command in the module.</span></span>
<span data-ttu-id="d1d93-321">Используйте этот параметр для импорта модулей, которые не находятся в расположении PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="d1d93-321">Use this parameter to import modules that are not in a PSModulePath location.</span></span>

<span data-ttu-id="d1d93-322">Поскольку каждое действие в рабочем процессе выполняется в собственном сеансе, команда Import-Module импортирует модуль только в тот сеанс, в котором он выполняется.</span><span class="sxs-lookup"><span data-stu-id="d1d93-322">Because each activity in a workflow runs in its own session, an Import-Module command imports a module only into the session in which it runs.</span></span> <span data-ttu-id="d1d93-323">Она не импортирует модуль в сеансы, в которых выполняются другие действия.</span><span class="sxs-lookup"><span data-stu-id="d1d93-323">It does not import the module into sessions in which other activities run.</span></span>

#### <a name="pssessionoption-pssessionoption"></a><span data-ttu-id="d1d93-324">PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="d1d93-324">PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="d1d93-325">Задает дополнительные параметры для сеансов целевых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d1d93-325">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="d1d93-326">Введите объект PSSessionOption, например, созданный с помощью командлета New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="d1d93-326">Enter a PSSessionOption object, such as one that you create by using the New-PSSessionOption cmdlet.</span></span> <span data-ttu-id="d1d93-327">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-327">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-328">Значения по умолчанию для параметров сеанса определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="d1d93-328">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="d1d93-329">В противном случае сеанс использует значения, указанные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-329">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="d1d93-330">Описание параметров сеанса, включая значения по умолчанию, см. в разделе справки по командлету New-PSSessionOption [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="d1d93-330">For a description of the session options, including the default values, see the help topic for the New-PSSessionOption cmdlet [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="d1d93-331">Дополнительные сведения о переменной настройки $PSSessionOption см. в разделе [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d1d93-331">For more information about the $PSSessionOption preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="psusessl-boolean"></a><span data-ttu-id="d1d93-332">псусессл \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-332">PSUseSSL \<Boolean\></span></span>

<span data-ttu-id="d1d93-333">Значение $True использует протокол SSL (SSL) для установления соединения с конечным компьютером.</span><span class="sxs-lookup"><span data-stu-id="d1d93-333">A value of $True uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="d1d93-334">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="d1d93-334">By default, SSL is not used.</span></span> <span data-ttu-id="d1d93-335">Значение $False не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="d1d93-335">A value of $False has no effect.</span></span> <span data-ttu-id="d1d93-336">Этот общий параметр действия также является общим параметром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-336">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="d1d93-337">Протокол WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="d1d93-337">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="d1d93-338">UseSSL является дополнительной защитой, которая отправляет данные по HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1d93-338">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="d1d93-339">Если вы используете этот параметр, но SSL недоступен для порт, указанному в команде, она завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d1d93-339">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

#### <a name="psverbose-psdatacollectionverboserecord"></a><span data-ttu-id="d1d93-340">псвербосе \<PSDataCollection[VerboseRecord]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span></span>

<span data-ttu-id="d1d93-341">Добавляет подробные сообщения из действия в указанную детальную коллекцию записей вместо записи подробных сообщений в консоль или значения свойства verbose задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-341">Adds verbose messages from the activity to the specified verbose record collection, instead of writing the verbose messages to the console or to the value of the Verbose property of the workflow job.</span></span> <span data-ttu-id="d1d93-342">Подробные сообщения из нескольких действий можно добавить в один объект коллекции подробных записей.</span><span class="sxs-lookup"><span data-stu-id="d1d93-342">You can add verbose messages from multiple activities to the same verbose record collection object.</span></span>

#### <a name="pswarning-psdatacollectionwarningrecord"></a><span data-ttu-id="d1d93-343">псварнинг \<PSDataCollection[WarningRecord]\></span><span class="sxs-lookup"><span data-stu-id="d1d93-343">PSWarning \<PSDataCollection[WarningRecord]\></span></span>

<span data-ttu-id="d1d93-344">Добавляет предупреждающие сообщения из действия в указанную коллекцию записей предупреждений вместо того, чтобы записывать предупреждающие сообщения в консоль или значение свойства предупреждения для задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d1d93-344">Adds warning messages from the activity to the specified warning record collection, instead of writing the warning messages to the console or to the value of the Warning property of the workflow job.</span></span> <span data-ttu-id="d1d93-345">Предупреждения из нескольких действий можно добавить в один объект коллекции записей предупреждений.</span><span class="sxs-lookup"><span data-stu-id="d1d93-345">You can add warning messages from multiple activities to the same warning record collection object.</span></span>

#### <a name="result"></a><span data-ttu-id="d1d93-346">Результат</span><span class="sxs-lookup"><span data-stu-id="d1d93-346">Result</span></span>

<span data-ttu-id="d1d93-347">Этот параметр допустим только в рабочих процессах XAML.</span><span class="sxs-lookup"><span data-stu-id="d1d93-347">This parameter is valid only in XAML workflows.</span></span>

#### <a name="usedefaultinput-boolean"></a><span data-ttu-id="d1d93-348">уседефаултинпут \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="d1d93-348">UseDefaultInput \<Boolean\></span></span>

<span data-ttu-id="d1d93-349">Принимает все входные данные рабочего процесса как входные данные для действия по значению.</span><span class="sxs-lookup"><span data-stu-id="d1d93-349">Accepts all workflow input as input to the activity by value.</span></span>

<span data-ttu-id="d1d93-350">Например, действие Get-Process в следующем примере рабочего процесса использует общий параметр действия UseDefaultInput для получения входных данных, которые передаются в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="d1d93-350">For example, the Get-Process activity in the following sample workflow uses the UseDefaultInput activity common parameter to get input that is passed to the workflow.</span></span> <span data-ttu-id="d1d93-351">При запуске рабочего процесса с входными данными эти входные данные используются действием.</span><span class="sxs-lookup"><span data-stu-id="d1d93-351">When you run the workflow with input, that input is used by the activity.</span></span>

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a><span data-ttu-id="d1d93-352">Verbose \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d1d93-352">Verbose \<SwitchParameter\></span></span>

<span data-ttu-id="d1d93-353">Отображает подробные сведения об операции, выполняемой командой.</span><span class="sxs-lookup"><span data-stu-id="d1d93-353">Displays detailed information about the operation performed by the command.</span></span>
<span data-ttu-id="d1d93-354">Эти сведения похожи на сведения в трассировке или в журнале транзакций.</span><span class="sxs-lookup"><span data-stu-id="d1d93-354">This information resembles the information in a trace or in a transaction log.</span></span>
<span data-ttu-id="d1d93-355">Параметр verbose переопределяет значение переменной $VerbosePreference для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-355">The Verbose parameter overrides the value of the $VerbosePreference variable for the current command.</span></span> <span data-ttu-id="d1d93-356">Этот параметр работает, только если команда создает подробное сообщение.</span><span class="sxs-lookup"><span data-stu-id="d1d93-356">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="d1d93-357">Этот параметр также является общим параметром Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-357">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="warningaction-actionpreference"></a><span data-ttu-id="d1d93-358">WarningAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="d1d93-358">WarningAction \<ActionPreference\></span></span>

<span data-ttu-id="d1d93-359">Определяет, как действие реагирует на предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d1d93-359">Determines how the activity responds to a warning.</span></span> <span data-ttu-id="d1d93-360">По умолчанию используется значение Continue.</span><span class="sxs-lookup"><span data-stu-id="d1d93-360">"Continue" is the default value.</span></span> <span data-ttu-id="d1d93-361">Параметр WarningAction переопределяет значение переменной $WarningPreference для текущей команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-361">The WarningAction parameter overrides the value of the $WarningPreference variable for the current command.</span></span> <span data-ttu-id="d1d93-362">Этот параметр работает, только если команда создает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="d1d93-362">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="d1d93-363">Этот параметр также является общим параметром Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d93-363">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="d1d93-364">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1d93-364">Valid Values:</span></span>

- <span data-ttu-id="d1d93-365">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="d1d93-365">SilentlyContinue.</span></span> <span data-ttu-id="d1d93-366">Подавляет предупреждающее сообщение и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-366">Suppresses the warning message and continues executing the command.</span></span>

- <span data-ttu-id="d1d93-367">Продолжения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-367">Continue.</span></span> <span data-ttu-id="d1d93-368">Отображает предупреждающее сообщение и возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-368">Displays the warning message and continues executing the command.</span></span>
  <span data-ttu-id="d1d93-369">По умолчанию используется значение Continue.</span><span class="sxs-lookup"><span data-stu-id="d1d93-369">"Continue" is the default value.</span></span>

- <span data-ttu-id="d1d93-370">INQUIRE.</span><span class="sxs-lookup"><span data-stu-id="d1d93-370">Inquire.</span></span> <span data-ttu-id="d1d93-371">Отображает предупреждающее сообщение и запрашивает подтверждение перед продолжением выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1d93-371">Displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="d1d93-372">Это значение используется редко.</span><span class="sxs-lookup"><span data-stu-id="d1d93-372">This value is rarely used.</span></span>

- <span data-ttu-id="d1d93-373">Остановка.</span><span class="sxs-lookup"><span data-stu-id="d1d93-373">Stop.</span></span> <span data-ttu-id="d1d93-374">Отображает предупреждающее сообщение и прекращает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="d1d93-374">Displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d93-375">Параметр WarningAction не переопределяет значение переменной предпочтений $WarningAction, если параметр используется в команде для выполнения скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="d1d93-375">The WarningAction parameter does not override the value of the $WarningAction preference variable when the parameter is used in a command to run a script or function.</span></span>

### <a name="examples"></a><span data-ttu-id="d1d93-376">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1d93-376">EXAMPLES</span></span>

<span data-ttu-id="d1d93-377">Общие параметры действий крайне удобны.</span><span class="sxs-lookup"><span data-stu-id="d1d93-377">The activity common parameters are extremely useful.</span></span> <span data-ttu-id="d1d93-378">Например, параметр PSComputerName можно использовать для выполнения определенных действий только на подмножестве конечных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d1d93-378">For example, you can use the PSComputerName parameter to run particular activities on only a subset of the target computers.</span></span>

<span data-ttu-id="d1d93-379">Также можно использовать параметры Псконнектионретрикаунт и Псконнектионретринтервалсек для настройки значений повтора для определенных действий.</span><span class="sxs-lookup"><span data-stu-id="d1d93-379">Or, you might use the PSConnectionRetryCount and PSConnectionRetryIntervalSec parameters to adjust the retry values for particular activities.</span></span>

<span data-ttu-id="d1d93-380">В следующем примере показано, как использовать общие параметры действия PSComputerName для выполнения действия Get-EventLog только на компьютерах, определенных в определенном домене.</span><span class="sxs-lookup"><span data-stu-id="d1d93-380">The following example shows how to use the PSComputerName activity common parameters to run a Get-EventLog activity only on computers it a particular domain.</span></span>

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a><span data-ttu-id="d1d93-381">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="d1d93-381">SEE ALSO</span></span>

<span data-ttu-id="d1d93-382">[about_Workflows](about_workflows.md) 
 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="d1d93-382">[about_Workflows](about_workflows.md)
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span></span>
