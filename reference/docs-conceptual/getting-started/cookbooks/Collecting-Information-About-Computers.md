---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сбор информации о компьютерах
ms.assetid: 9e7b6a2d-34f7-4731-a92c-8b3382eb51bb
ms.openlocfilehash: ca92474eaf6fa546c3d6450f5a282e45157018a8
ms.sourcegitcommit: 4a841ebda3339ae2477e0f5f5be8c01740221232
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="collecting-information-about-computers"></a><span data-ttu-id="17626-103">Сбор информации о компьютерах</span><span class="sxs-lookup"><span data-stu-id="17626-103">Collecting Information About Computers</span></span>

<span data-ttu-id="17626-104">Командлеты из модуля **CimCmdlets** — самые важные для общих задач управления системой.</span><span class="sxs-lookup"><span data-stu-id="17626-104">Cmdlets from **CimCmdlets** module are the most important cmdlets for general system management tasks.</span></span>
<span data-ttu-id="17626-105">Все ключевые параметры подсистемы доступны через инструментарий WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-105">All critical subsystem settings are exposed through WMI.</span></span>
<span data-ttu-id="17626-106">Более того, инструментарий WMI обрабатывает данные как объекты, сгруппированные в коллекции из одного или нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="17626-106">Furthermore, WMI treats data as objects that are in collections of one or more items.</span></span>
<span data-ttu-id="17626-107">Поскольку Windows PowerShell также работает с объектами и имеет конвейер, позволяющий одинаково обрабатывать отдельный объект или несколько объектов, общий доступ к инструментарию WMI предоставляет возможность выполнять некоторые сложные задачи с небольшими затратами усилий.</span><span class="sxs-lookup"><span data-stu-id="17626-107">Because Windows PowerShell also works with objects and has a pipeline that allows you to treat single or multiple objects in the same way, generic WMI access allows you to perform some advanced tasks with very little work.</span></span>

<span data-ttu-id="17626-108">В следующих примерах показано, как собрать определенные сведения, применяя командлет `Get-CimInstance` к произвольному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="17626-108">The following examples demonstrate how to collect specific information by using `Get-CimInstance` against an arbitrary computer.</span></span>
<span data-ttu-id="17626-109">Значение параметра **ComputerName** задается точкой **.**, представляющей локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="17626-109">We specify the **ComputerName** parameter with the dot value (**.**), which represents the local computer.</span></span>
<span data-ttu-id="17626-110">Здесь можно указать имя или IP-адрес, связанные с любым компьютером, к которому требуется получить доступ через инструментарий WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-110">You can specify a name or IP address associated with any computer you can reach through WMI.</span></span>
<span data-ttu-id="17626-111">Чтобы получить сведения о локальном компьютере, параметр **ComputerName** можно опустить.</span><span class="sxs-lookup"><span data-stu-id="17626-111">To retrieve information about the local computer, you could omit the **ComputerName** parameter.</span></span>

### <a name="listing-desktop-settings"></a><span data-ttu-id="17626-112">Вывод параметров рабочего стола</span><span class="sxs-lookup"><span data-stu-id="17626-112">Listing Desktop Settings</span></span>

<span data-ttu-id="17626-113">Для начала рассмотрим команду, собирающую сведения о рабочих столах локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="17626-113">We'll begin with a command that collects information about the desktops on the local computer.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop -ComputerName .
```

<span data-ttu-id="17626-114">Эта команда возвращает сведения обо всех рабочих столах, вне зависимости от их использования.</span><span class="sxs-lookup"><span data-stu-id="17626-114">This returns information for all desktops, whether they are in use or not.</span></span>

> [!NOTE]
> <span data-ttu-id="17626-115">Сведения, возвращаемые некоторыми классами WMI, могут быть очень подробными и часто содержат метаданные о классе WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-115">Information returned by some WMI classes can be very detailed, and often include metadata about the WMI class.</span></span>
<span data-ttu-id="17626-116">Так как имена большинства этих свойств метаданных начинаются с **Cim**, эти свойства можно отфильтровать с помощью `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="17626-116">Because most of these metadata properties have names that begin with **Cim**, you can filter the properties using `Select-Object`.</span></span>
<span data-ttu-id="17626-117">Укажите параметр **-ExcludeProperty**, используя "Cim\*" как значение.</span><span class="sxs-lookup"><span data-stu-id="17626-117">Specify the **-ExcludeProperty** parameter with "Cim\*" as the value.</span></span>
<span data-ttu-id="17626-118">Например:</span><span class="sxs-lookup"><span data-stu-id="17626-118">For example:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop -ComputerName . | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="17626-119">Чтобы отфильтровать метаданные, используйте оператор конвейера (|) для отправки результатов команды `Get-CimInstance` в `Select-Object -ExcludeProperty "CIM*"`.</span><span class="sxs-lookup"><span data-stu-id="17626-119">To filter out the metadata, use a pipeline operator (|) to send the results of the `Get-CimInstance` command to `Select-Object -ExcludeProperty "CIM*"`.</span></span>

