---
title: Удаленное взаимодействие PowerShell
description: Существует множество различных способов выполнения команд на удаленных компьютерах в PowerShell.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0e467a41282b261c56a89578dbc841725f59a6e0
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99603100"
---
# <a name="chapter-8---powershell-remoting"></a><span data-ttu-id="ad81b-103">Глава 8. Удаленное взаимодействие PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad81b-103">Chapter 8 - PowerShell remoting</span></span>

<span data-ttu-id="ad81b-104">В PowerShell доступно множество различных способов выполнения команд на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ad81b-104">PowerShell has many different ways to run commands against remote computers.</span></span> <span data-ttu-id="ad81b-105">В последней главе вы узнали, как удаленно запрашивать WMI с помощью командлетов CIM.</span><span class="sxs-lookup"><span data-stu-id="ad81b-105">In the last chapter, you saw how to remotely query WMI using the CIM cmdlets.</span></span> <span data-ttu-id="ad81b-106">PowerShell также содержит несколько командлетов со встроенным параметром **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="ad81b-106">PowerShell also includes several cmdlets that have a built-in **ComputerName** parameter.</span></span>

<span data-ttu-id="ad81b-107">Как показано в следующем примере, `Get-Command` можно использовать с параметром **ParameterName**, чтобы определить, какие команды имеют параметр **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="ad81b-107">As shown in the following example, `Get-Command` can be used with the **ParameterName** parameter to determine what commands have a **ComputerName** parameter.</span></span>

```powershell
Get-Command -ParameterName ComputerName
```

```Output
CommandType Name                        Version Source
----------- ----                        ------- ------
Cmdlet      Connect-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Connect-WSMan               7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Disconnect-WSMan            7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Enter-PSSession             7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-CimAssociatedInstance   7.0.0.0 CimCmdlets
Cmdlet      Get-CimClass                7.0.0.0 CimCmdlets
Cmdlet      Get-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Get-CimSession              7.0.0.0 CimCmdlets
Cmdlet      Get-Counter                 7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-HotFix                  7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Get-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-WinEvent                7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Invoke-CimMethod            7.0.0.0 CimCmdlets
Cmdlet      Invoke-Command              7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Invoke-WSManAction          7.0.0.0 Microsoft.WSMan.Management
Cmdlet      New-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      New-CimSession              7.0.0.0 CimCmdlets
Cmdlet      New-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      New-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Receive-Job                 7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Receive-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Register-CimIndicationEvent 7.0.0.0 CimCmdlets
Cmdlet      Remove-CimInstance          7.0.0.0 CimCmdlets
Cmdlet      Remove-CimSession           7.0.0.0 CimCmdlets
Cmdlet      Remove-PSSession            7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Remove-WSManInstance        7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Rename-Computer             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Restart-Computer            7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Send-MailMessage            7.0.0.0 Microsoft.PowerShell.Utility
Cmdlet      Set-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Set-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Stop-Computer               7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-Connection             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-WSMan                  7.0.0.0 Microsoft.WSMan.Management
```

<span data-ttu-id="ad81b-108">Параметр **ComputerName** есть у команд `Get-Process` и `Get-Hotfix`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-108">Commands such as `Get-Process` and `Get-Hotfix` have a **ComputerName** parameter.</span></span> <span data-ttu-id="ad81b-109">Следует отметить, что для корпорации Майкрософт это не то долгосрочное направление, которого следует придерживаться для выполнения команд на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ad81b-109">This isn't the long-term direction that Microsoft is heading for running commands against remote computers.</span></span> <span data-ttu-id="ad81b-110">Даже если вы нашли команду с параметром **ComputerName**, скорее всего, вам потребуется указать альтернативные учетные данные и у команды не будет параметра **Credential**.</span><span class="sxs-lookup"><span data-stu-id="ad81b-110">Even if you find a command that has a **ComputerName** parameter, chances are that you'll need to specify alternate credentials and it won't have a **Credential** parameter.</span></span> <span data-ttu-id="ad81b-111">Если вы решили запустить PowerShell из учетной записи с повышенными привилегиями, брандмауэр между вами и удаленным компьютером может заблокировать запрос.</span><span class="sxs-lookup"><span data-stu-id="ad81b-111">And if you decided to run PowerShell from an elevated account, a firewall between you and the remote computer can block the request.</span></span>

