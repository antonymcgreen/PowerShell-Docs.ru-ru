---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmaninstance?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManInstance
ms.openlocfilehash: 1fd516f248e3f361d16e3643271b240f671d9009
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229854"
---
# <span data-ttu-id="6ab39-103">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="6ab39-103">Get-WSManInstance</span></span>

## <span data-ttu-id="6ab39-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6ab39-104">SYNOPSIS</span></span>
<span data-ttu-id="6ab39-105">Выводит сведения управления для экземпляра ресурса, указанного URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-105">Displays management information for a resource instance specified by a Resource URI.</span></span>

## <span data-ttu-id="6ab39-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ab39-106">SYNTAX</span></span>

### <span data-ttu-id="6ab39-107">GetInstance (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6ab39-107">GetInstance (Default)</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-ConnectionURI <Uri>] [-Dialect <Uri>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet <Hashtable>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="6ab39-108">Перечисление</span><span class="sxs-lookup"><span data-stu-id="6ab39-108">Enumerate</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-BasePropertiesOnly] [-ComputerName <String>]
 [-ConnectionURI <Uri>] [-Dialect <Uri>] [-Enumerate] [-Filter <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-Associations] [-ResourceURI] <Uri> [-ReturnType <String>] [-SessionOption <SessionOption>]
 [-Shallow] [-UseSSL] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="6ab39-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ab39-109">DESCRIPTION</span></span>
<span data-ttu-id="6ab39-110">Командлет **Get-WSManInstance** извлекает экземпляр ресурса управления, указанный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="6ab39-110">The **Get-WSManInstance** cmdlet retrieves an instance of a management resource that is specified by a resource Uniform Resource Identifier (URI).</span></span>
<span data-ttu-id="6ab39-111">Извлекаемые сведения могут быть сложным набором сведений XML (объектом) или простым значением.</span><span class="sxs-lookup"><span data-stu-id="6ab39-111">The information that is retrieved can be a complex XML information set, which is an object, or a simple value.</span></span>
<span data-ttu-id="6ab39-112">Этот командлет эквивалентен стандартной команде **Get** веб-служб для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="6ab39-112">This cmdlet is the equivalent to the standard Web Services for Management (WS-Management) **Get** command.</span></span>

<span data-ttu-id="6ab39-113">Для извлечения информации он использует соединение/транспортный уровень WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6ab39-113">This cmdlet uses the WS-Management connection/transport layer to retrieve information.</span></span>

## <span data-ttu-id="6ab39-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="6ab39-114">EXAMPLES</span></span>

### <span data-ttu-id="6ab39-115">Пример 1. Получение всех данных из инструментария WMI</span><span class="sxs-lookup"><span data-stu-id="6ab39-115">Example 1: Get all information from WMI</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="winrm"} -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : Windows Remote Management (WS-Management)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Windows Remote Management (WinRM) service implements the WS-Management protocol for remote
management. WS-Management is a standard web services protocol used for remote software and
hardware management. The WinRM service listens on the network for WS-Management requests
and processes them. The WinRM Service needs to be configured with a listener using the
winrm.cmd command line tool or through Group Policy in order for it to listen over the
network. The WinRM service provides access to WMI data and enables event collection. Event
collection and subscription to events require that the service is running. WinRM messages
use HTTP and HTTPS as transports. The WinRM service does not depend on IIS but is
preconfigured to share a port with IIS on the same computer.  The WinRM service reserves the
/wsman URL prefix. To prevent conflicts with IIS, administrators should ensure that any
websites hosted on IIS do not use the /wsman URL prefix.
DesktopInteract         : false
DisplayName             : Windows Remote Management (WS-Management)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : winrm
PathName                : C:\Windows\System32\svchost.exe -k NetworkService
ProcessId               : 948
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0
```

<span data-ttu-id="6ab39-116">Эта команда возвращает все сведения, которые инструментарий управления Windows (WMI) (WMI) предоставляет сведения о службе **WinRM** на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="6ab39-116">This command returns all of the information that Windows Management Instrumentation (WMI) exposes about the **WinRM** service on the remote server01 computer.</span></span>

### <span data-ttu-id="6ab39-117">Пример 2. Получение сведений о состоянии службы очереди печати</span><span class="sxs-lookup"><span data-stu-id="6ab39-117">Example 2: Get the status of the Spooler service</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="spooler"} -Fragment Status -ComputerName "Server01"
XmlFragment=OK
```

