---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 85cbc9d012781873dddaf2a7d220a0e478dcbda2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601604"
---
# <span data-ttu-id="7f770-102">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7f770-102">Enter-PSHostProcess</span></span>

## <span data-ttu-id="7f770-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7f770-103">SYNOPSIS</span></span>
<span data-ttu-id="7f770-104">Подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="7f770-104">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="7f770-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f770-105">SYNTAX</span></span>

### <span data-ttu-id="7f770-106">Процессидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7f770-106">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7f770-107">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="7f770-107">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7f770-108">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="7f770-108">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7f770-109">пшостпроцессинфопараметерсет</span><span class="sxs-lookup"><span data-stu-id="7f770-109">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="7f770-110">пипенамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="7f770-110">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="7f770-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f770-111">DESCRIPTION</span></span>

<span data-ttu-id="7f770-112">`Enter-PSHostProcess`Командлет подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="7f770-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="7f770-113">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="7f770-113">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="7f770-114">Вместо создания нового процесса для размещения PowerShell и запуска удаленного сеанса удаленный интерактивный сеанс выполняется в существующем процессе, который уже выполняет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-114">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="7f770-115">При взаимодействии с удаленным сеансом в указанном процессе можно выполнить перечисление выполняющихся пространств выполнения, а затем выбрать пространство выполнения для отладки, выполнив команду `Debug-Runspace` или `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="7f770-115">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="7f770-116">В процессе, который необходимо ввести, должен быть размещен PowerShell (System.Management.Automation.dll).</span><span class="sxs-lookup"><span data-stu-id="7f770-116">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="7f770-117">Необходимо быть членом группы администраторов на компьютере, где находится процесс, или пользователь, выполняющий сценарий, запустивший процесс.</span><span class="sxs-lookup"><span data-stu-id="7f770-117">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="7f770-118">После выбора пространства выполнения для отладки для пространства выполнения будет открыт сеанс удаленной отладки, если в данный момент он выполняет команду или остановлен в отладчике.</span><span class="sxs-lookup"><span data-stu-id="7f770-118">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="7f770-119">Затем можно выполнить отладку скрипта пространства выполнения так же, как при отладке других сценариев удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="7f770-119">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="7f770-120">Отсоединитесь от сеанса отладки, а затем интерактивный сеанс с процессом, выполнив команду Exit дважды или остановите выполнение скрипта, запустив имеющуюся кнопку Quit отладчика.</span><span class="sxs-lookup"><span data-stu-id="7f770-120">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="7f770-121">Если указать процесс с помощью параметра **Name** и обнаружен только один процесс с указанным именем, то будет введен процесс.</span><span class="sxs-lookup"><span data-stu-id="7f770-121">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="7f770-122">Если найдено более одного процесса с указанным именем, PowerShell возвращает ошибку и перечисляет все обнаруженные процессы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="7f770-122">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="7f770-123">Для поддержки присоединения к процессам на удаленных компьютерах `Enter-PSHostProcess` командлет включен на указанном удаленном компьютере, чтобы можно было подключиться к локальному процессу в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-123">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="7f770-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="7f770-124">EXAMPLES</span></span>

### <span data-ttu-id="7f770-125">Пример 1. Начало отладки пространства выполнения в процессе интегрированной среды сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f770-125">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="7f770-126">В этом примере вы запускаете `Enter-PSHostProcess` из консоли PowerShell, чтобы войти в процесс интегрированной среды сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-126">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="7f770-127">В итоговом интерактивном сеансе можно найти пространство выполнения, которое необходимо отладить, выполнив `Get-Runspace` , а затем отладить пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f770-127">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="7f770-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f770-128">PARAMETERS</span></span>

### <span data-ttu-id="7f770-129">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="7f770-129">-AppDomainName</span></span>

<span data-ttu-id="7f770-130">Указывает имя домена приложения для подключения, если оно не указано, использует **дефаултаппдомаин**.</span><span class="sxs-lookup"><span data-stu-id="7f770-130">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="7f770-131">Используется `Get-PSHostProcessInfo` для вывода имен доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="7f770-131">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

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

### <span data-ttu-id="7f770-132">-Хостпроцессинфо</span><span class="sxs-lookup"><span data-stu-id="7f770-132">-HostProcessInfo</span></span>

<span data-ttu-id="7f770-133">Указывает объект **PSHostProcessInfo** , к которому можно подключиться с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-133">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="7f770-134">Используйте `Get-PSHostProcessInfo` для получения объекта.</span><span class="sxs-lookup"><span data-stu-id="7f770-134">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="7f770-135">-Id</span><span class="sxs-lookup"><span data-stu-id="7f770-135">-Id</span></span>

<span data-ttu-id="7f770-136">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="7f770-136">Specifies a process by the process ID.</span></span> <span data-ttu-id="7f770-137">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="7f770-137">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="7f770-138">-Name</span><span class="sxs-lookup"><span data-stu-id="7f770-138">-Name</span></span>

<span data-ttu-id="7f770-139">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="7f770-139">Specifies a process by the process name.</span></span> <span data-ttu-id="7f770-140">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="7f770-140">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="7f770-141">Имена процессов также можно получить из диалогового окна Свойства процесса в диспетчере задач.</span><span class="sxs-lookup"><span data-stu-id="7f770-141">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="7f770-142">-Process</span><span class="sxs-lookup"><span data-stu-id="7f770-142">-Process</span></span>

<span data-ttu-id="7f770-143">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="7f770-143">Specifies a process by the process object.</span></span> <span data-ttu-id="7f770-144">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="7f770-144">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="7f770-145">-Кустомпипенаме</span><span class="sxs-lookup"><span data-stu-id="7f770-145">-CustomPipeName</span></span>

<span data-ttu-id="7f770-146">Возвращает или задает имя настраиваемого именованного канала для подключения.</span><span class="sxs-lookup"><span data-stu-id="7f770-146">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="7f770-147">Обычно это используется в сочетании с `pwsh -CustomPipeName` .</span><span class="sxs-lookup"><span data-stu-id="7f770-147">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="7f770-148">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="7f770-148">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="7f770-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7f770-149">CommonParameters</span></span>

<span data-ttu-id="7f770-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f770-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f770-151">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7f770-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f770-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7f770-152">INPUTS</span></span>

### <span data-ttu-id="7f770-153">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7f770-153">System.Diagnostics.Process</span></span>

## <span data-ttu-id="7f770-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7f770-154">OUTPUTS</span></span>

## <span data-ttu-id="7f770-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7f770-155">NOTES</span></span>

<span data-ttu-id="7f770-156">`Enter-PSHostProcess` невозможно ввести процесс сеанса PowerShell, в котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="7f770-156">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="7f770-157">Однако можно ввести процесс другого сеанса PowerShell или сеанса интегрированной среды сценариев PowerShell, который выполняется в то же время, что и сеанс, в котором выполняется `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="7f770-157">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="7f770-158">`Enter-PSHostProcess` может вводить только процессы, в которых размещается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-158">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="7f770-159">То есть они загрузили подсистему PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f770-159">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="7f770-160">Чтобы выйти из процесса в процессе, введите команду **Exit** и нажмите клавишу <kbd>Ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7f770-160">To exit a process from within the process, type **exit**, and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="7f770-161">До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком.</span><span class="sxs-lookup"><span data-stu-id="7f770-161">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="7f770-162">Эта возможность была ограничена сеансами через WinRM.</span><span class="sxs-lookup"><span data-stu-id="7f770-162">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="7f770-163">PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="7f770-163">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="7f770-164">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7f770-164">RELATED LINKS</span></span>

[<span data-ttu-id="7f770-165">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7f770-165">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="7f770-166">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="7f770-166">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)