<span data-ttu-id="ad81b-112">Чтобы использовать команды удаленного взаимодействия PowerShell, которые демонстрируются в этой главе, необходимо включить удаленное взаимодействие PowerShell на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-112">To use the PowerShell remoting commands that are demonstrated in this chapter, PowerShell remoting must be enabled on the remote computer.</span></span> <span data-ttu-id="ad81b-113">Это можно сделать с помощью командлета `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-113">Use the `Enable-PSRemoting` cmdlet to enable PowerShell remoting.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WinRM has been updated to receive requests.
WinRM service type changed successfully.
WinRM service started.

WinRM has been updated for remote management.
WinRM firewall exception enabled.
```

## <a name="one-to-one-remoting"></a><span data-ttu-id="ad81b-114">Удаленное взаимодействие "один к одному"</span><span class="sxs-lookup"><span data-stu-id="ad81b-114">One-To-One Remoting</span></span>

<span data-ttu-id="ad81b-115">Если вы хотите, чтобы удаленный сеанс был интерактивным, то в этом случае подойдет удаленное взаимодействие "один к одному".</span><span class="sxs-lookup"><span data-stu-id="ad81b-115">If you want your remote session to be interactive, then one-to-one remoting is what you want.</span></span>
<span data-ttu-id="ad81b-116">Этот тип удаленного взаимодействия предоставляется с помощью командлета `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-116">This type of remoting is provided via the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="ad81b-117">В последней главе учетные данные администратора домена были сохранены в переменной с именем `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-117">In the last chapter, I stored my domain admin credentials in a variable named `$Cred`.</span></span> <span data-ttu-id="ad81b-118">Если вы еще не сделали этого, сохраните учетные данные администратора домена в переменной `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-118">If you haven't already done so, go ahead and store your domain admin credentials in the `$Cred` variable.</span></span>

<span data-ttu-id="ad81b-119">После этого вы сможете ввести учетные данные один раз и использовать их для каждой команды в активном текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad81b-119">This allows you to enter the credentials once and use them on a per command basis as long as your current PowerShell session is active.</span></span>

```powershell
$Cred = Get-Credential
```

<span data-ttu-id="ad81b-120">Создайте сеанс удаленного взаимодействия PowerShell "один к одному" с контроллером домена DC01.</span><span class="sxs-lookup"><span data-stu-id="ad81b-120">Create a one-to-one PowerShell remoting session to the domain controller named dc01.</span></span>

```powershell
Enter-PSSession -ComputerName dc01 -Credential $Cred
```

```Output
[dc01]: PS C:\Users\Administrator\Documents>
```

<span data-ttu-id="ad81b-121">Обратите внимание, что в предыдущем примере перед запросом PowerShell стоит `[dc01]`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-121">Notice that in the previous example that the PowerShell prompt is preceded by `[dc01]`.</span></span> <span data-ttu-id="ad81b-122">Это означает, что вы находитесь в интерактивном сеансе PowerShell с удаленным компьютером dc01.</span><span class="sxs-lookup"><span data-stu-id="ad81b-122">This means you're in an interactive PowerShell session to the remote computer named dc01.</span></span> <span data-ttu-id="ad81b-123">Все запускаемые команды выполняются на компьютере dc01, а не на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-123">Any commands you execute run on dc01, not on your local computer.</span></span> <span data-ttu-id="ad81b-124">Кроме того, помните, что у вас есть доступ только к командам PowerShell, которые существуют на удаленном, а не на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-124">Also, keep in mind that you only have access to the PowerShell commands that exist on the remote computer and not the ones on your local computer.</span></span> <span data-ttu-id="ad81b-125">Иными словами, если на компьютере установлены дополнительные модули, они недоступны на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-125">In other words, if you've installed additional modules on your computer, they aren't accessible on the remote computer.</span></span>

<span data-ttu-id="ad81b-126">При подключении к удаленному компьютеру в рамках интерактивного сеанса удаленного взаимодействия PowerShell "один к одному" вы фактически находитесь на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-126">When you're connected to a remote computer via a one-to-one interactive PowerShell remoting session, you're effectively sitting at the remote computer.</span></span> <span data-ttu-id="ad81b-127">Все объекты являются обычными объектами, аналогичными тем, с которыми вы уже работали.</span><span class="sxs-lookup"><span data-stu-id="ad81b-127">The objects are normal objects just like the ones you've been working with throughout this entire book.</span></span>

```powershell
[dc01]:  Get-Process | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
[dc01]:
```

<span data-ttu-id="ad81b-128">Завершив работу на удаленном компьютере, выйдите из сеанса удаленного взаимодействия "один к одному" с помощью командлета `Exit-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-128">When you're done working with the remote computer, exit the one-to-one remoting session by using the `Exit-PSSession` cmdlet.</span></span>

