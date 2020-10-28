---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Сбор информации о компьютерах
description: В этой статье описывается, как собирать сведения о конфигурации компьютера с помощью командлетов WMI и CIM.
ms.openlocfilehash: 5088960ab7c049085a9d7c05ec4571b6fd7e3545
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500595"
---
# <a name="collecting-information-about-computers"></a>Сбор информации о компьютерах

Командлеты из модуля **CimCmdlets**  — самые важные для общих задач управления системой. Все ключевые параметры подсистемы доступны через инструментарий WMI. Более того, инструментарий WMI обрабатывает данные как объекты, сгруппированные в коллекции из одного или нескольких элементов. Поскольку Windows PowerShell также работает с объектами и имеет конвейер, позволяющий одинаково обрабатывать отдельный объект или несколько объектов, общий доступ к инструментарию WMI предоставляет возможность выполнять некоторые сложные задачи с небольшими затратами усилий.

## <a name="listing-desktop-settings"></a>Вывод параметров рабочего стола

Для начала рассмотрим команду, собирающую сведения о рабочих столах локального компьютера.

```powershell
Get-CimInstance -ClassName Win32_Desktop
```

Эта команда возвращает сведения обо всех рабочих столах, вне зависимости от их использования.

> [!NOTE]
> Сведения, возвращаемые некоторыми классами WMI, могут быть очень подробными и часто содержат метаданные о классе WMI.

Так как имена большинства этих свойств метаданных начинаются с **Cim** , эти свойства можно отфильтровать с помощью `Select-Object`. Укажите параметр **-ExcludeProperty** , используя "Cim*" как значение. Пример:

```powershell
Get-CimInstance -ClassName Win32_Desktop | Select-Object -ExcludeProperty "CIM*"
```

Чтобы отфильтровать метаданные, используйте оператор конвейера (|) для отправки результатов команды `Get-CimInstance` в `Select-Object -ExcludeProperty "CIM*"`.

## <a name="listing-bios-information"></a>Вывод сведений о BIOS

Класс WMI **Win32_BIOS** возвращает довольно компактные и полные сведения о системной BIOS локального компьютера:

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

## <a name="listing-processor-information"></a>Вывод сведений о процессоре

Общие сведения о процессоре можно получить с помощью класса **Win32_Processor** инструментария WMI, но вам, скорее всего, потребуется отфильтровать полученные данные:

```powershell
Get-CimInstance -ClassName Win32_Processor | Select-Object -ExcludeProperty "CIM*"
```

Чтобы получить общую строку описания семейства процессора, достаточно вернуть свойство **SystemType** :

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a>Вывод производителя и модели компьютера

Сведения о модели компьютера также доступны в **Win32_ComputerSystem** . Чтобы получить данные поставщика вычислительной техники (OEM), стандартные отображаемые выходные данные фильтровать не нужно:

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```Output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

Выходные данные из команд, подобных показанной выше и возвращающих сведения напрямую от аппаратного обеспечения, не могут быть дополнены. Иногда сведения неверно сконфигурированы производителем оборудования и недоступны для запроса.

## <a name="listing-installed-hotfixes"></a>Вывод установленных исправлений

Список всех установленных исправлений можно получить с помощью **Win32_QuickFixEngineering** :

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering
```

Этот класс возвращает список исправлений в следующем виде:

```Output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

Для получения более кратких сведений нужно исключить некоторые свойства. Параметр **Property** в `Get-CimInstance`позволяет выбрать только идентификаторы **HotFixID** , однако на самом деле возвращается больше данных, так как по умолчанию отображаются все метаданные:

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixID
```

```Output
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4533002
InstalledBy           :
ServicePackInEffect   :
PSComputerName        :
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name…}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
...
```

Дополнительные данные выводятся, так как параметр **Property** в `Get-CimInstance` ограничивает свойства, возвращаемые из экземпляров класса WMI, но не объекты, возвращаемые оболочке PowerShell. Командлет `Select-Object` позволяет сократить возвращаемые выходные данные:

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixId | Select-Object -Property HotFixId
```

```Output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a>Вывод сведений о версии операционной среды

Свойства класса **Win32_OperatingSystem** включают сведения о версии операционной системы и пакета обновления. Эти свойства можно выбрать явным образом, чтобы получить сводные данные по версиям из **Win32_OperatingSystem** :

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

С параметром **Property** в `Select-Object` можно использовать подстановочные символы. Поскольку в рассматриваемом случае важны все свойства, имена которых начинаются с **Build** либо с **ServicePack** , указанную строку можно сократить:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property Build*,OSType,ServicePack*
```

```Output
BuildNumber             : 18362
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

## <a name="listing-local-users-and-owner"></a>Вывод локальных пользователей и владельца

Общие сведения о локальных пользователях — количество лицензированных пользователей, текущее число пользователей и имя владельца — можно получить, выбрав свойства класса **Win32_OperatingSystem** . Отображаемые свойства можно указать явным образом:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

В более сжатом варианте используются подстановочные символы:

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a>Получение сведений о доступном месте на диске

Чтобы получить сведения о дисковом пространстве и свободном месте на локальных дисках, можно воспользоваться классом Win32_LogicalDisk инструментария WMI.
Для просмотра следует выбрать только те экземпляры, у которых свойство DriveType принимает значение 3, так как именно оно используется инструментарием WMI для постоянных жестких дисков.

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
```

```Output
DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .
```

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" |
  Measure-Object -Property FreeSpace,Size -Sum |
    Select-Object -Property Property,Sum
```

```Output
Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

## <a name="getting-logon-session-information"></a>Получение сведений о сеансах входа в систему

Общие сведения о сеансах входа в систему, связанных с пользователями, можно получить через класс **Win32_LogonSession** инструментария WMI:

```powershell
Get-CimInstance -ClassName Win32_LogonSession
```

## <a name="getting-the-user-logged-on-to-a-computer"></a>Получение сведений о пользователе, выполнившем вход на компьютер

Имя пользователя, выполнившего вход на определенный компьютер, можно отобразить с помощью Win32_ComputerSystem. Приведенная ниже команда возвращает только пользователей, выполнивших вход на рабочий стол системы:

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName
```

## <a name="getting-local-time-from-a-computer"></a>Получение сведений о местном времени компьютера

Сведения о текущем местном времени определенного компьютера можно получить с помощью класса **Win32_LocalTime** инструментария WMI.

```powershell
Get-CimInstance -ClassName Win32_LocalTime
```

```Output
Day            : 23
DayOfWeek      : 1
Hour           : 8
Milliseconds   :
Minute         : 52
Month          : 12
Quarter        : 4
Second         : 55
WeekInMonth    : 4
Year           : 2019
PSComputerName :
```

## <a name="displaying-service-status"></a>Отображение состояния службы

Для просмотра состояния всех служб на определенном компьютере можно локально воспользоваться командлетом `Get-Service`. Для удаленных систем можно использовать класс **Win32_Service** инструментария WMI. Если использовать `Select-Object` для фильтрования **Status** , **Name** и **DisplayName** , формат вывода будет идентичен формату вывода командлета `Get-Service`:

```powershell
Get-CimInstance -ClassName Win32_Service | Select-Object -Property Status,Name,DisplayName
```

Чтобы полностью отобразить службы с очень длинными именами, может потребоваться использовать командлет `Format-Table` с параметрами **AutoSize** и **Wrap** , позволяющими оптимизировать ширину столбцов и переносить длинные имена на следующие строки вместо их усечения:

```powershell
Get-CimInstance -ClassName Win32_Service | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
