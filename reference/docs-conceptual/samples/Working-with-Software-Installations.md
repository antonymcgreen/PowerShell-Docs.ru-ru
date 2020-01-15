---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Работа с программами установки программного обеспечения
ms.openlocfilehash: d164064418ad7a0209166c81a7c3cc32a9db300a
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737157"
---
# <a name="working-with-software-installations"></a><span data-ttu-id="b5711-103">Работа с программами установки программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b5711-103">Working with Software Installations</span></span>

<span data-ttu-id="b5711-104">Доступ к приложениям, использующим установщик Windows, можно получить в классе **Win32_Product** WMI, но не все современные приложения используют установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="b5711-104">Applications that are designed to use Windows Installer can be accessed through WMI's **Win32_Product** class, but not all applications in use today use the Windows Installer.</span></span>
<span data-ttu-id="b5711-105">Установщик Windows обычно не управляет приложениями, использующими другие процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="b5711-105">Applications that use alternate setup routines are not usually managed by the Windows Installer.</span></span>
<span data-ttu-id="b5711-106">Конкретные техники работы с этими приложениями зависят от программного обеспечения установщика и решений, принятых разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="b5711-106">Specific techniques for working with those applications depends on the installer software and decisions made by the application developer.</span></span> <span data-ttu-id="b5711-107">Например, для управления приложениями, установленными путем копирования файлов в папку на компьютере, обычно не используются описанные здесь методы.</span><span class="sxs-lookup"><span data-stu-id="b5711-107">For example, applications installed by copying the files to a folder on the computer usually cannot be managed by using techniques discussed here.</span></span> <span data-ttu-id="b5711-108">Вы можете управлять этими приложениями, как файлами и папками, с помощью способов, приведенных в статье [Работа с файлами и папками](Working-with-Files-and-Folders.md).</span><span class="sxs-lookup"><span data-stu-id="b5711-108">You can manage these applications as files and folders by using the techniques discussed in [Working With Files and Folders](Working-with-Files-and-Folders.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="b5711-109">Класс **Win32_Product** не оптимизирован для запросов.</span><span class="sxs-lookup"><span data-stu-id="b5711-109">The **Win32_Product** class is not query optimized.</span></span> <span data-ttu-id="b5711-110">Если выполняются запросы, использующие фильтры с подстановочными знаками, то WMI будет использовать поставщика MSI для перечисления всех установленных продуктов, а затем последовательно проанализирует весь список с применением фильтра.</span><span class="sxs-lookup"><span data-stu-id="b5711-110">Queries that use wildcard filters cause WMI to use the MSI provider to enumerate all installed products then parse the full list sequentially to handle the filter.</span></span> <span data-ttu-id="b5711-111">При этом также инициируется проверка согласованности установленных пакетов для проверки и исправления установки.</span><span class="sxs-lookup"><span data-stu-id="b5711-111">This also initiates a consistency check of packages installed, verifying and repairing the install.</span></span> <span data-ttu-id="b5711-112">Проверка выполняется медленно и может привести к ошибкам в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="b5711-112">The validation is a slow process and may result in errors in the event logs.</span></span> <span data-ttu-id="b5711-113">Подробные сведения см. в [статье базы знаний 974524](https://support.microsoft.com/help/974524).</span><span class="sxs-lookup"><span data-stu-id="b5711-113">For more information seek [KB article 974524](https://support.microsoft.com/help/974524).</span></span>

## <a name="listing-windows-installer-applications"></a><span data-ttu-id="b5711-114">Создание списков приложений установщика Windows</span><span class="sxs-lookup"><span data-stu-id="b5711-114">Listing Windows Installer Applications</span></span>

<span data-ttu-id="b5711-115">Чтобы создать список приложений, установленных с помощью установщика Windows в локальной или удаленной системе, используйте следующий простой запрос WMI:</span><span class="sxs-lookup"><span data-stu-id="b5711-115">To list the applications installed with the Windows Installer on a local or remote system, use the following simple WMI query:</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.5 (x64)"
```

```Output
Name             Caption                   Vendor                    Version       IdentifyingNumber
----             -------                   ------                    -------       -----------------
Microsoft .NET … Microsoft .NET Core Runt… Microsoft Corporation     16.84.26919   {BEB59D04-C6DD-4926-AFE…
```

<span data-ttu-id="b5711-116">Чтобы отобразить все свойства объекта **Win32_Product**, используйте параметр **Properties** командлетов форматирования, например `Format-List` со значением `*` (все).</span><span class="sxs-lookup"><span data-stu-id="b5711-116">To display all the properties of the **Win32_Product** object to the display, use the **Properties** parameter of the formatting cmdlets, such as the `Format-List` cmdlet, with a value of `*` (all).</span></span>

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.5 (x64)" |
    Format-List -Property *
```

```Output
Name                  : Microsoft .NET Core Runtime - 2.1.5 (x64)
Version               : 16.84.26919
InstallState          : 5
Caption               : Microsoft .NET Core Runtime - 2.1.5 (x64)
Description           : Microsoft .NET Core Runtime - 2.1.5 (x64)
IdentifyingNumber     : {BEB59D04-C6DD-4926-AFEB-410CBE2EBCE4}
SKUNumber             :
Vendor                : Microsoft Corporation
AssignmentType        : 1
HelpLink              :
HelpTelephone         :
InstallDate           : 20181105
InstallDate2          :
InstallLocation       :
InstallSource         : C:\ProgramData\Package Cache\{BEB59D04-C6DD-4926-AFEB-410CBE2EBCE4}v16.84.26919\
Language              : 1033
LocalPackage          : C:\WINDOWS\Installer\4f97a771.msi
PackageCache          : C:\WINDOWS\Installer\4f97a771.msi
PackageCode           : {9A271A10-039D-49EA-8D24-043D91B9F915}
PackageName           : dotnet-runtime-2.1.5-win-x64.msi
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

<span data-ttu-id="b5711-117">Можно также использовать параметр `Get-CimInstance` **Filter**, чтобы выбрать только среду выполнения Microsoft .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="b5711-117">Or, you could use the `Get-CimInstance` **Filter** parameter to select only Microsoft .NET 2.0 Runtime.</span></span> <span data-ttu-id="b5711-118">Для значения параметра **Filter** используется синтаксис языка запросов WMI (WQL), а не синтаксис Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5711-118">The value of the **Filter** parameter uses WMI Query Language (WQL) syntax, not Windows PowerShell syntax.</span></span> <span data-ttu-id="b5711-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5711-119">For example:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.5 (x64)'" |
  Format-List -Property *
```

<span data-ttu-id="b5711-120">Чтобы получить список только интересующих вас свойств, используйте параметр **Property** командлетов форматирования.</span><span class="sxs-lookup"><span data-stu-id="b5711-120">To list only the properties that interest you, use the **Property** parameter of the formatting cmdlets to list the desired properties.</span></span>

```powershell
Get-CimInstance -Class Win32_Product  -Filter "Name='Microsoft .NET Core Runtime - 2.1.5 (x64)'" |
  Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
```

```Output
Name              : Microsoft .NET Core Runtime - 2.1.5 (x64)
InstallDate       : 20180816
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\4f97a771.msi
Vendor            : Microsoft Corporation
Version           : 16.72.26629
IdentifyingNumber : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
```

## <a name="listing-all-uninstallable-applications"></a><span data-ttu-id="b5711-121">Создание списка всех удаленных приложений</span><span class="sxs-lookup"><span data-stu-id="b5711-121">Listing All Uninstallable Applications</span></span>

<span data-ttu-id="b5711-122">Так как большинство стандартных приложений регистрируют программу удаления в Windows, с ними можно работать локально, в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="b5711-122">Because most standard applications register an uninstaller with Windows, we can work with those locally by finding them in the Windows registry.</span></span> <span data-ttu-id="b5711-123">Не существует гарантированного способа найти все приложения в системе.</span><span class="sxs-lookup"><span data-stu-id="b5711-123">There is no guaranteed way to find every application on a system.</span></span> <span data-ttu-id="b5711-124">Но можно найти все программы в списках, отображаемых в окне **Установка и удаление программ** в следующем разделе реестра:</span><span class="sxs-lookup"><span data-stu-id="b5711-124">However, it is possible to find all programs with listings displayed in **Add or Remove Programs** in the following registry key:</span></span>

<span data-ttu-id="b5711-125">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span><span class="sxs-lookup"><span data-stu-id="b5711-125">`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall`.</span></span>

<span data-ttu-id="b5711-126">В этом разделе можно найти приложения.</span><span class="sxs-lookup"><span data-stu-id="b5711-126">We can examine this key to find applications.</span></span> <span data-ttu-id="b5711-127">Чтобы упростить просмотр раздела Uninstall, можно сопоставить диск PowerShell с таким путем реестра:</span><span class="sxs-lookup"><span data-stu-id="b5711-127">To make it easier to view the Uninstall key, we can map a PowerShell drive to this registry location:</span></span>

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```

<span data-ttu-id="b5711-128">Теперь диск с именем "Uninstall" можно использовать для быстрого и удобного поиска установок приложений.</span><span class="sxs-lookup"><span data-stu-id="b5711-128">We now have a drive named "Uninstall:" that can be used to quickly and conveniently look for application installations.</span></span> <span data-ttu-id="b5711-129">Количество установленных приложений можно найти, подсчитав количество разделов реестра в разделе "Удаление": Диск PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5711-129">We can find the number of installed applications by counting the number of registry keys in the Uninstall: PowerShell drive:</span></span>

```powershell
(Get-ChildItem -Path Uninstall:).Count
```

```Output
459
```

<span data-ttu-id="b5711-130">С помощью разных методов, начиная с `Get-ChildItem`, можно дальше выполнять поиск в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="b5711-130">We can search this list of applications further by using a variety of techniques, beginning with `Get-ChildItem`.</span></span> <span data-ttu-id="b5711-131">Чтобы получить список приложений и сохранить их в переменную `$UninstallableApplications`, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b5711-131">To get a list of applications and save them in the `$UninstallableApplications` variable, use the following command:</span></span>

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

<span data-ttu-id="b5711-132">Чтобы отобразить значения записей реестра в подразделах реестра раздела "Удаление", используйте метод GetValue.</span><span class="sxs-lookup"><span data-stu-id="b5711-132">To display the values of the registry entries in the registry keys under Uninstall, use the GetValue method of the registry keys.</span></span> <span data-ttu-id="b5711-133">Значение метода является записью реестра.</span><span class="sxs-lookup"><span data-stu-id="b5711-133">The value of the method is the name of the registry entry.</span></span>

<span data-ttu-id="b5711-134">Например, чтобы найти отображаемые имена приложений в разделе "Удаление", используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b5711-134">For example, to find the display names of applications in the Uninstall key, use the following command:</span></span>

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

<span data-ttu-id="b5711-135">Нет никакой гарантии, что эти значения уникальны.</span><span class="sxs-lookup"><span data-stu-id="b5711-135">There is no guarantee that these values are unique.</span></span> <span data-ttu-id="b5711-136">В следующем примере два установленных элемента отображаются как Windows Media Encoder 9 Series:</span><span class="sxs-lookup"><span data-stu-id="b5711-136">In the following example, two installed items appear as "Windows Media Encoder 9 Series":</span></span>

```powershell
$UninstallableApplications | Where-Object -FilterScript {
  $_.GetValue("DisplayName") -eq "Microsoft Silverlight"
}
```

```Output
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall

Name                           Property
----                           --------
{89F4137D-6C26-4A84-BDB8-2E5A4 AuthorizedCDFPrefix :
BB71E00}                       Comments            :
                               Contact             :
                               DisplayVersion      : 5.1.50918.0
                               HelpLink            : http://go.microsoft.com/fwlink/?LinkID=91955
                               HelpTelephone       :
                               InstallDate         : 20190115
                               InstallLocation     : C:\Program Files\Microsoft Silverlight\
                               InstallSource       : c:\ef64c54526db9c34cd477c103e68a254\
                               ModifyPath          : MsiExec.exe /X{89F4137D-6C26-4A84-BDB8-2E5A4BB71E00}
                               NoModify            : 1
                               NoRepair            : 1
                               Publisher           : Microsoft Corporation
                               Readme              :
                               Size                :
                               EstimatedSize       : 236432
                               UninstallString     : MsiExec.exe /X{89F4137D-6C26-4A84-BDB8-2E5A4BB71E00}
                               URLInfoAbout        :
                               URLUpdateInfo       :
                               VersionMajor        : 5
                               VersionMinor        : 1
                               WindowsInstaller    : 1
                               Version             : 84002534
                               Language            : 1033
                               DisplayName         : Microsoft Silverlight
                               sEstimatedSize2     : 79214
```

## <a name="installing-applications"></a><span data-ttu-id="b5711-137">Установка приложений</span><span class="sxs-lookup"><span data-stu-id="b5711-137">Installing Applications</span></span>

<span data-ttu-id="b5711-138">Вы можете использовать класс **Win32_Product** для удаленной или локальной установки пакетов установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="b5711-138">You can use the **Win32_Product** class to install Windows Installer packages, remotely or locally.</span></span>

> [!NOTE]
> <span data-ttu-id="b5711-139">Чтобы установить приложение, запустите PowerShell, используя параметр "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="b5711-139">To install an application, you must start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="b5711-140">Если установка выполняется удаленно, используйте сетевой UNC-путь, чтобы указать путь к пакету MSI, так как подсистема WMI не распознает пути PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5711-140">When installing remotely, use a Universal Naming Convention (UNC) network path to specify the path to the .msi package, because the WMI subsystem does not understand PowerShell paths.</span></span> <span data-ttu-id="b5711-141">Например, чтобы установить пакет NewPackage.msi, расположенный в сетевой папке `\\AppServ\dsp` на удаленном компьютере PC01, введите следующую команду в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5711-141">For example, to install the NewPackage.msi package located in the network share `\\AppServ\dsp` on the remote computer PC01, type the following command at the PowerShell prompt:</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

<span data-ttu-id="b5711-142">Приложения, которые не используют метод установщика Windows, могут включать специальные методы для автоматического развертывания конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="b5711-142">Applications that do not use Windows Installer technology may have application-specific methods for automated deployment.</span></span> <span data-ttu-id="b5711-143">Изучите документацию по приложению или обратитесь в службу поддержки поставщика приложения.</span><span class="sxs-lookup"><span data-stu-id="b5711-143">Check the documentation for the application or consult the application vendor's support system.</span></span>

## <a name="removing-applications"></a><span data-ttu-id="b5711-144">Удаление приложений</span><span class="sxs-lookup"><span data-stu-id="b5711-144">Removing Applications</span></span>

<span data-ttu-id="b5711-145">Удаление пакета установщика Windows с помощью PowerShell работает примерно так же, как и установка пакета.</span><span class="sxs-lookup"><span data-stu-id="b5711-145">Removing a Windows Installer package using PowerShell works in approximately the same way as installing a package.</span></span> <span data-ttu-id="b5711-146">Далее представлен пример, в котором пакет для удаления выбирается на основе имени. В некоторых случаях его может быть проще отфильтровать с помощью **IdentifyingNumber**:</span><span class="sxs-lookup"><span data-stu-id="b5711-146">Here is an example that selects the package to uninstall based on its name; in some cases it may be easier to filter with the **IdentifyingNumber**:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

<span data-ttu-id="b5711-147">Удаление других приложений не так просто, даже если оно выполняется локально.</span><span class="sxs-lookup"><span data-stu-id="b5711-147">Removing other applications is not quite so simple, even when done locally.</span></span> <span data-ttu-id="b5711-148">Строки удаления командной строки для этих приложений можно найти путем извлечения свойства **UninstallString**.</span><span class="sxs-lookup"><span data-stu-id="b5711-148">We can find the command line uninstallation strings for these applications by extracting the **UninstallString** property.</span></span>
<span data-ttu-id="b5711-149">Этот способ работает для приложений установщика Windows и более старых программ, отображающихся в разделе "Удаление":</span><span class="sxs-lookup"><span data-stu-id="b5711-149">This method works for Windows Installer applications and for older programs appearing under the Uninstall key:</span></span>

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="b5711-150">Выходные данные при необходимости можно отфильтровать по отображаемому имени:</span><span class="sxs-lookup"><span data-stu-id="b5711-150">You can filter the output by the display name, if you like:</span></span>

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

<span data-ttu-id="b5711-151">Возможно, что эти строки нельзя будет напрямую использовать из командной строки PowerShell без внесения некоторых изменений.</span><span class="sxs-lookup"><span data-stu-id="b5711-151">However, these strings may not be directly usable from the PowerShell prompt without some modification.</span></span>

## <a name="upgrading-windows-installer-applications"></a><span data-ttu-id="b5711-152">Обновление приложений установщика Windows</span><span class="sxs-lookup"><span data-stu-id="b5711-152">Upgrading Windows Installer Applications</span></span>

<span data-ttu-id="b5711-153">Чтобы обновить приложение, необходимо знать название приложения и путь к пакету обновлений приложения.</span><span class="sxs-lookup"><span data-stu-id="b5711-153">To upgrade an application, you need to know the name of the application and the path to the application upgrade package.</span></span> <span data-ttu-id="b5711-154">Получив эти сведения, вы можете обновить приложение с помощью одной команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5711-154">With that information, you can upgrade an application with a single PowerShell command:</span></span>

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