```powershell
[dc01]:  Exit-PSSession
```

## <a name="one-to-many-remoting"></a><span data-ttu-id="ad81b-129">Удаленное взаимодействие "один ко многим"</span><span class="sxs-lookup"><span data-stu-id="ad81b-129">One-To-Many Remoting</span></span>

<span data-ttu-id="ad81b-130">Иногда может потребоваться выполнить задачу в интерактивном режиме на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-130">Sometimes you may need to perform a task interactively on a remote computer.</span></span> <span data-ttu-id="ad81b-131">Удаленное взаимодействие гораздо более эффективно при выполнении задачи на нескольких удаленных компьютерах одновременно.</span><span class="sxs-lookup"><span data-stu-id="ad81b-131">But remoting is much more powerful when performing a task on multiple remote computers at the same time.</span></span> <span data-ttu-id="ad81b-132">С помощью командлета `Invoke-Command` выполните команду на одном удаленном компьютере или нескольких одновременно.</span><span class="sxs-lookup"><span data-stu-id="ad81b-132">Use the `Invoke-Command` cmdlet to run a command against one or more remote computers at the same time.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="ad81b-133">В предыдущем примере на три сервера были отправлены запросы состояния службы времени Windows.</span><span class="sxs-lookup"><span data-stu-id="ad81b-133">In the previous example, three servers were queried for the status of the Windows Time service.</span></span> <span data-ttu-id="ad81b-134">Командлет `Get-Service` был помещен в блок сценария `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-134">The `Get-Service` cmdlet was placed inside the script block of `Invoke-Command`.</span></span> <span data-ttu-id="ad81b-135">На самом деле сценарий `Get-Service` выполняется на удаленном компьютере и результаты возвращаются на локальный компьютер в виде десериализованных объектов.</span><span class="sxs-lookup"><span data-stu-id="ad81b-135">`Get-Service` actually runs on the remote computer and the results are returned to your local computer as deserialized objects.</span></span>

<span data-ttu-id="ad81b-136">Передача предыдущей команды в `Get-Member` подтверждает, что результаты действительно десериализованы.</span><span class="sxs-lookup"><span data-stu-id="ad81b-136">Piping the previous command to `Get-Member` shows that the results are indeed deserialized objects.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred | Get-Member
```

```Output
   TypeName: Deserialized.System.ServiceProcess.ServiceController