<span data-ttu-id="6ab39-118">Эта команда возвращает только состояние службы **диспетчера очереди печати** на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="6ab39-118">This command returns only the status of the **Spooler** service on the remote server01 computer.</span></span>

### <span data-ttu-id="6ab39-119">Пример 3. Получение ссылок на конечные точки для всех служб</span><span class="sxs-lookup"><span data-stu-id="6ab39-119">Example 3: Get endpoint references for all services</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/win32_service -ReturnType EPR
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Visual Studio 2008 Remote Debugger
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Allows members of the Administrators group to remotely debug server applications using Visual
Studio 2008. Use the Visual Studio 2008 Remote Debugging Configuration Wizard to enable this
service.
DesktopInteract         : false
DisplayName             : Visual Studio 2008 Remote Debugger
ErrorControl            : Ignore
ExitCode                : 1077
InstallDate             : InstallDate
Name                    : msvsmon90
PathName                : "C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\Remote Debugger\x86\msvsmon.exe" /service msvsmon90
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Own Process
Started                 : false
StartMode               : Disabled
StartName               : LocalSystem
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : COMPUTER01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="6ab39-120">Эта команда возвращает ссылки на конечные точки, которые соответствуют всем службам на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ab39-120">This command returns endpoint references that correspond to all the services on the local computer.</span></span>

### <span data-ttu-id="6ab39-121">Пример 4. Получение служб, отвечающих указанным критериям</span><span class="sxs-lookup"><span data-stu-id="6ab39-121">Example 4: Get services that meet specified criteria</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/* -Filter "select * from win32_service where StartMode = 'Auto' and State = 'Stopped'" -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Windows Media Center Service Launcher
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Starts Windows Media Center Scheduler and Windows Media Center Receiver services
at startup if TV is enabled within Windows Media Center.
DesktopInteract         : false
DisplayName             : Windows Media Center Service Launcher
ErrorControl            : Ignore
ExitCode                : 0
InstallDate             : InstallDate
Name                    : ehstart
PathName                : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : false
StartMode               : Auto
StartName               : NT AUTHORITY\LocalService
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : Server01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="6ab39-122">Эта команда выводит список всех служб на удаленном компьютере server01, которые отвечают следующим критериям:</span><span class="sxs-lookup"><span data-stu-id="6ab39-122">This command lists all of the services that meet the following criteria on the remote Server01 computer:</span></span>

- <span data-ttu-id="6ab39-123">служба имеет автоматический тип запуска;</span><span class="sxs-lookup"><span data-stu-id="6ab39-123">The startup type of the service is Automatic.</span></span>
- <span data-ttu-id="6ab39-124">служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="6ab39-124">The service is stopped.</span></span>

### <span data-ttu-id="6ab39-125">Пример 5. Получение конфигурации прослушивателя, соответствующего критериям на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="6ab39-125">Example 5: Get listener configuration that matches criteria on the local computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"}
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.123, ::1, 2001:4898:0:fff:0:5efe:123.123.123.123...}
```

<span data-ttu-id="6ab39-126">Эта команда выводит конфигурацию прослушивателя WS-Management на локальном компьютере для прослушивателя, соответствующего критериям в наборе селекторов.</span><span class="sxs-lookup"><span data-stu-id="6ab39-126">This command lists the WS-Management listener configuration on the local computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="6ab39-127">Пример 6. Получение конфигурации прослушивателя, соответствующего критериям на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="6ab39-127">Example 6: Get listener configuration that matches criteria on a remote computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"} -ComputerName "Server01"
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.124, ::1, 2001:4898:0:fff:0:5efe:123.123.123.124...}
```

