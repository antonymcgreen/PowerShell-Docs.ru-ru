---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сбор информации о компьютерах
ms.assetid: 9e7b6a2d-34f7-4731-a92c-8b3382eb51bb
ms.openlocfilehash: d837684108656e17ebf26189bd4841c5de01051c
ms.sourcegitcommit: 806cf87488b80800b9f50a8af286e8379519a034
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293169"
---
# <a name="collecting-information-about-computers"></a>Сбор информации о компьютерах

Командлеты из модуля **CimCmdlets** — самые важные для общих задач управления системой.
Все ключевые параметры подсистемы доступны через инструментарий WMI.
Более того, инструментарий WMI обрабатывает данные как объекты, сгруппированные в коллекции из одного или нескольких элементов.
Поскольку Windows PowerShell также работает с объектами и имеет конвейер, позволяющий одинаково обрабатывать отдельный объект или несколько объектов, общий доступ к инструментарию WMI предоставляет возможность выполнять некоторые сложные задачи с небольшими затратами усилий.

В следующих примерах показано, как собрать определенные сведения, применяя командлет `Get-CimInstance` к произвольному компьютеру.
Значение параметра **ComputerName** задается точкой **.**, представляющей локальный компьютер.
Здесь можно указать имя или IP-адрес, связанные с любым компьютером, к которому требуется получить доступ через инструментарий WMI.
Чтобы получить сведения о локальном компьютере, параметр **ComputerName** можно опустить.

## <a name="listing-desktop-settings"></a>Вывод параметров рабочего стола

Для начала рассмотрим команду, собирающую сведения о рабочих столах локального компьютера.

```powershell
Get-CimInstance -ClassName Win32_Desktop -ComputerName .
```

Эта команда возвращает сведения обо всех рабочих столах, вне зависимости от их использования.

> [!NOTE]
> Сведения, возвращаемые некоторыми классами WMI, могут быть очень подробными и часто содержат метаданные о классе WMI.
Так как имена большинства этих свойств метаданных начинаются с **Cim**, эти свойства можно отфильтровать с помощью `Select-Object`.
Укажите параметр **-ExcludeProperty**, используя "Cim*" как значение.
Например:

```powershell
Get-CimInstance -ClassName Win32_Desktop -ComputerName . | Select-Object -ExcludeProperty "CIM*"
```

Чтобы отфильтровать метаданные, используйте оператор конвейера (|) для отправки результатов команды `Get-CimInstance` в `Select-Object -ExcludeProperty "CIM*"`.

## <a name="listing-bios-information"></a>Вывод сведений о BIOS

Класс WMI **Win32_BIOS** возвращает довольно компактные и полные сведения о системной BIOS локального компьютера:

```powershell
Get-CimInstance -ClassName Win32_BIOS -ComputerName .
```

## <a name="listing-processor-information"></a>Вывод сведений о процессоре

Общие сведения о процессоре можно получить с помощью класса **Win32_Processor** инструментария WMI, но вам, скорее всего, потребуется отфильтровать полученные данные:

```powershell
Get-CimInstance -ClassName Win32_Processor -ComputerName . | Select-Object -ExcludeProperty "CIM*"
```

Чтобы получить общую строку описания семейства процессора, достаточно вернуть свойство **SystemType**:

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName . | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a>Вывод производителя и модели компьютера

Сведения о модели компьютера также доступны в **Win32_ComputerSystem**.
Чтобы получить данные поставщика вычислительной техники (OEM), стандартные отображаемые выходные данные фильтровать не нужно:

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

Выходные данные из команд, подобных показанной выше и возвращающих сведения напрямую от аппаратного обеспечения, не могут быть дополнены.
Иногда сведения неверно сконфигурированы производителем оборудования и недоступны для запроса.

## <a name="listing-installed-hotfixes"></a>Вывод установленных исправлений

