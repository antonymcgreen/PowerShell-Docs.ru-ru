---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 56b8cef1911d1365f9568483921bfb49fbc32451
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226701"
---
# <span data-ttu-id="c1f59-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="c1f59-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="c1f59-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1f59-104">SYNOPSIS</span></span>
<span data-ttu-id="c1f59-105">Подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="c1f59-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="c1f59-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1f59-106">SYNTAX</span></span>

### <span data-ttu-id="c1f59-107">Процессидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c1f59-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c1f59-108">процесспараметерсет</span><span class="sxs-lookup"><span data-stu-id="c1f59-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c1f59-109">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="c1f59-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c1f59-110">пшостпроцессинфопараметерсет</span><span class="sxs-lookup"><span data-stu-id="c1f59-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="c1f59-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1f59-111">DESCRIPTION</span></span>

<span data-ttu-id="c1f59-112">`Enter-PSHostProcess`Командлет подключается к интерактивному сеансу с локальным процессом и входит в него.</span><span class="sxs-lookup"><span data-stu-id="c1f59-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span>

<span data-ttu-id="c1f59-113">Вместо создания нового процесса для размещения PowerShell и запуска удаленного сеанса удаленный интерактивный сеанс выполняется в существующем процессе, который уже выполняет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-113">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="c1f59-114">При взаимодействии с удаленным сеансом в указанном процессе можно выполнить перечисление выполняющихся пространств выполнения, а затем выбрать пространство выполнения для отладки, выполнив команду `Debug-Runspace` или `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="c1f59-114">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="c1f59-115">В процессе, который необходимо ввести, должен быть размещен PowerShell (System.Management.Automation.dll).</span><span class="sxs-lookup"><span data-stu-id="c1f59-115">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="c1f59-116">Необходимо быть членом группы администраторов на компьютере, где находится процесс, или пользователь, выполняющий сценарий, запустивший процесс.</span><span class="sxs-lookup"><span data-stu-id="c1f59-116">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="c1f59-117">После выбора пространства выполнения для отладки для пространства выполнения будет открыт сеанс удаленной отладки, если в данный момент он выполняет команду или остановлен в отладчике.</span><span class="sxs-lookup"><span data-stu-id="c1f59-117">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="c1f59-118">Затем можно выполнить отладку скрипта пространства выполнения так же, как при отладке других сценариев удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1f59-118">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="c1f59-119">Отсоединитесь от сеанса отладки, а затем интерактивный сеанс с процессом, выполнив команду Exit дважды или остановите выполнение скрипта, запустив имеющуюся кнопку Quit отладчика.</span><span class="sxs-lookup"><span data-stu-id="c1f59-119">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="c1f59-120">Если указать процесс с помощью параметра **Name** и обнаружен только один процесс с указанным именем, то будет введен процесс.</span><span class="sxs-lookup"><span data-stu-id="c1f59-120">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="c1f59-121">Если найдено более одного процесса с указанным именем, PowerShell возвращает ошибку и перечисляет все обнаруженные процессы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c1f59-121">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="c1f59-122">Для поддержки присоединения к процессам на удаленных компьютерах `Enter-PSHostProcess` командлет включен на указанном удаленном компьютере, чтобы можно было подключиться к локальному процессу в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-122">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="c1f59-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1f59-123">EXAMPLES</span></span>

### <span data-ttu-id="c1f59-124">Пример 1. Начало отладки пространства выполнения в процессе интегрированной среды сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f59-124">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="c1f59-125">В этом примере вы запускаете `Enter-PSHostProcess` из консоли PowerShell, чтобы войти в процесс интегрированной среды сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-125">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="c1f59-126">В итоговом интерактивном сеансе можно найти пространство выполнения, которое необходимо отладить, выполнив `Get-Runspace` , а затем отладить пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="c1f59-126">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="c1f59-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1f59-127">PARAMETERS</span></span>

### <span data-ttu-id="c1f59-128">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="c1f59-128">-AppDomainName</span></span>

<span data-ttu-id="c1f59-129">Указывает имя домена приложения для подключения, если оно не указано, использует **дефаултаппдомаин**.</span><span class="sxs-lookup"><span data-stu-id="c1f59-129">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="c1f59-130">Используется `Get-PSHostProcessInfo` для вывода имен доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="c1f59-130">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1f59-131">-Хостпроцессинфо</span><span class="sxs-lookup"><span data-stu-id="c1f59-131">-HostProcessInfo</span></span>

<span data-ttu-id="c1f59-132">Указывает объект **PSHostProcessInfo** , к которому можно подключиться с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-132">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="c1f59-133">Используйте `Get-PSHostProcessInfo` для получения объекта.</span><span class="sxs-lookup"><span data-stu-id="c1f59-133">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="c1f59-134">-Id</span><span class="sxs-lookup"><span data-stu-id="c1f59-134">-Id</span></span>

<span data-ttu-id="c1f59-135">Указывает процесс по ИДЕНТИФИКАТОРу процесса.</span><span class="sxs-lookup"><span data-stu-id="c1f59-135">Specifies a process by the process ID.</span></span> <span data-ttu-id="c1f59-136">Чтобы получить идентификатор процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="c1f59-136">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="c1f59-137">-Name</span><span class="sxs-lookup"><span data-stu-id="c1f59-137">-Name</span></span>

<span data-ttu-id="c1f59-138">Задает процесс по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="c1f59-138">Specifies a process by the process name.</span></span> <span data-ttu-id="c1f59-139">Чтобы получить имя процесса, выполните `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="c1f59-139">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="c1f59-140">Имена процессов также можно получить из диалогового окна Свойства процесса в диспетчере задач.</span><span class="sxs-lookup"><span data-stu-id="c1f59-140">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="c1f59-141">-Process</span><span class="sxs-lookup"><span data-stu-id="c1f59-141">-Process</span></span>

<span data-ttu-id="c1f59-142">Указывает процесс в объекте процесса.</span><span class="sxs-lookup"><span data-stu-id="c1f59-142">Specifies a process by the process object.</span></span> <span data-ttu-id="c1f59-143">Самый простой способ использовать этот параметр — Сохранить результаты `Get-Process` команды, которая возвращает процесс, который необходимо ввести в переменную, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="c1f59-143">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="c1f59-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1f59-144">CommonParameters</span></span>

<span data-ttu-id="c1f59-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1f59-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1f59-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1f59-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1f59-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1f59-147">INPUTS</span></span>

### <span data-ttu-id="c1f59-148">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="c1f59-148">System.Diagnostics.Process</span></span>

## <span data-ttu-id="c1f59-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1f59-149">OUTPUTS</span></span>

## <span data-ttu-id="c1f59-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1f59-150">NOTES</span></span>

<span data-ttu-id="c1f59-151">`Enter-PSHostProcess` невозможно ввести процесс сеанса PowerShell, в котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="c1f59-151">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="c1f59-152">Однако можно ввести процесс другого сеанса PowerShell или сеанса интегрированной среды сценариев PowerShell, который выполняется в то же время, что и сеанс, в котором выполняется `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="c1f59-152">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="c1f59-153">`Enter-PSHostProcess` может вводить только процессы, в которых размещается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-153">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="c1f59-154">То есть они загрузили подсистему PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f59-154">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="c1f59-155">Чтобы выйти из процесса в процессе, введите команду **Exit** и нажмите клавишу <kbd>Ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="c1f59-155">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

## <span data-ttu-id="c1f59-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1f59-156">RELATED LINKS</span></span>

[<span data-ttu-id="c1f59-157">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="c1f59-157">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="c1f59-158">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="c1f59-158">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)