<span data-ttu-id="6ab39-128">Эта команда выводит конфигурацию прослушивателя WS-Management на удаленном компьютере server01 для прослушивателя, соответствующего критериям в наборе селекторов.</span><span class="sxs-lookup"><span data-stu-id="6ab39-128">This command lists the WS-Management listener configuration on the remote server01 computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="6ab39-129">Пример 7. Получение связанных экземпляров, которые связаны с указанным экземпляром</span><span class="sxs-lookup"><span data-stu-id="6ab39-129">Example 7: Get associated instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
xsi                       : http://www.w3.org/2001/XMLSchema-instance
p                         : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_ComputerSystem
cim                       : http://schemas.dmtf.org/wbem/wscim/1/common
type                      : p:Win32_ComputerSystem_Type
lang                      : en-US
AdminPasswordStatus       : 1
AutomaticManagedPagefile  : true
AutomaticResetBootOption  : true
AutomaticResetCapability  : true
BootOptionOnLimit         : BootOptionOnLimit
BootOptionOnWatchDog      : BootOptionOnWatchDog
BootROMSupported          : true
BootupState               : Normal boot
Caption                   : SERVER01
ChassisBootupState        : 3
CreationClassName         : Win32_ComputerSystem
CurrentTimeZone           : -480
DaylightInEffect          : false
Description               : AT/AT COMPATIBLE
DNSHostName               : server01
Domain                    : site01.corp.fabrikam.com
DomainRole                : 1
EnableDaylightSavingsTime : true
FrontPanelResetStatus     : 2
InfraredSupported         : false
InstallDate               : InstallDate
KeyboardPasswordStatus    : 2
LastLoadInfo              : LastLoadInfo
Manufacturer              : Dell Inc.
Model                     : OptiPlex 745
Name                      : SERVER01
NameFormat                : NameFormat
NetworkServerModeEnabled  : true
NumberOfLogicalProcessors : 2
NumberOfProcessors        : 1
OEMStringArray            : www.dell.com
PartOfDomain              : true
PauseAfterReset           : -1
PCSystemType              : 5
PowerManagementSupported  : PowerManagementSupported
PowerOnPasswordStatus     : 1
PowerState                : 0
PowerSupplyState          : 3
PrimaryOwnerContact       : PrimaryOwnerContact
PrimaryOwnerName          : testuser01
ResetCapability           : 1
ResetCount                : -1
ResetLimit                : -1
Roles                     : {LM_Workstation, LM_Server, SQLServer, NT}
Status                    : OK
SystemStartupDelay        : SystemStartupDelay
SystemStartupSetting      : SystemStartupSetting
SystemType                : X86-based PC
ThermalState              : 3
TotalPhysicalMemory       : 3217760256
UserName                  : FABRIKAM\testuser01
WakeUpType                : 6
Workgroup                 : Workgroup
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Remote Procedure Call (RPC)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Serves as the endpoint mapper and COM Service Control Manager. If this service is stopped
or disabled, programs using COM or Remote Procedure Call (RPC) services will not function
properly.
DesktopInteract         : false
DisplayName             : Remote Procedure Call (RPC)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : RpcSs
PathName                : C:\Windows\system32\svchost.exe -k rpcss
ProcessId               : 1100
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0

xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_SystemDriver
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_SystemDriver_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : HTTP
CreationClassName       : Win32_SystemDriver
Description             : HTTP
DesktopInteract         : false
DisplayName             : HTTP
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : HTTP
PathName                : C:\Windows\system32\drivers\HTTP.sys
ServiceSpecificExitCode : 0
ServiceType             : Kernel Driver
Started                 : true
StartMode               : Manual
StartName               :
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
```

<span data-ttu-id="6ab39-130">Эта команда возвращает связанные экземпляры, которые связаны с указанным экземпляром (winrm).</span><span class="sxs-lookup"><span data-stu-id="6ab39-130">This command gets the associated instances that are related to the specified instance (winrm).</span></span>

<span data-ttu-id="6ab39-131">Фильтр необходимо заключить в кавычки, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="6ab39-131">You must enclose the filter in quotation marks, as shown in the example.</span></span>

### <span data-ttu-id="6ab39-132">Пример 8. Получение экземпляров ассоциаций, которые связаны с указанным экземпляром</span><span class="sxs-lookup"><span data-stu-id="6ab39-132">Example 8: Get association instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Associations -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
```

