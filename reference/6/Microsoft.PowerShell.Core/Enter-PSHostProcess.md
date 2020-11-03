---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: dcc0fc0ddb9486d4bf1f24b7366622c011266a04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229286"
---
# <span data-ttu-id="f0039-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="f0039-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="f0039-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f0039-104">SYNOPSIS</span></span>
<span data-ttu-id="f0039-105">Подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="f0039-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="f0039-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f0039-106">SYNTAX</span></span>

### <span data-ttu-id="f0039-107">Процессидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f0039-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="f0039-108">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0039-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="f0039-109">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0039-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="f0039-110">пшостпроцессинфопараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0039-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="f0039-111">пипенамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0039-111">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="f0039-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f0039-112">DESCRIPTION</span></span>

<span data-ttu-id="f0039-113">`Enter-PSHostProcess`Командлет подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="f0039-113">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="f0039-114">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="f0039-114">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="f0039-115">Вместо создания нового процесса для размещения PowerShell и запуска удаленного сеанса удаленный интерактивный сеанс выполняется в существующем процессе, который уже выполняет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-115">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="f0039-116">При взаимодействии с удаленным сеансом в указанном процессе можно выполнить перечисление выполняющихся пространств выполнения, а затем выбрать пространство выполнения для отладки, выполнив команду `Debug-Runspace` или `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="f0039-116">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="f0039-117">В процессе, который необходимо ввести, должен быть размещен PowerShell (System.Management.Automation.dll).</span><span class="sxs-lookup"><span data-stu-id="f0039-117">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="f0039-118">Необходимо быть членом группы администраторов на компьютере, где находится процесс, или пользователь, выполняющий сценарий, запустивший процесс.</span><span class="sxs-lookup"><span data-stu-id="f0039-118">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="f0039-119">После выбора пространства выполнения для отладки для пространства выполнения будет открыт сеанс удаленной отладки, если в данный момент он выполняет команду или остановлен в отладчике.</span><span class="sxs-lookup"><span data-stu-id="f0039-119">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="f0039-120">Затем можно выполнить отладку скрипта пространства выполнения так же, как при отладке других сценариев удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0039-120">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="f0039-121">Отсоединитесь от сеанса отладки, а затем интерактивный сеанс с процессом, выполнив команду Exit дважды или остановите выполнение скрипта, запустив имеющуюся кнопку Quit отладчика.</span><span class="sxs-lookup"><span data-stu-id="f0039-121">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="f0039-122">Если указать процесс с помощью параметра **Name** и обнаружен только один процесс с указанным именем, то будет введен процесс.</span><span class="sxs-lookup"><span data-stu-id="f0039-122">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="f0039-123">Если найдено более одного процесса с указанным именем, PowerShell возвращает ошибку и перечисляет все обнаруженные процессы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="f0039-123">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="f0039-124">Для поддержки присоединения к процессам на удаленных компьютерах `Enter-PSHostProcess` командлет включен на указанном удаленном компьютере, чтобы можно было подключиться к локальному процессу в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-124">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="f0039-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0039-125">EXAMPLES</span></span>

### <span data-ttu-id="f0039-126">Пример 1. Начало отладки пространства выполнения в процессе интегрированной среды сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0039-126">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="f0039-127">В этом примере вы запускаете `Enter-PSHostProcess` из консоли PowerShell, чтобы войти в процесс интегрированной среды сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-127">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="f0039-128">В итоговом интерактивном сеансе можно найти пространство выполнения, которое необходимо отладить, выполнив `Get-Runspace` , а затем отладить пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0039-128">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## <span data-ttu-id="f0039-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f0039-129">PARAMETERS</span></span>

### <span data-ttu-id="f0039-130">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="f0039-130">-AppDomainName</span></span>

<span data-ttu-id="f0039-131">Указывает имя домена приложения для подключения, если оно не указано, использует **дефаултаппдомаин**.</span><span class="sxs-lookup"><span data-stu-id="f0039-131">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="f0039-132">Используется `Get-PSHostProcessInfo` для вывода имен доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="f0039-132">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-133">-Хостпроцессинфо</span><span class="sxs-lookup"><span data-stu-id="f0039-133">-HostProcessInfo</span></span>

<span data-ttu-id="f0039-134">Указывает объект **PSHostProcessInfo** , к которому можно подключиться с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-134">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="f0039-135">Используйте `Get-PSHostProcessInfo` для получения объекта.</span><span class="sxs-lookup"><span data-stu-id="f0039-135">Use `Get-PSHostProcessInfo` to get the object.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-136">-Id</span><span class="sxs-lookup"><span data-stu-id="f0039-136">-Id</span></span>

<span data-ttu-id="f0039-137">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="f0039-137">Specifies a process by the process ID.</span></span> <span data-ttu-id="f0039-138">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="f0039-138">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-139">-Name</span><span class="sxs-lookup"><span data-stu-id="f0039-139">-Name</span></span>

<span data-ttu-id="f0039-140">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="f0039-140">Specifies a process by the process name.</span></span> <span data-ttu-id="f0039-141">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="f0039-141">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="f0039-142">Имена процессов также можно получить из диалогового окна Свойства процесса в диспетчере задач.</span><span class="sxs-lookup"><span data-stu-id="f0039-142">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-143">-Process</span><span class="sxs-lookup"><span data-stu-id="f0039-143">-Process</span></span>

<span data-ttu-id="f0039-144">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="f0039-144">Specifies a process by the process object.</span></span> <span data-ttu-id="f0039-145">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f0039-145">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-146">-Кустомпипенаме</span><span class="sxs-lookup"><span data-stu-id="f0039-146">-CustomPipeName</span></span>

<span data-ttu-id="f0039-147">Возвращает или задает имя настраиваемого именованного канала для подключения.</span><span class="sxs-lookup"><span data-stu-id="f0039-147">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="f0039-148">Обычно это используется в сочетании с `pwsh -CustomPipeName` .</span><span class="sxs-lookup"><span data-stu-id="f0039-148">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="f0039-149">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="f0039-149">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0039-150">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f0039-150">CommonParameters</span></span>

<span data-ttu-id="f0039-151">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f0039-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f0039-152">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f0039-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f0039-153">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f0039-153">INPUTS</span></span>

### <span data-ttu-id="f0039-154">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="f0039-154">System.Diagnostics.Process</span></span>

## <span data-ttu-id="f0039-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f0039-155">OUTPUTS</span></span>

## <span data-ttu-id="f0039-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f0039-156">NOTES</span></span>

<span data-ttu-id="f0039-157">`Enter-PSHostProcess` невозможно ввести процесс сеанса PowerShell, в котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="f0039-157">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="f0039-158">Однако можно ввести процесс другого сеанса PowerShell или сеанса интегрированной среды сценариев PowerShell, который выполняется в то же время, что и сеанс, в котором выполняется `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="f0039-158">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="f0039-159">`Enter-PSHostProcess` может вводить только процессы, в которых размещается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-159">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="f0039-160">То есть они загрузили подсистему PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0039-160">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="f0039-161">Чтобы выйти из процесса в процессе, введите команду **Exit** и нажмите клавишу <kbd>Ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f0039-161">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

## <span data-ttu-id="f0039-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f0039-162">RELATED LINKS</span></span>

[<span data-ttu-id="f0039-163">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="f0039-163">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="f0039-164">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="f0039-164">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)
