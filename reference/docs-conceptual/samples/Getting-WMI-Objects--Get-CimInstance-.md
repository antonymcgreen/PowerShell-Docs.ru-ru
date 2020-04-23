---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Объекты Getting WMI (Get CimInstance)
ms.openlocfilehash: 4ff47844fd367a49f554c7c05c491bdddf28eabc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "77002654"
---
# <a name="getting-wmi-objects-get-ciminstance"></a>Объекты Getting WMI (Get-CimInstance)

## <a name="getting-wmi-objects-get-ciminstance"></a>Объекты Getting WMI (Get-CimInstance)

Инструментарий управления Windows (WMI) является ключевой технологией системного администрирования Windows, поскольку предоставляет широкий спектр сведений в унифицированном виде. Так как спектр возможностей инструментария WMI достаточно широк, командлет `Get-CimInstance` PowerShell для доступа к объектам WMI наиболее полезный. Мы рассмотрим, как командлет CimCmdletst обращается к объектам WMI и как использовать объекты WMI для выполнения определенных задач.

### <a name="listing-wmi-classes"></a>Вывод списка классов WMI

Первая проблема, с которой сталкивается большинство пользователей WMI, — это выяснение того, что можно сделать с помощью инструментария WMI. Классы WMI описывают ресурсы, которыми можно управлять. Имеются сотни классов WMI, некоторые из которых содержат множество свойств.

Командлет `Get-CimClass` решает эту проблему, предоставляя сведения об инструментарии WMI. Список классов WMI, доступных на локальном компьютере, можно получить, введя команду:

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

Те же сведения можно извлечь на удаленном компьютере, указав в параметре **ComputerName** имя или IP-адрес компьютера.

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

Список классов, возвращаемый удаленным компьютером, может различаться в зависимости от операционной системы компьютера и определенных расширений WMI, добавленных установленными приложениями.

> [!NOTE]
> При использовании командлетов CIM для подключения к удаленному компьютеру на последнем должен быть запущен инструментарий WMI, а используемая учетная запись должна входить в группу локальных администраторов на удаленном компьютере.
> В удаленной системе можно не устанавливать оболочку PowerShell. Это позволяет администрировать операционные системы, на которых не запущена оболочка PowerShell, но есть инструментарий WMI.

### <a name="displaying-wmi-class-details"></a>Вывод сведений о классе WMI

Если имя класса WMI уже известно, можно немедленно получить сведения о нем. Например, одним из классов WMI, используемых для получения сведений о компьютере, является **Win32_OperatingSystem**.

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

Хотя показаны все параметры, команда может быть представлена в более короткой форме.
Параметр **ComputerName** не является обязательным при подключении к локальной системе. Мы покажем это, чтобы продемонстрировать наиболее общий случай и напомнить об этом параметре. По умолчанию параметр **Namespace** имеет значение `root/CIMV2` и может быть опущен. В конце концов, большинство командлетов позволяет опускать имя типовых параметров. Если в командлете `Get-CimInstance` не указано имя для первого параметра, PowerShell считает его параметром **Class**. Это значит, что последнюю команду можно было ввести в таком виде:

```powershell
Get-CimInstance Win32_OperatingSystem
```

Класс **Win32_OperatingSystem** имеет больше свойств, чем показано здесь. Можно воспользоваться командлетом Get-Member, чтобы показать все свойства. Свойства класса WMI автоматически доступны, как и другие свойства объекта:

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

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a>Вывод свойств, отличных от используемых по умолчанию, с помощью командлетов Format

Если необходимо показать сведения, содержащиеся в классе **Win32_OperatingSystem**, которые не выводятся по умолчанию, можно воспользоваться командлетом **Format**. Например, если нужно показать сведения о количестве доступной памяти, введите:

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
> В именах свойств в командлете `Format-Table` допускаются подстановочные знаки, поэтому последний элемент конвейера может быть сокращен до `Format-Table -Property Total*Memory*, Free*`.

Сведения о памяти можно представить в более понятном виде, отформатировав список с помощью следующей команды:

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