<span data-ttu-id="6ab39-133">Эта команда возвращает экземпляры ассоциаций, которые связаны с указанным экземпляром (winrm).</span><span class="sxs-lookup"><span data-stu-id="6ab39-133">This command gets association instances that are related to the specified instance (winrm).</span></span>
<span data-ttu-id="6ab39-134">Так как для параметра *Dialect* задано значение association и используется параметр *Associations* , эта команда возвращает экземпляры ассоциаций, а не связанные экземпляры.</span><span class="sxs-lookup"><span data-stu-id="6ab39-134">Because the *Dialect* value is association and the *Associations* parameter is used, this command returns association instances, not associated instances.</span></span>

<span data-ttu-id="6ab39-135">Фильтр необходимо заключить в кавычки, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="6ab39-135">You must enclose the filter in quotation marks, as shown in the example.</span></span>

## <span data-ttu-id="6ab39-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ab39-136">PARAMETERS</span></span>

### <span data-ttu-id="6ab39-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="6ab39-137">-ApplicationName</span></span>
<span data-ttu-id="6ab39-138">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="6ab39-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="6ab39-139">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="6ab39-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="6ab39-140">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="6ab39-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="6ab39-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="6ab39-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="6ab39-142">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="6ab39-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="6ab39-143">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="6ab39-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="6ab39-144">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="6ab39-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="6ab39-145">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ab39-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="6ab39-146">В этом случае для повышения эффективности в службах IIS размещены службы WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6ab39-146">In this case, IIS hosts WS-Management for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-147">-Associations</span><span class="sxs-lookup"><span data-stu-id="6ab39-147">-Associations</span></span>
<span data-ttu-id="6ab39-148">Указывает, что этот командлет получает экземпляры ассоциаций, а не связанные экземпляры.</span><span class="sxs-lookup"><span data-stu-id="6ab39-148">Indicates that this cmdlet gets association instances, not associated instances.</span></span>
<span data-ttu-id="6ab39-149">Вы можете использовать этот параметр только в том случае, когда для параметра *Dialect* задано значение Association.</span><span class="sxs-lookup"><span data-stu-id="6ab39-149">You can use this parameter only when the *Dialect* parameter has a value of Association.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-150">-Authentication</span><span class="sxs-lookup"><span data-stu-id="6ab39-150">-Authentication</span></span>
<span data-ttu-id="6ab39-151">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="6ab39-151">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="6ab39-152">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6ab39-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6ab39-153">Обычные.</span><span class="sxs-lookup"><span data-stu-id="6ab39-153">Basic.</span></span>
<span data-ttu-id="6ab39-154">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="6ab39-154">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="6ab39-155">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ab39-155">Default.</span></span>
<span data-ttu-id="6ab39-156">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6ab39-156">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="6ab39-157">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ab39-157">This is the default.</span></span>
- <span data-ttu-id="6ab39-158">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="6ab39-158">Digest.</span></span>
<span data-ttu-id="6ab39-159">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-159">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="6ab39-160">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="6ab39-160">Kerberos.</span></span>
<span data-ttu-id="6ab39-161">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6ab39-161">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="6ab39-162">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="6ab39-162">Negotiate.</span></span>
<span data-ttu-id="6ab39-163">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="6ab39-163">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="6ab39-164">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="6ab39-164">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="6ab39-165">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="6ab39-165">CredSSP.</span></span>
<span data-ttu-id="6ab39-166">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6ab39-166">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="6ab39-167">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="6ab39-167">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="6ab39-168">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6ab39-168">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="6ab39-169">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="6ab39-169">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="6ab39-170">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="6ab39-170">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-171">-BasePropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="6ab39-171">-BasePropertiesOnly</span></span>
<span data-ttu-id="6ab39-172">Указывает, что этот командлет перечисляет только свойства, которые являются частью базового класса, заданного параметром *ResourceURI*.</span><span class="sxs-lookup"><span data-stu-id="6ab39-172">Indicates that this cmdlet enumerates only the properties that are part of the base class that is specified by the *ResourceURI* parameter.</span></span>
<span data-ttu-id="6ab39-173">Этот параметр не действует, если указан *неполный параметр.*</span><span class="sxs-lookup"><span data-stu-id="6ab39-173">This parameter has no effect if the *Shallow* parameter is specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases: UBPO, Base

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-174">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="6ab39-174">-CertificateThumbprint</span></span>
<span data-ttu-id="6ab39-175">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="6ab39-175">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="6ab39-176">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="6ab39-176">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="6ab39-177">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="6ab39-177">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="6ab39-178">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="6ab39-178">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="6ab39-179">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="6ab39-179">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-180">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6ab39-180">-ComputerName</span></span>
<span data-ttu-id="6ab39-181">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="6ab39-181">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="6ab39-182">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="6ab39-182">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="6ab39-183">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="6ab39-183">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="6ab39-184">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ab39-184">The local computer is the default.</span></span>
<span data-ttu-id="6ab39-185">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="6ab39-185">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="6ab39-186">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="6ab39-186">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-187">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="6ab39-187">-ConnectionURI</span></span>
<span data-ttu-id="6ab39-188">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="6ab39-188">Specifies the connection endpoint.</span></span>
<span data-ttu-id="6ab39-189">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="6ab39-189">The format of this string is as follows:</span></span>

