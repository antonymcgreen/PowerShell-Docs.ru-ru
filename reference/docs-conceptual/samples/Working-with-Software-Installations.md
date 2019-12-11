---
ms.date: 06/03/2019
keywords: powershell,командлет
title: Работа с программами установки программного обеспечения
ms.openlocfilehash: 6d2111a332f0e8c1b545186d3d950e936aed1834
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "66830286"
---
# <a name="working-with-software-installations"></a>Работа с программами установки программного обеспечения

Доступ к приложениям, использующим установщик Windows, можно получить в классе **Win32_Product** WMI, но не все современные приложения используют установщик Windows.
Установщик Windows обычно не управляет приложениями, использующими другие процедуры установки.
Конкретные техники работы с этими приложениями зависят от программного обеспечения установщика и решений, принятых разработчиком приложения. Например, для управления приложениями, установленными путем копирования файлов в папку на компьютере, обычно не используются описанные здесь методы. Вы можете управлять этими приложениями, как файлами и папками, с помощью способов, приведенных в статье [Работа с файлами и папками](Working-with-Files-and-Folders.md).

> [!CAUTION]
> Класс **Win32_Product** не оптимизирован для запросов. Если выполняются запросы, использующие фильтры с подстановочными знаками, то WMI будет использовать поставщика MSI для перечисления всех установленных продуктов, а затем последовательно проанализирует весь список с применением фильтра. При этом также инициируется проверка согласованности установленных пакетов для проверки и исправления установки. Проверка выполняется медленно и может привести к ошибкам в журнале событий. Подробные сведения см. в [статье базы знаний 974524](https://support.microsoft.com/help/974524).

## <a name="listing-windows-installer-applications"></a>Создание списков приложений установщика Windows

Чтобы создать список приложений, установленных с помощью установщика Windows в локальной или удаленной системе, используйте следующий простой запрос WMI:

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)"
```

```Output
Name               Caption                     Vendor                 Version      IdentifyingNumber
----               -------                     ------                 -------      -----------------
Microsoft .NET ... Microsoft .NET Core Runt... Microsoft Corporation  16.72.26629  {ACC73072-9AD5-416C-94B...
```

Чтобы отобразить все свойства объекта **Win32_Product**, используйте параметр **Properties** командлетов форматирования, например `Format-List` со значением `*` (все).

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)" |
    Format-List -Property *
```

```Output
Name                  : Microsoft .NET Core Runtime - 2.1.2 (x64)
Version               : 16.72.26629
InstallState          : 5
Caption               : Microsoft .NET Core Runtime - 2.1.2 (x64)
Description           : Microsoft .NET Core Runtime - 2.1.2 (x64)
IdentifyingNumber     : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
SKUNumber             :
Vendor                : Microsoft Corporation
AssignmentType        : 1
HelpLink              :
HelpTelephone         :
InstallDate           : 20180816
InstallDate2          :
InstallLocation       :
InstallSource         : C:\ProgramData\Package Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
Language              : 1033
LocalPackage          : C:\WINDOWS\Installer\414c96e.msi
PackageCache          : C:\WINDOWS\Installer\414c96e.msi
PackageCode           : {D20AC783-1EC5-4A58-9277-F452F5EB9AD9}
PackageName           : dotnet-runtime-2.1.2-win-x64.msi
ProductID             :
RegCompany            :
RegOwner              :
Transforms            :
URLInfoAbout          :
URLUpdateInfo         :
WordCount             : 0
PSComputerName        :
CimClass              : root/cimv2:Win32_Product
CimInstanceProperties : {Caption, Description, IdentifyingNumber, Name...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

Также можно использовать параметр `Get-CimInstance` **Filter**, чтобы выбрать только Microsoft .NET Framework 2.0. Для значения параметра **Filter** используется синтаксис языка запросов WMI (WQL), а не синтаксис Windows PowerShell. Например:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property *
```

Чтобы получить список только интересующих вас свойств, используйте параметр **Property** командлетов форматирования.

```powershell
Get-CimInstance -Class Win32_Product  -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
```

```Output
Name              : Microsoft .NET Core Runtime - 2.1.2 (x64)
InstallDate       : 20180816
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\414c96e.msi
Vendor            : Microsoft Corporation
Version           : 16.72.26629
IdentifyingNumber : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
```

## <a name="listing-all-uninstallable-applications"></a>Создание списка всех удаленных приложений

Так как большинство стандартных приложений регистрируют программу удаления в Windows, с ними можно работать локально, в реестре Windows. Не существует гарантированного способа найти все приложения в системе. Но можно найти все программы в списках, отображаемых в окне **Установка и удаление программ**. В окне **Установка или удаление программ** выполняется поиск этих приложений в следующем разделе реестра:

`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.

В этом разделе можно найти приложения. Чтобы упростить просмотр раздела Uninstall, можно сопоставить диск PowerShell с таким путем реестра:

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```
Теперь диск с именем "Uninstall" можно использовать для быстрого и удобного поиска установок приложений. Количество установленных приложений можно найти, подсчитав количество разделов реестра в разделе "Удаление": Диск PowerShell:

```
(Get-ChildItem -Path Uninstall:).Count
459
```

С помощью разных методов, начиная с **Get-ChildItem**, можно дальше выполнять поиск в списке приложений. Чтобы получить список приложений и сохранить их в переменную **$UninstallableApplications**, используйте следующую команду:

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

Чтобы отобразить значения записей реестра в подразделах реестра раздела "Удаление", используйте метод GetValue. Значение метода является записью реестра.

Например, чтобы найти отображаемые имена приложений в разделе "Удаление", используйте следующую команду:

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

Нет никакой гарантии, что эти значения уникальны. В следующем примере два установленных элемента отображаются как Windows Media Encoder 9 Series:

```powershell
$UninstallableApplications | Where-Object -FilterScript { $_.GetValue("DisplayName") -eq "Windows Media Encoder 9 Series"}
```

```Output
Name                           Property
----                           --------
{ACC73072-9AD5-416C-94BF-D82DD AuthorizedCDFPrefix :
CEA0F1B}                       Comments            :
                               Contact             :
                               DisplayVersion      : 16.72.26629
                               HelpLink            :
                               HelpTelephone       :
                               InstallDate         : 20180816
                               InstallLocation     :
                               InstallSource       : C:\ProgramData\Package
                               Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
                               ModifyPath          : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               NoModify            : 1
                               Publisher           : Microsoft Corporation
                               Readme              :
                               Size                :
                               EstimatedSize       : 67156
                               SystemComponent     : 1
                               UninstallString     : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               URLInfoAbout        :
                               URLUpdateInfo       :
                               VersionMajor        : 16
                               VersionMinor        : 72
                               WindowsInstaller    : 1
                               Version             : 273180677
                               Language            : 1033
                               DisplayName         : Microsoft .NET Core Runtime - 2.1.2 (x64)
```

## <a name="installing-applications"></a>Установка приложений

Вы можете использовать класс **Win32_Product** для удаленной или локальной установки пакетов установщика Windows.

> [!NOTE]
> Чтобы установить приложение, запустите PowerShell, используя параметр "Запуск от имени администратора".

Если установка выполняется удаленно, используйте сетевой UNC-путь, чтобы указать путь к пакету MSI, так как подсистема WMI не распознает пути PowerShell. Например, чтобы установить пакет NewPackage.msi, расположенный в сетевой папке `\\AppServ\dsp` на удаленном компьютере PC01, введите следующую команду в командной строке PowerShell:

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

Приложения, которые не используют метод установщика Windows, могут включать специальные методы для автоматического развертывания конкретного приложения. Изучите документацию по приложению или обратитесь в службу поддержки поставщика приложения.

## <a name="removing-applications"></a>Удаление приложений

Удаление пакета установщика Windows с помощью PowerShell работает примерно так же, как и установка пакета. Далее представлен пример, в котором пакет для удаления выбирается на основе имени. В некоторых случаях его может быть проще отфильтровать с помощью **IdentifyingNumber**:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

Удаление других приложений не так просто, даже если оно выполняется локально. Строки удаления командной строки для этих приложений можно найти путем извлечения свойства **UninstallString**.
Этот способ работает для приложений установщика Windows и более старых программ, отображающихся в разделе "Удаление":

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

Выходные данные при необходимости можно отфильтровать по отображаемому имени:

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

Возможно, что эти строки нельзя будет напрямую использовать из командной строки PowerShell без внесения некоторых изменений.

## <a name="upgrading-windows-installer-applications"></a>Обновление приложений установщика Windows

Чтобы обновить приложение, необходимо знать название приложения и путь к пакету обновлений приложения. Получив эти сведения, вы можете обновить приложение с помощью одной команды PowerShell:

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
