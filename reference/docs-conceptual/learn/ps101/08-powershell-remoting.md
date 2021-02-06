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
# <a name="chapter-8---powershell-remoting"></a>Глава 8. Удаленное взаимодействие PowerShell

В PowerShell доступно множество различных способов выполнения команд на удаленных компьютерах. В последней главе вы узнали, как удаленно запрашивать WMI с помощью командлетов CIM. PowerShell также содержит несколько командлетов со встроенным параметром **ComputerName**.

Как показано в следующем примере, `Get-Command` можно использовать с параметром **ParameterName**, чтобы определить, какие команды имеют параметр **ComputerName**.

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

Параметр **ComputerName** есть у команд `Get-Process` и `Get-Hotfix`. Следует отметить, что для корпорации Майкрософт это не то долгосрочное направление, которого следует придерживаться для выполнения команд на удаленных компьютерах. Даже если вы нашли команду с параметром **ComputerName**, скорее всего, вам потребуется указать альтернативные учетные данные и у команды не будет параметра **Credential**. Если вы решили запустить PowerShell из учетной записи с повышенными привилегиями, брандмауэр между вами и удаленным компьютером может заблокировать запрос.

Чтобы использовать команды удаленного взаимодействия PowerShell, которые демонстрируются в этой главе, необходимо включить удаленное взаимодействие PowerShell на удаленном компьютере. Это можно сделать с помощью командлета `Enable-PSRemoting`.

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

## <a name="one-to-one-remoting"></a>Удаленное взаимодействие "один к одному"

Если вы хотите, чтобы удаленный сеанс был интерактивным, то в этом случае подойдет удаленное взаимодействие "один к одному".
Этот тип удаленного взаимодействия предоставляется с помощью командлета `Enter-PSSession`.

В последней главе учетные данные администратора домена были сохранены в переменной с именем `$Cred`. Если вы еще не сделали этого, сохраните учетные данные администратора домена в переменной `$Cred`.

После этого вы сможете ввести учетные данные один раз и использовать их для каждой команды в активном текущем сеансе PowerShell.

```powershell
$Cred = Get-Credential
```

Создайте сеанс удаленного взаимодействия PowerShell "один к одному" с контроллером домена DC01.

```powershell
Enter-PSSession -ComputerName dc01 -Credential $Cred
```

```Output
[dc01]: PS C:\Users\Administrator\Documents>
```

Обратите внимание, что в предыдущем примере перед запросом PowerShell стоит `[dc01]`. Это означает, что вы находитесь в интерактивном сеансе PowerShell с удаленным компьютером dc01. Все запускаемые команды выполняются на компьютере dc01, а не на локальном компьютере. Кроме того, помните, что у вас есть доступ только к командам PowerShell, которые существуют на удаленном, а не на локальном компьютере. Иными словами, если на компьютере установлены дополнительные модули, они недоступны на удаленном компьютере.

При подключении к удаленному компьютеру в рамках интерактивного сеанса удаленного взаимодействия PowerShell "один к одному" вы фактически находитесь на удаленном компьютере. Все объекты являются обычными объектами, аналогичными тем, с которыми вы уже работали.

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

Завершив работу на удаленном компьютере, выйдите из сеанса удаленного взаимодействия "один к одному" с помощью командлета `Exit-PSSession`.

```powershell
[dc01]:  Exit-PSSession
```

## <a name="one-to-many-remoting"></a>Удаленное взаимодействие "один ко многим"

Иногда может потребоваться выполнить задачу в интерактивном режиме на удаленном компьютере. Удаленное взаимодействие гораздо более эффективно при выполнении задачи на нескольких удаленных компьютерах одновременно. С помощью командлета `Invoke-Command` выполните команду на одном удаленном компьютере или нескольких одновременно.

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

В предыдущем примере на три сервера были отправлены запросы состояния службы времени Windows. Командлет `Get-Service` был помещен в блок сценария `Invoke-Command`. На самом деле сценарий `Get-Service` выполняется на удаленном компьютере и результаты возвращаются на локальный компьютер в виде десериализованных объектов.

Передача предыдущей команды в `Get-Member` подтверждает, что результаты действительно десериализованы.

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