<span data-ttu-id="6ab39-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="6ab39-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="6ab39-191">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6ab39-191">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="6ab39-192">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="6ab39-192">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-193">-Credential</span><span class="sxs-lookup"><span data-stu-id="6ab39-193">-Credential</span></span>
<span data-ttu-id="6ab39-194">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="6ab39-194">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="6ab39-195">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="6ab39-195">The default is the current user.</span></span>
<span data-ttu-id="6ab39-196">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="6ab39-196">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="6ab39-197">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="6ab39-197">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="6ab39-198">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="6ab39-198">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-199">-Dialect</span><span class="sxs-lookup"><span data-stu-id="6ab39-199">-Dialect</span></span>
<span data-ttu-id="6ab39-200">Определяет диалект, используемый в предикате фильтра.</span><span class="sxs-lookup"><span data-stu-id="6ab39-200">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="6ab39-201">Это может быть любой диалект, поддерживаемый удаленной службой.</span><span class="sxs-lookup"><span data-stu-id="6ab39-201">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="6ab39-202">Для URI диалекта можно использовать следующие псевдонимы:</span><span class="sxs-lookup"><span data-stu-id="6ab39-202">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="6ab39-203">ВОДИТ `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="6ab39-203">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="6ab39-204">Выбора `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="6ab39-204">Selector `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="6ab39-205">Связке `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="6ab39-205">Association `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-206">-Enumerate</span><span class="sxs-lookup"><span data-stu-id="6ab39-206">-Enumerate</span></span>
<span data-ttu-id="6ab39-207">Указывает, что этот командлет возвращает все экземпляры ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="6ab39-207">Indicates that this cmdlet returns all of the instances of a management resource.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-208">-Filter</span><span class="sxs-lookup"><span data-stu-id="6ab39-208">-Filter</span></span>
<span data-ttu-id="6ab39-209">Задает выражение фильтра для перечисления.</span><span class="sxs-lookup"><span data-stu-id="6ab39-209">Specifies the filter expression for the enumeration.</span></span>
<span data-ttu-id="6ab39-210">При указании этого параметра необходимо также указать параметр *Dialect*.</span><span class="sxs-lookup"><span data-stu-id="6ab39-210">If you specify this parameter, you must also specify *Dialect*.</span></span>

<span data-ttu-id="6ab39-211">Допустимые значения этого параметра зависят от диалекта, указанного в параметре *Dialect*.</span><span class="sxs-lookup"><span data-stu-id="6ab39-211">The valid values of this parameter depend on the dialect that is specified in *Dialect*.</span></span>
<span data-ttu-id="6ab39-212">Например, если параметр *Dialect* имеет значение WQL, параметр *Filter* должен содержать строку с допустимым запросом WQL, например следующего вида:</span><span class="sxs-lookup"><span data-stu-id="6ab39-212">For example, if *Dialect* is WQL, the *Filter* parameter must contain a string, and the string must contain a valid WQL query such as the following query:</span></span>

`"Select * from Win32_Service where State != Running"`

<span data-ttu-id="6ab39-213">Если параметр *Dialect* имеет значение Association, параметр *Filter* должен содержать строку с допустимым запросом WQL, например следующего вида:</span><span class="sxs-lookup"><span data-stu-id="6ab39-213">If *Dialect* is Association, *Filter* must contain a string, and the string must contain a valid filter, such as the following filter:</span></span>

`-filter:Object=EPR\[;AssociationClassName=AssocClassName\]\[;ResultClassName=ClassName\]\[;Role=RefPropertyName\]\[;ResultRole=RefPropertyName\]}`

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-214">-Fragment</span><span class="sxs-lookup"><span data-stu-id="6ab39-214">-Fragment</span></span>
<span data-ttu-id="6ab39-215">Задает раздел внутри экземпляра, который должен быть обновлен или возвращен для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="6ab39-215">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="6ab39-216">Например, чтобы получить состояние службы очереди печати, укажите следующий код:</span><span class="sxs-lookup"><span data-stu-id="6ab39-216">For example, to get the status of a spooler service, specify the following:</span></span>

`-Fragment Status`

```yaml
Type: System.String
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-217">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="6ab39-217">-OptionSet</span></span>
<span data-ttu-id="6ab39-218">Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-218">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="6ab39-219">Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="6ab39-219">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="6ab39-220">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="6ab39-220">Any number of options can be specified.</span></span>

