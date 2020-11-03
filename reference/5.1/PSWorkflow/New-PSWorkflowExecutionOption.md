---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229809"
---
# <span data-ttu-id="97ad2-103">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="97ad2-103">New-PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="97ad2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="97ad2-104">SYNOPSIS</span></span>

<span data-ttu-id="97ad2-105">Создает объект, содержащий параметры конфигурации сеанса для сеансов рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-105">Creates an object that contains session configuration options for workflow sessions.</span></span>

## <span data-ttu-id="97ad2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97ad2-106">SYNTAX</span></span>

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="97ad2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97ad2-107">DESCRIPTION</span></span>

<span data-ttu-id="97ad2-108">`New-PSWorkflowExecutionOption`Командлет создает объект, который содержит дополнительные параметры для конфигураций сеанса рабочего процесса, которые являются конфигурациями сеансов, предназначенными для запуска рабочих процессов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97ad2-108">The `New-PSWorkflowExecutionOption` cmdlet creates an object that contains advanced options for workflow session configurations, that is session configurations designed to run Windows PowerShell Workflow workflows.</span></span>

<span data-ttu-id="97ad2-109">Можно использовать объект **PSWorkflowExecutionOption** , который `New-PSWorkflowExecutionOption` создает в качестве значения параметра **сессионтипеоптион** командлетов, которые создают или изменяют конфигурацию сеанса, например `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="97ad2-109">You can use the **PSWorkflowExecutionOption** object that `New-PSWorkflowExecutionOption` generates as the value of the **SessionTypeOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="97ad2-110">Каждый параметр `New-PSWorkflowExecutionOption` командлета представляет свойство объекта параметра конфигурации сеанса рабочего процесса, возвращаемого командлетом.</span><span class="sxs-lookup"><span data-stu-id="97ad2-110">Each parameter of the `New-PSWorkflowExecutionOption` cmdlet represents a property of the workflow session configuration option object that the cmdlet returns.</span></span> <span data-ttu-id="97ad2-111">Если параметр не указан, командлет создает для свойства объект со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97ad2-111">If you omit a parameter, the cmdlet creates the object with a default value for the property.</span></span>

<span data-ttu-id="97ad2-112">`New-PSWorkflowExecutionOption`Командлет является частью компонента рабочего процесса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97ad2-112">The `New-PSWorkflowExecutionOption` cmdlet is part of the Windows PowerShell Workflow feature.</span></span>

<span data-ttu-id="97ad2-113">В эту команду также можно добавить общие параметры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="97ad2-113">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="97ad2-114">Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="97ad2-114">For more information about workflow common parameters, see [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span></span>

<span data-ttu-id="97ad2-115">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="97ad2-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="97ad2-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="97ad2-116">EXAMPLES</span></span>

### <span data-ttu-id="97ad2-117">Пример 1. Создание объекта параметров рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="97ad2-117">Example 1: Create a Workflow Options Object</span></span>

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

<span data-ttu-id="97ad2-118">Эта команда использует `New-PSWorkflowExecutionOption` командлет, чтобы увеличить значение **макссессионсперворкфлов** до 10 и уменьшить значение **максдисконнектедсессионс** до 200.</span><span class="sxs-lookup"><span data-stu-id="97ad2-118">This command uses the `New-PSWorkflowExecutionOption` cmdlet to increase the **MaxSessionsPerWorkflow** value to 10 and decrease the **MaxDisconnectedSessions** value to 200.</span></span>

<span data-ttu-id="97ad2-119">Выходные данные показывают объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="97ad2-119">The output shows the object that the cmdlet returns.</span></span>

### <span data-ttu-id="97ad2-120">Пример 2. Использование объекта параметров рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="97ad2-120">Example 2: Using a Workflow Options Object</span></span>

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="97ad2-121">Первые две команды создают новый объект конфигурации сеанса и регистрируют его.</span><span class="sxs-lookup"><span data-stu-id="97ad2-121">The first two commands create a new session configuration object and registers it.</span></span>

<span data-ttu-id="97ad2-122">Третья команда использует `Get-PSSessionConfiguration` командлет для получения конфигурации сеанса итворкфловс и `Format-List` для вывода всех свойств конфигурации сеанса в списке. Выходные данные показывают, что параметры рабочего процесса в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-122">The third command uses the `Get-PSSessionConfiguration` cmdlet to the get the ITWorkflows session configuration and the `Format-List` to display all properties of the session configuration in a list.The output shows that the workflow options in the session configuration.</span></span> <span data-ttu-id="97ad2-123">В частности, конфигурации сеанса имеет свойство **MaxSessionsPerWorkflow** со значением 10 и свойство **MaxDisconnectedSessions** со значением 200.</span><span class="sxs-lookup"><span data-stu-id="97ad2-123">Specifically, the session configuration has a **MaxSessionsPerWorkflow** property with a value of 10 and a **MaxDisconnectedSessions** property with a value of 200.</span></span>

## <span data-ttu-id="97ad2-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97ad2-124">PARAMETERS</span></span>

### <span data-ttu-id="97ad2-125">-ActivityProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="97ad2-125">-ActivityProcessIdleTimeoutSec</span></span>

<span data-ttu-id="97ad2-126">Определяет, как долго сохраняется каждый хост-процесс действия после того, как процесс становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="97ad2-126">Determines how long each activity host process is maintained after the process becomes idle.</span></span> <span data-ttu-id="97ad2-127">По истечении периода процесс закрывается.</span><span class="sxs-lookup"><span data-stu-id="97ad2-127">When the interval expires, the process closes.</span></span>

<span data-ttu-id="97ad2-128">Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="97ad2-128">Enter a value in seconds.</span></span> <span data-ttu-id="97ad2-129">Значение по умолчанию — 60.</span><span class="sxs-lookup"><span data-stu-id="97ad2-129">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-130">-AllowedActivity</span><span class="sxs-lookup"><span data-stu-id="97ad2-130">-AllowedActivity</span></span>

<span data-ttu-id="97ad2-131">Указывает действия, которые можно выполнять в сеансе.</span><span class="sxs-lookup"><span data-stu-id="97ad2-131">Specifies the activities that are permitted to run in the session.</span></span>

<span data-ttu-id="97ad2-132">Введите имена действий, уточненные пространством имен, например `Microsoft.Powershell.HyperV.Activities.*` .</span><span class="sxs-lookup"><span data-stu-id="97ad2-132">Enter namespace-qualified activity names, such as `Microsoft.Powershell.HyperV.Activities.*`.</span></span>
<span data-ttu-id="97ad2-133">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="97ad2-133">Wildcard characters are supported.</span></span> <span data-ttu-id="97ad2-134">Значение по умолчанию **PSDefaultActivities** включает в себя встроенные действия Windows Workflow Foundation и действия, представляющие основные командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97ad2-134">The default value, **PSDefaultActivities** , includes the built-in Windows Workflow Foundation activities and the activities that represent the Windows PowerShell Core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-135">-EnableValidation</span><span class="sxs-lookup"><span data-stu-id="97ad2-135">-EnableValidation</span></span>

<span data-ttu-id="97ad2-136">Проверяет, что все действия рабочих процессов в сеансе включены в список разрешенных действий.</span><span class="sxs-lookup"><span data-stu-id="97ad2-136">Verifies that all workflow activities in the session are included in the allowed activities list.</span></span>

<span data-ttu-id="97ad2-137">По умолчанию используется значение True.</span><span class="sxs-lookup"><span data-stu-id="97ad2-137">The default value is True.</span></span> <span data-ttu-id="97ad2-138">Чтобы отключить проверку, используйте следующий формат команды: `-EnableValidation:$false`.</span><span class="sxs-lookup"><span data-stu-id="97ad2-138">To disable validation, use the following command format: `-EnableValidation:$false`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-139">-MaxActivityProcesses</span><span class="sxs-lookup"><span data-stu-id="97ad2-139">-MaxActivityProcesses</span></span>

<span data-ttu-id="97ad2-140">Указывает максимальное число процессов, которые могут быть созданы в сеансе для поддержки действий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-140">Specifies the maximum number of processes that can be created in the session to support workflow activities.</span></span> <span data-ttu-id="97ad2-141">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="97ad2-141">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-142">-MaxConnectedSessions</span><span class="sxs-lookup"><span data-stu-id="97ad2-142">-MaxConnectedSessions</span></span>

<span data-ttu-id="97ad2-143">Указывает максимальное количество удаленных сеансов, находящихся в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="97ad2-143">Specifies the maximum number of remote sessions that are in an operational state.</span></span> <span data-ttu-id="97ad2-144">Эта квота применяется к сеансам, подключенным ко всем удаленным узлам (конечным компьютерам).</span><span class="sxs-lookup"><span data-stu-id="97ad2-144">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="97ad2-145">По умолчанию используется значение 100.</span><span class="sxs-lookup"><span data-stu-id="97ad2-145">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-146">-MaxDisconnectedSessions</span><span class="sxs-lookup"><span data-stu-id="97ad2-146">-MaxDisconnectedSessions</span></span>

<span data-ttu-id="97ad2-147">Указывает максимальное количество удаленных сеансов, находящихся в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="97ad2-147">Specifies the maximum number of remote sessions that are in a disconnected state.</span></span> <span data-ttu-id="97ad2-148">Эта квота применяется к сеансам, подключенным ко всем удаленным узлам (конечным компьютерам).</span><span class="sxs-lookup"><span data-stu-id="97ad2-148">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="97ad2-149">Значение по умолчанию ― 1000.</span><span class="sxs-lookup"><span data-stu-id="97ad2-149">The default value is 1000.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-150">-MaxPersistenceStoreSizeGB</span><span class="sxs-lookup"><span data-stu-id="97ad2-150">-MaxPersistenceStoreSizeGB</span></span>

<span data-ttu-id="97ad2-151">Указывает максимальный размер (в ГБ) хранилища сохраняемости, выделенного для выполняемых в сеансе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="97ad2-151">Specifies the maximum size, in gigabytes, of the persistence store allocated to workflows that run in the session.</span></span> <span data-ttu-id="97ad2-152">При превышении размера хранилище расширяется, чтобы сохранить все сохраненные данные, но при этом отображается предупреждение и в журнал событий рабочего процесса записывается сообщение.</span><span class="sxs-lookup"><span data-stu-id="97ad2-152">When the size is exceeded, the persistence store is expanded to save all persisted data, but a warning is displayed and a message is written to the workflow event log.</span></span> <span data-ttu-id="97ad2-153">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="97ad2-153">The default value is 10.</span></span>

<span data-ttu-id="97ad2-154">Хранилище сохраняемости содержит данные обо всех заданиях рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-154">The persistence store contains data for all workflow jobs.</span></span> <span data-ttu-id="97ad2-155">Возможность хранения данных позволяет возобновить задания без потери состояния.</span><span class="sxs-lookup"><span data-stu-id="97ad2-155">The ability to store data allows the jobs to resume without losing state.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-156">-MaxRunningWorkflows</span><span class="sxs-lookup"><span data-stu-id="97ad2-156">-MaxRunningWorkflows</span></span>

<span data-ttu-id="97ad2-157">Указывает максимальное число рабочих процессов, которые могут выполняться в сеансе одновременно.</span><span class="sxs-lookup"><span data-stu-id="97ad2-157">Specifies that maximum number of workflows that can run in the session concurrently.</span></span>
<span data-ttu-id="97ad2-158">Значение по умолчанию — 30.</span><span class="sxs-lookup"><span data-stu-id="97ad2-158">The default value is 30.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-159">-MaxSessionsPerRemoteNode</span><span class="sxs-lookup"><span data-stu-id="97ad2-159">-MaxSessionsPerRemoteNode</span></span>

<span data-ttu-id="97ad2-160">Указывает максимальное количество сеансов, которые могут быть подключены к каждому удаленному узлу (конечному компьютеру).</span><span class="sxs-lookup"><span data-stu-id="97ad2-160">Specifies the maximum number of sessions that can be connected to each remote node (target computer).</span></span> <span data-ttu-id="97ad2-161">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="97ad2-161">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-162">-MaxSessionsPerWorkflow</span><span class="sxs-lookup"><span data-stu-id="97ad2-162">-MaxSessionsPerWorkflow</span></span>

<span data-ttu-id="97ad2-163">Указывает максимальное количество сеансов, которые можно создать для поддержки каждого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-163">Specifies the maximum number of session that can be created to support each workflow.</span></span> <span data-ttu-id="97ad2-164">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="97ad2-164">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-165">-OutOfProcessActivity</span><span class="sxs-lookup"><span data-stu-id="97ad2-165">-OutOfProcessActivity</span></span>

<span data-ttu-id="97ad2-166">Определяет, какие разрешенные действия (указанные параметром **AllowedActivities** ) выполняются вне процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-166">Determines which allowed activities (specified by the **AllowedActivities** parameter) run out-of-process.</span></span> <span data-ttu-id="97ad2-167">Значение по умолчанию — **InlineScript**.</span><span class="sxs-lookup"><span data-stu-id="97ad2-167">The default value is **InlineScript**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-168">-PersistencePath</span><span class="sxs-lookup"><span data-stu-id="97ad2-168">-PersistencePath</span></span>

<span data-ttu-id="97ad2-169">Указывает расположение на диске, где хранится состояние рабочего процесса и данные.</span><span class="sxs-lookup"><span data-stu-id="97ad2-169">Specifies the location on disk where workflow state and data are stored.</span></span> <span data-ttu-id="97ad2-170">Хранение данных и состояния рабочего процесса позволяет приостанавливать и возобновлять рабочие процессы, а также восстанавливать работу после нарушений и сетевых ошибок.</span><span class="sxs-lookup"><span data-stu-id="97ad2-170">Storing the workflow state and data allows workflows to be suspended and resumed, and to recover from interruptions and network failures.</span></span>

<span data-ttu-id="97ad2-171">Значение по умолчанию — `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span><span class="sxs-lookup"><span data-stu-id="97ad2-171">The default value is `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-172">-PersistWithEncryption</span><span class="sxs-lookup"><span data-stu-id="97ad2-172">-PersistWithEncryption</span></span>

<span data-ttu-id="97ad2-173">Указывает, что рабочий процесс шифрует данные в хранилище сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="97ad2-173">Indicates that the workflow encrypts the data in the persistence store.</span></span> <span data-ttu-id="97ad2-174">Рекомендуется использовать эту функцию при хранении данных сохраняемости в общей сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="97ad2-174">Consider using this feature when storing persistence data in a network share.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-175">-RemoteNodeSessionIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="97ad2-175">-RemoteNodeSessionIdleTimeoutSec</span></span>

<span data-ttu-id="97ad2-176">Указывает продолжительность поддержки работоспособности сеанса, который подключен к удаленному узлу (конечному компьютеру), в случае бездействия.</span><span class="sxs-lookup"><span data-stu-id="97ad2-176">Specifies how long a session that is connected to a remote node (target computer) is maintained if it is idle.</span></span>

<span data-ttu-id="97ad2-177">Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="97ad2-177">Enter a value in seconds.</span></span> <span data-ttu-id="97ad2-178">Значение по умолчанию — 60.</span><span class="sxs-lookup"><span data-stu-id="97ad2-178">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-179">-SessionThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="97ad2-179">-SessionThrottleLimit</span></span>

<span data-ttu-id="97ad2-180">Указывает, сколько операций создается для поддержки всех рабочих процессов, запущенных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-180">Specifies how many operations are created to support all workflows started in the session.</span></span> <span data-ttu-id="97ad2-181">По умолчанию используется значение 100.</span><span class="sxs-lookup"><span data-stu-id="97ad2-181">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-182">-WorkflowShutdownTimeoutMSec</span><span class="sxs-lookup"><span data-stu-id="97ad2-182">-WorkflowShutdownTimeoutMSec</span></span>

<span data-ttu-id="97ad2-183">Указывает продолжительность поддержки работоспособности сеанса после принудительной приостановки всех рабочих процессов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="97ad2-183">Specifies how long the session is maintained after all workflows in the session are forcibly suspended.</span></span> <span data-ttu-id="97ad2-184">По истечении этого времени Windows PowerShell закрывает сеанс, даже если еще не приостановлены все рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="97ad2-184">When the timeout expires, Windows PowerShell closes the session, even if all workflows are not yet suspended.</span></span>

<span data-ttu-id="97ad2-185">Введите значение в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="97ad2-185">Enter a value in milliseconds.</span></span>
<span data-ttu-id="97ad2-186">Значение по умолчанию — 500.</span><span class="sxs-lookup"><span data-stu-id="97ad2-186">The default value is 500.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97ad2-187">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="97ad2-187">CommonParameters</span></span>

<span data-ttu-id="97ad2-188">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97ad2-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97ad2-189">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="97ad2-189">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="97ad2-190">Входные данные</span><span class="sxs-lookup"><span data-stu-id="97ad2-190">INPUTS</span></span>

### <span data-ttu-id="97ad2-191">Нет</span><span class="sxs-lookup"><span data-stu-id="97ad2-191">None</span></span>

<span data-ttu-id="97ad2-192">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="97ad2-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="97ad2-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="97ad2-193">OUTPUTS</span></span>

### <span data-ttu-id="97ad2-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="97ad2-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="97ad2-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="97ad2-195">NOTES</span></span>

<span data-ttu-id="97ad2-196">При превышении максимального значения, заданного параметром, команда на создание другого экземпляра в сеансе завершается ошибкой, если это не прописано в описании параметра.</span><span class="sxs-lookup"><span data-stu-id="97ad2-196">When the maximum value set by an option is exceeded, the command to create another instance in the session fails, unless noted in the parameter description.</span></span> <span data-ttu-id="97ad2-197">Например, если значение **MaxConnectedSessions** равно 100.</span><span class="sxs-lookup"><span data-stu-id="97ad2-197">For example, if the value of **MaxConnectedSessions** is 100.</span></span> <span data-ttu-id="97ad2-198">Команда на создание 101-го сеанса с удаленным узлом (конечным компьютером) завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="97ad2-198">The command to create the 101st session to a remote node (target computer) fails.</span></span>

<span data-ttu-id="97ad2-199">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="97ad2-199">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="97ad2-200">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="97ad2-200">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="97ad2-201">В частности, свойства конфигурации сеанса, включающие в себя объект **PSWorkflowExecutionOptions** , зависят от значений параметров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97ad2-201">In particular, the properties of session configurations that include a **PSWorkflowExecutionOptions** object vary based on the workflow option values.</span></span> <span data-ttu-id="97ad2-202">Например, если конфигурация сеанса включает в себя объект **PSWorkflowExecutionOptions** , который задает нестандартное значение для свойства **SessionThrottleLimit** , конфигурация сеанса имеет свойство **SessionThrottleLimit**.</span><span class="sxs-lookup"><span data-stu-id="97ad2-202">For example, if the session configuration includes a **PSWorkflowExecutionOptions** object that sets a non-default value for the **SessionThrottleLimit** property, the session configuration has a **SessionThrottleLimit** property.</span></span> <span data-ttu-id="97ad2-203">В противном случае это условие не выполняется.</span><span class="sxs-lookup"><span data-stu-id="97ad2-203">Otherwise, it does not.</span></span>

## <span data-ttu-id="97ad2-204">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="97ad2-204">RELATED LINKS</span></span>

[<span data-ttu-id="97ad2-205">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="97ad2-205">New-PSWorkflowSession</span></span>](New-PSWorkflowSession.md)

[<span data-ttu-id="97ad2-206">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="97ad2-206">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="97ad2-207">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="97ad2-207">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