### <a name="listing-bios-information"></a><span data-ttu-id="17626-120">Вывод сведений о BIOS</span><span class="sxs-lookup"><span data-stu-id="17626-120">Listing BIOS Information</span></span>

<span data-ttu-id="17626-121">Класс WMI **Win32_BIOS** возвращает довольно компактные и полные сведения о системной BIOS локального компьютера:</span><span class="sxs-lookup"><span data-stu-id="17626-121">The WMI **Win32_BIOS** class returns fairly compact and complete information about the system BIOS on the local computer:</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -ComputerName .
```

### <a name="listing-processor-information"></a><span data-ttu-id="17626-122">Вывод сведений о процессоре</span><span class="sxs-lookup"><span data-stu-id="17626-122">Listing Processor Information</span></span>

<span data-ttu-id="17626-123">Общие сведения о процессоре можно получить с помощью класса **Win32_Processor** инструментария WMI, но вам, скорее всего, потребуется отфильтровать полученные данные:</span><span class="sxs-lookup"><span data-stu-id="17626-123">You can retrieve general processor information by using WMI's **Win32_Processor** class, although you will likely want to filter the information:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Processor -ComputerName . | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="17626-124">Чтобы получить общую строку описания семейства процессора, достаточно вернуть свойство **SystemType**:</span><span class="sxs-lookup"><span data-stu-id="17626-124">For a generic description string of the processor family, you can just return the **SystemType** property:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName . | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

### <a name="listing-computer-manufacturer-and-model"></a><span data-ttu-id="17626-125">Вывод производителя и модели компьютера</span><span class="sxs-lookup"><span data-stu-id="17626-125">Listing Computer Manufacturer and Model</span></span>

<span data-ttu-id="17626-126">Сведения о модели компьютера также доступны в **Win32_ComputerSystem**.</span><span class="sxs-lookup"><span data-stu-id="17626-126">Computer model information is also available from **Win32_ComputerSystem**.</span></span>
<span data-ttu-id="17626-127">Чтобы получить данные поставщика вычислительной техники (OEM), стандартные отображаемые выходные данные фильтровать не нужно:</span><span class="sxs-lookup"><span data-stu-id="17626-127">The standard displayed output will not need any filtering to provide OEM data:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

<span data-ttu-id="17626-128">Выходные данные из команд, подобных показанной выше и возвращающих сведения напрямую от аппаратного обеспечения, не могут быть дополнены.</span><span class="sxs-lookup"><span data-stu-id="17626-128">Your output from commands such as this, which return information directly from some hardware, is only as good as the data you have.</span></span>
<span data-ttu-id="17626-129">Иногда сведения неверно сконфигурированы производителем оборудования и недоступны для запроса.</span><span class="sxs-lookup"><span data-stu-id="17626-129">Some information is not correctly configured by hardware manufacturers and may therefore be unavailable.</span></span>

### <a name="listing-installed-hotfixes"></a><span data-ttu-id="17626-130">Вывод установленных исправлений</span><span class="sxs-lookup"><span data-stu-id="17626-130">Listing Installed Hotfixes</span></span>

<span data-ttu-id="17626-131">Список всех установленных исправлений можно получить с помощью **Win32_QuickFixEngineering**:</span><span class="sxs-lookup"><span data-stu-id="17626-131">You can list all installed hotfixes by using **Win32_QuickFixEngineering**:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -ComputerName .
```

<span data-ttu-id="17626-132">Этот класс возвращает список исправлений в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="17626-132">This class returns a list of hotfixes that looks like this:</span></span>