Список всех установленных исправлений можно получить с помощью **Win32_QuickFixEngineering**:

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -ComputerName .
```

Этот класс возвращает список исправлений в следующем виде:

```output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

Для получения более кратких сведений нужно исключить некоторые свойства.
Параметр **Property** в `Get-CimInstance`позволяет выбрать только идентификаторы **HotFixID**, однако на самом деле возвращается больше данных, так как по умолчанию отображаются все метаданные:

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

Дополнительные данные выводятся, так как параметр Property в `Get-CimInstance` ограничивает свойства, возвращаемые из экземпляров класса, но не объекты, возвращаемые оболочке Windows PowerShell.
Командлет `Select-Object` позволяет сократить возвращаемые выходные данные:

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -ComputerName . -Property HotFixId | Select-Object -Property HotFixId
```

```output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a>Вывод сведений о версии операционной среды

Свойства класса **Win32_OperatingSystem** включают сведения о версии операционной системы и пакета обновления.
Эти свойства можно выбрать явным образом, чтобы получить сводные данные по версиям из **Win32_OperatingSystem**:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

С параметром **Property** в `Select-Object` можно использовать подстановочные символы.
Поскольку в рассматриваемом случае важны все свойства, имена которых начинаются с **Build** либо с **ServicePack**, указанную строку можно сократить:

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

## <a name="listing-local-users-and-owner"></a>Вывод локальных пользователей и владельца

Общие сведения о локальных пользователях — количество лицензированных пользователей, текущее число пользователей и имя владельца — можно получить, выбрав соответствующие свойства **Win32_OperatingSystem**.
Отображаемые свойства можно указать явным образом:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

В более сжатом варианте используются подстановочные символы:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem -ComputerName . | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a>Получение сведений о доступном месте на диске

Чтобы получить сведения о дисковом пространстве и свободном месте на локальных дисках, можно воспользоваться классом Win32_LogicalDisk инструментария WMI.
Для просмотра следует выбрать только те экземпляры, у которых свойство DriveType принимает значение 3, так как именно оно используется инструментарием WMI для постоянных жестких дисков.

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

## <a name="getting-logon-session-information"></a>Получение сведений о сеансах входа в систему

Общие сведения о сеансах входа в систему, связанных с пользователями, можно получить через класс **Win32_LogonSession** инструментария WMI:

```powershell
Get-CimInstance -ClassName Win32_LogonSession -ComputerName .
```

## <a name="getting-the-user-logged-on-to-a-computer"></a>Получение сведений о пользователе, выполнившем вход на компьютер

Имя пользователя, выполнившего вход на определенный компьютер, можно отобразить с помощью Win32_ComputerSystem.
Приведенная ниже команда возвращает только пользователей, выполнивших вход на рабочий стол системы:

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName -ComputerName .
```

## <a name="getting-local-time-from-a-computer"></a>Получение сведений о местном времени компьютера

Сведения о текущем местном времени определенного компьютера можно получить с помощью класса **Win32_LocalTime** инструментария WMI.

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

## <a name="displaying-service-status"></a>Отображение состояния службы

Для просмотра состояния всех служб на определенном компьютере можно локально воспользоваться командлетом `Get-Service`.
Для удаленных систем можно использовать класс **Win32_Service** инструментария WMI.
Если использовать `Select-Object` для фильтрования **Status**, **Name** и **DisplayName**, формат вывода будет идентичен формату вывода командлета `Get-Service`:

```powershell
Get-CimInstance -ClassName Win32_Service -ComputerName . | Select-Object -Property Status,Name,DisplayName
```

Чтобы полностью отобразить службы с очень длинными именами, может потребоваться использовать командлет `Format-Table` с параметрами **AutoSize** и **Wrap**, позволяющими оптимизировать ширину столбцов и переносить длинные имена на следующие строки вместо их усечения:

```powershell
Get-CimInstance -ClassName Win32_Service -ComputerName . | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
