---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Получение объектов WMI (Get-WmiObject)
ms.openlocfilehash: 23fd8cf596a8be7e36651ac3f9c79ca97240e647
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737225"
---
# <a name="getting-wmi-objects-get-wmiobject"></a><span data-ttu-id="0443c-103">Получение объектов WMI (Get-WmiObject)</span><span class="sxs-lookup"><span data-stu-id="0443c-103">Getting WMI Objects (Get-WmiObject)</span></span>

## <a name="getting-wmi-objects-get-wmiobject"></a><span data-ttu-id="0443c-104">Получение объектов WMI (Get-WmiObject)</span><span class="sxs-lookup"><span data-stu-id="0443c-104">Getting WMI Objects (Get-WmiObject)</span></span>

<span data-ttu-id="0443c-105">Инструментарий управления Windows (WMI) является ключевой технологией системного администрирования Windows, поскольку предоставляет широкий спектр сведений в унифицированном виде.</span><span class="sxs-lookup"><span data-stu-id="0443c-105">Windows Management Instrumentation (WMI) is a core technology for Windows system administration because it exposes a wide range of information in a uniform manner.</span></span> <span data-ttu-id="0443c-106">Так как спектр возможностей инструментария WMI достаточно широк, командлет `Get-CimInstance` PowerShell для доступа к объектам WMI наиболее полезный.</span><span class="sxs-lookup"><span data-stu-id="0443c-106">Because of how much WMI makes possible, the PowerShell cmdlet for accessing WMI objects, `Get-CimInstance`, is one of the most useful for doing real work.</span></span> <span data-ttu-id="0443c-107">Мы рассмотрим, как командлет CimCmdletst обращается к объектам WMI и как использовать объекты WMI для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="0443c-107">We are going to discuss how to use the CimCmdlets to access WMI objects and then how to use WMI objects to do specific things.</span></span>

### <a name="listing-wmi-classes"></a><span data-ttu-id="0443c-108">Вывод списка классов WMI</span><span class="sxs-lookup"><span data-stu-id="0443c-108">Listing WMI Classes</span></span>

<span data-ttu-id="0443c-109">Первая проблема, с которой сталкивается большинство пользователей WMI, — это выяснение того, что можно сделать с помощью инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="0443c-109">The first problem most WMI users encounter is trying to find out what can be done with WMI.</span></span> <span data-ttu-id="0443c-110">Классы WMI описывают ресурсы, которыми можно управлять.</span><span class="sxs-lookup"><span data-stu-id="0443c-110">WMI classes describe the resources that can be managed.</span></span> <span data-ttu-id="0443c-111">Имеются сотни классов WMI, некоторые из которых содержат множество свойств.</span><span class="sxs-lookup"><span data-stu-id="0443c-111">There are hundreds of WMI classes, some of which contain dozens of properties.</span></span>

<span data-ttu-id="0443c-112">Командлет `Get-CimClass` решает эту проблему, предоставляя сведения об инструментарии WMI.</span><span class="sxs-lookup"><span data-stu-id="0443c-112">`Get-CimClass` addresses this problem by making WMI discoverable.</span></span> <span data-ttu-id="0443c-113">Список классов WMI, доступных на локальном компьютере, можно получить, введя команду:</span><span class="sxs-lookup"><span data-stu-id="0443c-113">You can get a list of the WMI classes available on the local computer by typing:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 |
  Where-Object CimClassName -like Win32* |
    Select-Object CimClassName