```output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

<span data-ttu-id="17626-133">Для получения более кратких сведений нужно исключить некоторые свойства.</span><span class="sxs-lookup"><span data-stu-id="17626-133">For more succinct output, you may want to exclude some properties.</span></span>
<span data-ttu-id="17626-134">Параметр **Property** в `Get-CimInstance`позволяет выбрать только идентификаторы **HotFixID**, однако на самом деле возвращается больше данных, так как по умолчанию отображаются все метаданные:</span><span class="sxs-lookup"><span data-stu-id="17626-134">Although you can use the `Get-CimInstance`'s **Property** parameter to choose only the **HotFixID**, doing so will actually return more information, because all the metadata is displayed by default:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -ComputerName . -Property HotFixID
```

```output
PSShowComputerName    : True
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4048951
InstalledBy           :
ServicePackInEffect   :
PSComputerName        : .
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

<span data-ttu-id="17626-135">Дополнительные данные выводятся, так как параметр Property в `Get-CimInstance` ограничивает свойства, возвращаемые из экземпляров класса, но не объекты, возвращаемые оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17626-135">The additional data is returned, because the Property parameter in `Get-CimInstance` restricts the properties returned from WMI class instances, not the object returned to Windows PowerShell.</span></span>
<span data-ttu-id="17626-136">Командлет `Select-Object` позволяет сократить возвращаемые выходные данные:</span><span class="sxs-lookup"><span data-stu-id="17626-136">To reduce the output, use `Select-Object`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -ComputerName . -Property HotFixId | Select-Object -Property HotFixId
```

```output
HotFixId
--------
KB4048951
```

### <a name="listing-operating-system-version-information"></a><span data-ttu-id="17626-137">Вывод сведений о версии операционной среды</span><span class="sxs-lookup"><span data-stu-id="17626-137">Listing Operating System Version Information</span></span>

<span data-ttu-id="17626-138">Свойства класса **Win32_OperatingSystem** включают сведения о версии операционной системы и пакета обновления.</span><span class="sxs-lookup"><span data-stu-id="17626-138">The **Win32_OperatingSystem** class properties include version and service pack information.</span></span>
<span data-ttu-id="17626-139">Эти свойства можно выбрать явным образом, чтобы получить сводные данные по версиям из **Win32_OperatingSystem**:</span><span class="sxs-lookup"><span data-stu-id="17626-139">You can explicitly select only these properties to get a version information summary from **Win32_OperatingSystem**:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

<span data-ttu-id="17626-140">С параметром **Property** в `Select-Object` можно использовать подстановочные символы.</span><span class="sxs-lookup"><span data-stu-id="17626-140">You can also use wildcards with the `Select-Object`'s **Property** parameter.</span></span>
<span data-ttu-id="17626-141">Поскольку в рассматриваемом случае важны все свойства, имена которых начинаются с **Build** либо с **ServicePack**, указанную строку можно сократить:</span><span class="sxs-lookup"><span data-stu-id="17626-141">Because all the properties beginning with either **Build** or **ServicePack** are important to use here, we can shorten this to the following form:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property Build*,OSType,ServicePack*
```

```output
BuildNumber             : 16299
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

### <a name="listing-local-users-and-owner"></a><span data-ttu-id="17626-142">Вывод локальных пользователей и владельца</span><span class="sxs-lookup"><span data-stu-id="17626-142">Listing Local Users and Owner</span></span>

<span data-ttu-id="17626-143">Общие сведения о локальных пользователях — количество лицензированных пользователей, текущее число пользователей и имя владельца — можно получить, выбрав соответствующие свойства **Win32_OperatingSystem**.</span><span class="sxs-lookup"><span data-stu-id="17626-143">Local general user information — number of licensed users, current number of users, and owner name — can be found with a selection of **Win32_OperatingSystem** class' properties.</span></span>
<span data-ttu-id="17626-144">Отображаемые свойства можно указать явным образом:</span><span class="sxs-lookup"><span data-stu-id="17626-144">You can explicitly select the properties to display like this:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