Обратите внимание, что в десериализованных объектах отсутствует большинство методов. Это значит, что они не являются активными объектами, они инертны. Нельзя запускать или останавливать службу с помощью десериализованного объекта, так как он является моментальным снимком состояния этого объекта на момент выполнения команды на удаленном компьютере.

Это не значит, что вы не можете запускать или прекращать работу службы с помощью метода `Invoke-Command`. Это просто значит, что метод должен быть вызван в удаленном сеансе.

Чтобы доказать это, далее я остановлю службу времени Windows на всех трех удаленных серверах с помощью метода **Stop()** .

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

Как отмечалось в предыдущей главе, если для выполнения задачи существует командлет, рекомендуется использовать его, а не метод. В предыдущем сценарии вместо метода остановки советую выполнить командлет `Stop-Service`. Чтобы доказать свою точку зрения, я решил использовать метод **Stop()** , так как многие люди ошибочно полагают, что в рамках удаленного взаимодействия PowerShell вызывать методы невозможно. Их нельзя вызывать в возвращаемом объекте, потому что он десериализован, но можно вызывать в самом удаленном сеансе.

## <a name="powershell-sessions"></a>Сеансы PowerShell

В последнем примере в предыдущем разделе выполнялись две команды с помощью командлета `Invoke-Command`.
Это означает, что для их запуска прошлось бы настроить два отдельных сеанса.

Подобно сеансам CIM, обсуждаемым в главе 7, сеанс PowerShell на удаленном компьютере можно использовать для запуска нескольких команд на удаленном компьютере без дополнительных затрат на создание нового сеанса для каждой отдельной команды.

Создайте сеанс PowerShell с каждым из трех компьютеров, с которыми мы работали в этой главе, — DC01, SQL02 и WEB01.

```powershell
$Session = New-PSSession -ComputerName dc01, sql02, web01 -Credential $Cred
```

С помощью переменной `$Session` запустите службу времени Windows с использованием метода и проверьте состояние службы.

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

После создания сеанса с использованием альтернативных учетных данных указывать учетные данные при каждом выполнении команды не требуется.

Завершив работу с сеансами, не забудьте удалить их.

```powershell
Get-PSSession | Remove-PSSession
```

## <a name="summary"></a>Сводка

В этой главе вы узнали об удаленном взаимодействии PowerShell, научились выполнять команды в интерактивном сеансе с одним удаленным компьютером и поняли, как выполнять команды на нескольких компьютерах с помощью удаленного взаимодействия "один ко многим". Вы также узнали о преимуществах использования сеанса PowerShell при выполнении нескольких команд на одном удаленном компьютере.

## <a name="review"></a>Просмотр

1. Как включить удаленное взаимодействие PowerShell?
1. Какая команда PowerShell используется для запуска интерактивного сеанса с удаленным компьютером?
1. В чем преимущество использования сеанса удаленного взаимодействия PowerShell по сравнению с простым указанием имени компьютера с помощью каждой команды?
1. Можно ли использовать сеанс удаленного взаимодействия PowerShell с сеансом удаленного взаимодействия "один к одному"?
1. Чем отличается тип объектов, возвращаемых командлетами, от типа объектов, которые возвращаются при выполнении этих же командлетов на удаленных компьютерах с `Invoke-Command`?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [about_Remote][]
- [about_Remote_FAQ][]
- [about_Remote_Output][]
- [about_Remote_Requirements][]
- [about_Remote_Troubleshooting][]
- [about_Remote_Variables][]

<!-- link references -->
[about_Remote]: /powershell/module/microsoft.powershell.core/about/about_remote
[about_Remote_FAQ]: /powershell/module/microsoft.powershell.core/about/about_remote_faq
[about_Remote_Output]: /powershell/module/microsoft.powershell.core/about/about_remote_output
[about_Remote_Requirements]: /powershell/module/microsoft.powershell.core/about/about_remote_requirements
[about_Remote_Troubleshooting]: /powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting
[about_Remote_Variables]: /powershell/module/microsoft.powershell.core/about/about_remote_variables
[Breaking changes in PowerShell 6.0]: /powershell/scripting/whats-new/breaking-changes-ps6#remove--protocol-from--computer-cmdlets-5277