<span data-ttu-id="6ab39-221">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="6ab39-221">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: OS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-222">-Port</span><span class="sxs-lookup"><span data-stu-id="6ab39-222">-Port</span></span>
<span data-ttu-id="6ab39-223">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="6ab39-223">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="6ab39-224">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="6ab39-224">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="6ab39-225">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="6ab39-225">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="6ab39-226">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="6ab39-226">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="6ab39-227">Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption* , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="6ab39-227">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="6ab39-228">Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6ab39-228">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-229">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="6ab39-229">-ResourceURI</span></span>
<span data-ttu-id="6ab39-230">Указывает URI класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-230">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="6ab39-231">URI идентифицирует определенный тип ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ab39-231">The URI identifies a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="6ab39-232">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6ab39-232">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="6ab39-233">Пример:</span><span class="sxs-lookup"><span data-stu-id="6ab39-233">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: RURI

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-234">-ReturnType</span><span class="sxs-lookup"><span data-stu-id="6ab39-234">-ReturnType</span></span>
<span data-ttu-id="6ab39-235">Указывает тип возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="6ab39-235">Specifies the type of data to be returned.</span></span>
<span data-ttu-id="6ab39-236">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6ab39-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6ab39-237">Объект</span><span class="sxs-lookup"><span data-stu-id="6ab39-237">Object</span></span>
- <span data-ttu-id="6ab39-238">EPR</span><span class="sxs-lookup"><span data-stu-id="6ab39-238">EPR</span></span>
- <span data-ttu-id="6ab39-239">ObjectAndEPR</span><span class="sxs-lookup"><span data-stu-id="6ab39-239">ObjectAndEPR</span></span>

<span data-ttu-id="6ab39-240">По умолчанию используется значение Object.</span><span class="sxs-lookup"><span data-stu-id="6ab39-240">The default value is Object.</span></span>