Name                MemberType   Definition
----                ----------   ----------
GetType             Method       type GetType()
ToString            Method       string ToString(), string ToString(string format, Sys...
Name                NoteProperty string Name=W32time
PSComputerName      NoteProperty string PSComputerName=sql02
PSShowComputerName  NoteProperty bool PSShowComputerName=True
RequiredServices    NoteProperty Deserialized.System.ServiceProcess.ServiceController[...
RunspaceId          NoteProperty guid RunspaceId=570313c4-ac84-4109-bf67-c6b33236af0a
CanPauseAndContinue Property     System.Boolean {get;set;}
CanShutdown         Property     System.Boolean {get;set;}
CanStop             Property     System.Boolean {get;set;}
Container           Property      {get;set;}
DependentServices   Property     Deserialized.System.ServiceProcess.ServiceController[...
DisplayName         Property     System.String {get;set;}
MachineName         Property     System.String {get;set;}
ServiceHandle       Property     System.String {get;set;}
ServiceName         Property     System.String {get;set;}
ServicesDependedOn  Property     Deserialized.System.ServiceProcess.ServiceController[...
ServiceType         Property     System.String {get;set;}
Site                Property      {get;set;}
StartType           Property     System.String {get;set;}
Status              Property     System.String {get;set;}
```

<span data-ttu-id="ad81b-137">Обратите внимание, что в десериализованных объектах отсутствует большинство методов.</span><span class="sxs-lookup"><span data-stu-id="ad81b-137">Notice that the majority of the methods are missing on deserialized objects.</span></span> <span data-ttu-id="ad81b-138">Это значит, что они не являются активными объектами, они инертны.</span><span class="sxs-lookup"><span data-stu-id="ad81b-138">This means they're not live objects; they're inert.</span></span> <span data-ttu-id="ad81b-139">Нельзя запускать или останавливать службу с помощью десериализованного объекта, так как он является моментальным снимком состояния этого объекта на момент выполнения команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-139">You can't start or stop a service using a deserialized object because it's a snapshot of the state of that object the point when the command ran on the remote computer.</span></span>

<span data-ttu-id="ad81b-140">Это не значит, что вы не можете запускать или прекращать работу службы с помощью метода `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-140">That doesn't mean you can't start or stop a service using a method with `Invoke-Command` though.</span></span> <span data-ttu-id="ad81b-141">Это просто значит, что метод должен быть вызван в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ad81b-141">It just means that the method has to be called in the remote session.</span></span>

<span data-ttu-id="ad81b-142">Чтобы доказать это, далее я остановлю службу времени Windows на всех трех удаленных серверах с помощью метода **Stop()** .</span><span class="sxs-lookup"><span data-stu-id="ad81b-142">I'll stop the Windows Time service on all three of those remote servers using the **Stop()** method to prove this point.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {(Get-Service -Name W32time).Stop()} -Credential $Cred
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="ad81b-143">Как отмечалось в предыдущей главе, если для выполнения задачи существует командлет, рекомендуется использовать его, а не метод.</span><span class="sxs-lookup"><span data-stu-id="ad81b-143">As mentioned in a previous chapter, if a cmdlet exists for accomplishing a task, I recommend using it instead of using a method.</span></span> <span data-ttu-id="ad81b-144">В предыдущем сценарии вместо метода остановки советую выполнить командлет `Stop-Service`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-144">In the previous scenario, I recommend using the `Stop-Service` cmdlet instead of the stop method.</span></span> <span data-ttu-id="ad81b-145">Чтобы доказать свою точку зрения, я решил использовать метод **Stop()** , так как многие люди ошибочно полагают, что в рамках удаленного взаимодействия PowerShell вызывать методы невозможно.</span><span class="sxs-lookup"><span data-stu-id="ad81b-145">I chose to use the **Stop()** method to prove a point since many people are under the misconception that methods can't be called when using PowerShell remoting.</span></span> <span data-ttu-id="ad81b-146">Их нельзя вызывать в возвращаемом объекте, потому что он десериализован, но можно вызывать в самом удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ad81b-146">They can't be called on the object that's returned because it's deserialized, but they can be called in the remote session itself.</span></span>

## <a name="powershell-sessions"></a><span data-ttu-id="ad81b-147">Сеансы PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad81b-147">PowerShell Sessions</span></span>

<span data-ttu-id="ad81b-148">В последнем примере в предыдущем разделе выполнялись две команды с помощью командлета `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="ad81b-148">In the last example in the previous section, I ran two commands using the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="ad81b-149">Это означает, что для их запуска прошлось бы настроить два отдельных сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad81b-149">That means two separate sessions had to be set up and torn down to run those two commands.</span></span>

<span data-ttu-id="ad81b-150">Подобно сеансам CIM, обсуждаемым в главе 7, сеанс PowerShell на удаленном компьютере можно использовать для запуска нескольких команд на удаленном компьютере без дополнительных затрат на создание нового сеанса для каждой отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="ad81b-150">Similar to the CIM sessions discussed in Chapter 7, a PowerShell session to a remote computer can be used to run multiple commands against the remote computer without the overhead of a new session for each individual command.</span></span>

<span data-ttu-id="ad81b-151">Создайте сеанс PowerShell с каждым из трех компьютеров, с которыми мы работали в этой главе, — DC01, SQL02 и WEB01.</span><span class="sxs-lookup"><span data-stu-id="ad81b-151">Create a PowerShell session to each of the three computers we've been working with in this chapter, DC01, SQL02, and WEB01.</span></span>

```powershell
$Session = New-PSSession -ComputerName dc01, sql02, web01 -Credential $Cred
```

<span data-ttu-id="ad81b-152">С помощью переменной `$Session` запустите службу времени Windows с использованием метода и проверьте состояние службы.</span><span class="sxs-lookup"><span data-stu-id="ad81b-152">Now use the variable named `$Session` to start the Windows Time service using a method and check the status of the service.</span></span>

```powershell
Invoke-Command -Session $Session {(Get-Service -Name W32time).Start()}
Invoke-Command -Session $Session {Get-Service -Name W32time}
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="ad81b-153">После создания сеанса с использованием альтернативных учетных данных указывать учетные данные при каждом выполнении команды не требуется.</span><span class="sxs-lookup"><span data-stu-id="ad81b-153">Once the session is created using alternate credentials, it's no longer necessary to specify the credentials each time a command is run.</span></span>

<span data-ttu-id="ad81b-154">Завершив работу с сеансами, не забудьте удалить их.</span><span class="sxs-lookup"><span data-stu-id="ad81b-154">When you're finished using the sessions, be sure to remove them.</span></span>

```powershell
Get-PSSession | Remove-PSSession
```

## <a name="summary"></a><span data-ttu-id="ad81b-155">Сводка</span><span class="sxs-lookup"><span data-stu-id="ad81b-155">Summary</span></span>

<span data-ttu-id="ad81b-156">В этой главе вы узнали об удаленном взаимодействии PowerShell, научились выполнять команды в интерактивном сеансе с одним удаленным компьютером и поняли, как выполнять команды на нескольких компьютерах с помощью удаленного взаимодействия "один ко многим".</span><span class="sxs-lookup"><span data-stu-id="ad81b-156">In this chapter you've learned about PowerShell remoting, how to run commands in an interactive session with one remote computer, and how to run commands against multiple computers using one-to-many remoting.</span></span> <span data-ttu-id="ad81b-157">Вы также узнали о преимуществах использования сеанса PowerShell при выполнении нескольких команд на одном удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad81b-157">You've also learned the benefits of using a PowerShell session when running multiple commands against the same remote computer.</span></span>

## <a name="review"></a><span data-ttu-id="ad81b-158">Просмотр</span><span class="sxs-lookup"><span data-stu-id="ad81b-158">Review</span></span>

1. <span data-ttu-id="ad81b-159">Как включить удаленное взаимодействие PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ad81b-159">How do you enable PowerShell remoting?</span></span>
1. <span data-ttu-id="ad81b-160">Какая команда PowerShell используется для запуска интерактивного сеанса с удаленным компьютером?</span><span class="sxs-lookup"><span data-stu-id="ad81b-160">What is the PowerShell command for starting an interactive session with a remote computer?</span></span>
1. <span data-ttu-id="ad81b-161">В чем преимущество использования сеанса удаленного взаимодействия PowerShell по сравнению с простым указанием имени компьютера с помощью каждой команды?</span><span class="sxs-lookup"><span data-stu-id="ad81b-161">What is a benefit of using a PowerShell remoting session versus just specifying the computer name with each command?</span></span>
1. <span data-ttu-id="ad81b-162">Можно ли использовать сеанс удаленного взаимодействия PowerShell с сеансом удаленного взаимодействия "один к одному"?</span><span class="sxs-lookup"><span data-stu-id="ad81b-162">Can a PowerShell remoting session be used with a one-to-one remoting session?</span></span>
1. <span data-ttu-id="ad81b-163">Чем отличается тип объектов, возвращаемых командлетами, от типа объектов, которые возвращаются при выполнении этих же командлетов на удаленных компьютерах с `Invoke-Command`?</span><span class="sxs-lookup"><span data-stu-id="ad81b-163">What is the difference in the type of objects that are returned by cmdlets versus those returned when running those same cmdlets against remote computers with `Invoke-Command`?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="ad81b-164">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="ad81b-164">Recommended Reading</span></span>

- <span data-ttu-id="ad81b-165">[about_Remote][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-165">[about_Remote][]</span></span>
- <span data-ttu-id="ad81b-166">[about_Remote_FAQ][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-166">[about_Remote_FAQ][]</span></span>
- <span data-ttu-id="ad81b-167">[about_Remote_Output][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-167">[about_Remote_Output][]</span></span>
- <span data-ttu-id="ad81b-168">[about_Remote_Requirements][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-168">[about_Remote_Requirements][]</span></span>
- <span data-ttu-id="ad81b-169">[about_Remote_Troubleshooting][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-169">[about_Remote_Troubleshooting][]</span></span>
- <span data-ttu-id="ad81b-170">[about_Remote_Variables][]</span><span class="sxs-lookup"><span data-stu-id="ad81b-170">[about_Remote_Variables][]</span></span>

<!-- link references -->
[about_Remote]: /powershell/module/microsoft.powershell.core/about/about_remote
[about_Remote_FAQ]: /powershell/module/microsoft.powershell.core/about/about_remote_faq
[about_Remote_Output]: /powershell/module/microsoft.powershell.core/about/about_remote_output
[about_Remote_Requirements]: /powershell/module/microsoft.powershell.core/about/about_remote_requirements
[about_Remote_Troubleshooting]: /powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting
[about_Remote_Variables]: /powershell/module/microsoft.powershell.core/about/about_remote_variables
[Breaking changes in PowerShell 6.0]: /powershell/scripting/whats-new/breaking-changes-ps6#remove--protocol-from--computer-cmdlets-5277