```

```Output
CimClassName
------------
Win32_DeviceChangeEvent
Win32_SystemConfigurationChangeEvent
Win32_VolumeChangeEvent
Win32_SystemTrace
Win32_ProcessTrace
Win32_ProcessStartTrace
Win32_ProcessStopTrace
Win32_ThreadTrace
Win32_ThreadStartTrace
Win32_ThreadStopTrace
...
```

<span data-ttu-id="0443c-114">Те же сведения можно извлечь на удаленном компьютере, указав в параметре **ComputerName** имя или IP-адрес компьютера.</span><span class="sxs-lookup"><span data-stu-id="0443c-114">You can retrieve the same information from a remote computer by using the **ComputerName** parameter, specifying a computer name or IP address:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

<span data-ttu-id="0443c-115">Список классов, возвращаемый удаленным компьютером, может различаться в зависимости от операционной системы компьютера и определенных расширений WMI, добавленных установленными приложениями.</span><span class="sxs-lookup"><span data-stu-id="0443c-115">The class listing returned by remote computers may vary due to the specific operating system the computer is running and the particular WMI extensions added by installed applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0443c-116">При использовании командлетов CIM для подключения к удаленному компьютеру на последнем должен быть запущен инструментарий WMI, а используемая учетная запись должна входить в группу локальных администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0443c-116">When using CIM cmdlets to connect to a remote computer, the remote computer must be running WMI and the account you are using must be in the local administrators group on the remote computer.</span></span>
> <span data-ttu-id="0443c-117">В удаленной системе можно не устанавливать оболочку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0443c-117">The remote system does not need to have PowerShell installed.</span></span> <span data-ttu-id="0443c-118">Это позволяет администрировать операционные системы, на которых не запущена оболочка PowerShell, но есть инструментарий WMI.</span><span class="sxs-lookup"><span data-stu-id="0443c-118">This allows you to administer operating systems that are not running PowerShell, but do have WMI available.</span></span>

### <a name="displaying-wmi-class-details"></a><span data-ttu-id="0443c-119">Вывод сведений о классе WMI</span><span class="sxs-lookup"><span data-stu-id="0443c-119">Displaying WMI Class Details</span></span>

<span data-ttu-id="0443c-120">Если имя класса WMI уже известно, можно немедленно получить сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="0443c-120">If you already know the name of a WMI class, you can use it to get information immediately.</span></span> <span data-ttu-id="0443c-121">Например, одним из классов WMI, используемых для получения сведений о компьютере, является **Win32_OperatingSystem**.</span><span class="sxs-lookup"><span data-stu-id="0443c-121">For example, one of the WMI classes commonly used for retrieving information about a computer is **Win32_OperatingSystem**.</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

<span data-ttu-id="0443c-122">Хотя показаны все параметры, команда может быть представлена в более короткой форме.</span><span class="sxs-lookup"><span data-stu-id="0443c-122">Although we are showing all of the parameters, the command can be expressed in a more succinct way.</span></span>
<span data-ttu-id="0443c-123">Параметр **ComputerName** не является обязательным при подключении к локальной системе.</span><span class="sxs-lookup"><span data-stu-id="0443c-123">The **ComputerName** parameter is not necessary when connecting to the local system.</span></span> <span data-ttu-id="0443c-124">Мы покажем это, чтобы продемонстрировать наиболее общий случай и напомнить об этом параметре.</span><span class="sxs-lookup"><span data-stu-id="0443c-124">We show it to demonstrate the most general case and remind you about the parameter.</span></span> <span data-ttu-id="0443c-125">По умолчанию параметр **Namespace** имеет значение `root/CIMV2` и может быть опущен.</span><span class="sxs-lookup"><span data-stu-id="0443c-125">The **Namespace** defaults to `root/CIMV2`, and can be omitted as well.</span></span> <span data-ttu-id="0443c-126">В конце концов, большинство командлетов позволяет опускать имя типовых параметров.</span><span class="sxs-lookup"><span data-stu-id="0443c-126">Finally, most cmdlets allow you to omit the name of common parameters.</span></span> <span data-ttu-id="0443c-127">Если в командлете `Get-CimInstance` не указано имя для первого параметра, PowerShell считает его параметром **Class**.</span><span class="sxs-lookup"><span data-stu-id="0443c-127">With `Get-CimInstance`, if no name is specified for the first parameter, PowerShell treats it as the **Class** parameter.</span></span> <span data-ttu-id="0443c-128">Это значит, что последнюю команду можно было ввести в таком виде:</span><span class="sxs-lookup"><span data-stu-id="0443c-128">This means the last command could have been issued by typing:</span></span>

```powershell
Get-WmiObject Win32_OperatingSystem
```

<span data-ttu-id="0443c-129">Класс **Win32_OperatingSystem** имеет больше свойств, чем показано здесь.</span><span class="sxs-lookup"><span data-stu-id="0443c-129">The **Win32_OperatingSystem** class has many more properties than those displayed here.</span></span> <span data-ttu-id="0443c-130">Можно воспользоваться командлетом Get-Member, чтобы показать все свойства.</span><span class="sxs-lookup"><span data-stu-id="0443c-130">You can use Get-Member to see all the properties.</span></span> <span data-ttu-id="0443c-131">Свойства класса WMI автоматически доступны, как и другие свойства объекта:</span><span class="sxs-lookup"><span data-stu-id="0443c-131">The properties of a WMI class are automatically available like other object properties:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Get-Member -MemberType Property
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_OperatingSystem
Name                                      MemberType Definition
----                                      ---------- ----------
BootDevice                                Property   string BootDevice {get;}
BuildNumber                               Property   string BuildNumber {get;}
BuildType                                 Property   string BuildType {get;}
Caption                                   Property   string Caption {get;}
CodeSet                                   Property   string CodeSet {get;}
CountryCode                               Property   string CountryCode {get;}
CreationClassName                         Property   string CreationClassName {get;}
CSCreationClassName                       Property   string CSCreationClassName {get;}
CSDVersion                                Property   string CSDVersion {get;}
CSName                                    Property   string CSName {get;}
CurrentTimeZone                           Property   short CurrentTimeZone {get;}
DataExecutionPrevention_32BitApplications Property   bool DataExecutionPrevention_32BitApplications {get;}
DataExecutionPrevention_Available         Property   bool DataExecutionPrevention_Available {get;}
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a><span data-ttu-id="0443c-132">Вывод свойств, отличных от используемых по умолчанию, с помощью командлетов Format</span><span class="sxs-lookup"><span data-stu-id="0443c-132">Displaying Non-Default Properties with Format Cmdlets</span></span>

<span data-ttu-id="0443c-133">Если необходимо показать сведения, содержащиеся в классе **Win32_OperatingSystem**, которые не выводятся по умолчанию, можно воспользоваться командлетом **Format**.</span><span class="sxs-lookup"><span data-stu-id="0443c-133">If you want information contained in the **Win32_OperatingSystem** class that is not displayed by default, you can display it by using the **Format** cmdlets.</span></span> <span data-ttu-id="0443c-134">Например, если нужно показать сведения о количестве доступной памяти, введите:</span><span class="sxs-lookup"><span data-stu-id="0443c-134">For example, if you want to display available memory data, type:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem |
  Format-Table -Property TotalVirtualMemorySize, TotalVisibleMemorySize,
    FreePhysicalMemory, FreeVirtualMemory, FreeSpaceInPagingFiles
```

```Output
TotalVirtualMemorySize TotalVisibleMemorySize FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------------- ------------------ ----------------- ----------------------
              33449088               16671872            6451868          18424496               16285032
```

> [!NOTE]
> <span data-ttu-id="0443c-135">В именах свойств в командлете `Format-Table` допускаются подстановочные знаки, поэтому последний элемент конвейера может быть сокращен до `Format-Table -Property Total*Memory*, Free*`.</span><span class="sxs-lookup"><span data-stu-id="0443c-135">Wildcards work with property names in `Format-Table`, so the final pipeline element can be reduced to `Format-Table -Property Total*Memory*, Free*`</span></span>

<span data-ttu-id="0443c-136">Сведения о памяти можно представить в более понятном виде, отформатировав список с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="0443c-136">The memory data might be more readable if you format it as a list by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Format-List Total*Memory*, Free*
```

```Output
TotalVirtualMemorySize : 33449088
TotalVisibleMemorySize : 16671872
FreePhysicalMemory     : 6524456
FreeSpaceInPagingFiles : 16285808
FreeVirtualMemory      : 18393668
Name                   : Microsoft Windows 10 Pro|C:\WINDOWS|\Device\Harddisk0\Partition2
```