<span data-ttu-id="6ab39-241">Если указано значение Object или этот параметр не задан, этот командлет возвращает только объекты.</span><span class="sxs-lookup"><span data-stu-id="6ab39-241">If you specify Object or do not specify this parameter, this cmdlet returns only objects.</span></span>
<span data-ttu-id="6ab39-242">Если указана ссылка на конечную точку (EPR), этот командлет возвращает только ссылки на конечные точки объектов.</span><span class="sxs-lookup"><span data-stu-id="6ab39-242">If you specify endpoint reference (EPR) this cmdlet returns only the endpoint references of the objects.</span></span>
<span data-ttu-id="6ab39-243">Ссылки на конечную точку содержат сведения о URI ресурса и селекторы для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6ab39-243">Endpoint references contain information about the resource URI and the selectors for the instance.</span></span>
<span data-ttu-id="6ab39-244">Если указано значение ObjectAndEPR, этот командлет возвращает как объект, так и связанные с ним ссылки на конечные точки.</span><span class="sxs-lookup"><span data-stu-id="6ab39-244">If you specify ObjectAndEPR, this cmdlet returns both the object and its associated endpoint references.</span></span>

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases: RT
Accepted values: object, epr, objectandepr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-245">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="6ab39-245">-SelectorSet</span></span>
<span data-ttu-id="6ab39-246">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="6ab39-246">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="6ab39-247">Параметр *selector* используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-247">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="6ab39-248">Значение параметра набора *selector* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="6ab39-248">The value of the *SelectorSet* parameter must be a hash table.</span></span>

<span data-ttu-id="6ab39-249">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6ab39-249">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-250">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="6ab39-250">-SessionOption</span></span>
<span data-ttu-id="6ab39-251">Определяет расширенные параметры для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="6ab39-251">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="6ab39-252">Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="6ab39-252">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="6ab39-253">Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.</span><span class="sxs-lookup"><span data-stu-id="6ab39-253">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: SO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-254">-Shallow</span><span class="sxs-lookup"><span data-stu-id="6ab39-254">-Shallow</span></span>
<span data-ttu-id="6ab39-255">Указывает, что этот командлет возвращает только экземпляры того базового класса, который указан в URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="6ab39-255">Indicates that this cmdlet returns only instances of the base class that is specified in the resource URI.</span></span>
<span data-ttu-id="6ab39-256">Если этот параметр не указан, командлет возвращает экземпляры базового класса, указанного в URI, и всех производных от него классов.</span><span class="sxs-lookup"><span data-stu-id="6ab39-256">If you do not specify this parameter,, this cmdlet returns instances of the base class that is specified in the URI and in all its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-257">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="6ab39-257">-UseSSL</span></span>
<span data-ttu-id="6ab39-258">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="6ab39-258">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="6ab39-259">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="6ab39-259">By default, SSL is not used.</span></span>

<span data-ttu-id="6ab39-260">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="6ab39-260">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="6ab39-261">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ab39-261">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="6ab39-262">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6ab39-262">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SSL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ab39-263">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6ab39-263">CommonParameters</span></span>
<span data-ttu-id="6ab39-264">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ab39-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ab39-265">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ab39-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ab39-266">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6ab39-266">INPUTS</span></span>

### <span data-ttu-id="6ab39-267">Нет</span><span class="sxs-lookup"><span data-stu-id="6ab39-267">None</span></span>
<span data-ttu-id="6ab39-268">Эта команда не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="6ab39-268">This command does not accept any input.</span></span>

## <span data-ttu-id="6ab39-269">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6ab39-269">OUTPUTS</span></span>

### <span data-ttu-id="6ab39-270">System.Xml.XmlElement</span><span class="sxs-lookup"><span data-stu-id="6ab39-270">System.Xml.XmlElement</span></span>
<span data-ttu-id="6ab39-271">Этот командлет создает объект **XMLElement**.</span><span class="sxs-lookup"><span data-stu-id="6ab39-271">This cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="6ab39-272">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6ab39-272">NOTES</span></span>

## <span data-ttu-id="6ab39-273">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6ab39-273">RELATED LINKS</span></span>

[<span data-ttu-id="6ab39-274">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="6ab39-274">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="6ab39-275">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="6ab39-275">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="6ab39-276">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="6ab39-276">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="6ab39-277">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="6ab39-277">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="6ab39-278">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="6ab39-278">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="6ab39-279">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="6ab39-279">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="6ab39-280">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="6ab39-280">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="6ab39-281">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="6ab39-281">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="6ab39-282">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="6ab39-282">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="6ab39-283">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="6ab39-283">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="6ab39-284">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="6ab39-284">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="6ab39-285">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="6ab39-285">Test-WSMan</span></span>](Test-WSMan.md)