<span data-ttu-id="17626-145">В более сжатом варианте используются подстановочные символы:</span><span class="sxs-lookup"><span data-stu-id="17626-145">A more succinct version using wildcards is:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property *user*
```

### <a name="getting-available-disk-space"></a><span data-ttu-id="17626-146">Получение сведений о доступном месте на диске</span><span class="sxs-lookup"><span data-stu-id="17626-146">Getting Available Disk Space</span></span>

<span data-ttu-id="17626-147">Чтобы получить сведения о дисковом пространстве и свободном месте на локальных дисках, можно воспользоваться классом Win32_LogicalDisk инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-147">To see the disk space and free space for local drives, you can use the Win32_LogicalDisk WMI class.</span></span>
<span data-ttu-id="17626-148">Для просмотра следует выбрать только те экземпляры, у которых свойство DriveType принимает значение 3, так как именно оно используется инструментарием WMI для постоянных жестких дисков.</span><span class="sxs-lookup"><span data-stu-id="17626-148">You need to see only instances with a DriveType of 3 — the value WMI uses for fixed hard disks.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" -ComputerName .

DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .

Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" -ComputerName . | Measure-Object -Property FreeSpace,Size -Sum | Select-Object -Property Property,Sum

Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

### <a name="getting-logon-session-information"></a><span data-ttu-id="17626-149">Получение сведений о сеансах входа в систему</span><span class="sxs-lookup"><span data-stu-id="17626-149">Getting Logon Session Information</span></span>

<span data-ttu-id="17626-150">Общие сведения о сеансах входа в систему, связанных с пользователями, можно получить через класс **Win32_LogonSession** инструментария WMI:</span><span class="sxs-lookup"><span data-stu-id="17626-150">You can get general information about logon sessions associated with users through the **Win32_LogonSession** WMI class:</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogonSession -ComputerName .
```

### <a name="getting-the-user-logged-on-to-a-computer"></a><span data-ttu-id="17626-151">Получение сведений о пользователе, выполнившем вход на компьютер</span><span class="sxs-lookup"><span data-stu-id="17626-151">Getting the User Logged on to a Computer</span></span>

<span data-ttu-id="17626-152">Имя пользователя, выполнившего вход на определенный компьютер, можно отобразить с помощью Win32_ComputerSystem.</span><span class="sxs-lookup"><span data-stu-id="17626-152">You can display the user logged on to a particular computer system using Win32_ComputerSystem.</span></span>
<span data-ttu-id="17626-153">Приведенная ниже команда возвращает только пользователей, выполнивших вход на рабочий стол системы:</span><span class="sxs-lookup"><span data-stu-id="17626-153">This command returns only the user logged on to the system desktop:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName -ComputerName .
```

### <a name="getting-local-time-from-a-computer"></a><span data-ttu-id="17626-154">Получение сведений о местном времени компьютера</span><span class="sxs-lookup"><span data-stu-id="17626-154">Getting Local Time from a Computer</span></span>

<span data-ttu-id="17626-155">Сведения о текущем местном времени определенного компьютера можно получить с помощью класса **Win32_LocalTime** инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-155">You can retrieve the current local time on a specific computer by using the **Win32_LocalTime** WMI class.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LocalTime -ComputerName .

Day          : 15
DayOfWeek    : 4
Hour         : 12
Milliseconds :
Minute       : 11
Month        : 6
Quarter      : 2
Second       : 52
WeekInMonth  : 3
Year         : 2017
PSComputerName : .
```

### <a name="displaying-service-status"></a><span data-ttu-id="17626-156">Отображение состояния службы</span><span class="sxs-lookup"><span data-stu-id="17626-156">Displaying Service Status</span></span>

<span data-ttu-id="17626-157">Для просмотра состояния всех служб на определенном компьютере можно локально воспользоваться командлетом `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="17626-157">To view the status of all services on a specific computer, you can locally use the `Get-Service` cmdlet.</span></span>
<span data-ttu-id="17626-158">Для удаленных систем можно использовать класс **Win32_Service** инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="17626-158">For remote systems, you can use the **Win32_Service** WMI class.</span></span>
<span data-ttu-id="17626-159">Если использовать `Select-Object` для фильтрования **Status**, **Name** и **DisplayName**, формат вывода будет идентичен формату вывода командлета `Get-Service`:</span><span class="sxs-lookup"><span data-stu-id="17626-159">If you also use `Select-Object` to filter the results to **Status**, **Name**, and **DisplayName**, the output format will be almost identical to that from `Get-Service`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -ComputerName . | Select-Object -Property Status,Name,DisplayName
```

<span data-ttu-id="17626-160">Чтобы полностью отобразить службы с очень длинными именами, может потребоваться использовать командлет `Format-Table` с параметрами **AutoSize** и **Wrap**, позволяющими оптимизировать ширину столбцов и переносить длинные имена на следующие строки вместо их усечения:</span><span class="sxs-lookup"><span data-stu-id="17626-160">To allow the complete display of names for the occasional services with extremely long names, you may want to use `Format-Table` with the **AutoSize** and **Wrap** parameters, to optimize column width and allow long names to wrap instead of being truncated:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -ComputerName . | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
