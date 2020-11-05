---
ms.date: 12/12/2018
keywords: dsc,powershell,resource,gallery,setup
title: Установка дополнительных ресурсов DSC
description: В этой статье приведены ресурсы DSC, которые включены в модуль PSDesiredStateConfiguration. В ней также описывается, как найти и установить ресурсы из коллекции PowerShell.
ms.openlocfilehash: e75561ed539e06716c9a103f905b9d1e4f3e71d3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645132"
---
# <a name="install-additional-dsc-resources"></a><span data-ttu-id="1bda1-105">Установка дополнительных ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="1bda1-105">Install Additional DSC Resources</span></span>

<span data-ttu-id="1bda1-106">PowerShell включает в себя несколько установочных ресурсов для Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="1bda1-106">PowerShell includes several Out-of-the-box resources for Desired State Configuration (DSC).</span></span> <span data-ttu-id="1bda1-107">Модуль **PSDesiredStateConfiguration** содержит все OOB ресурсы DSC, доступные в конкретно вашем экземпляре PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bda1-107">The **PSDesiredStateConfiguration** module contains all of the OOB DSC resources available on your specific instance of PowerShell.</span></span>

<span data-ttu-id="1bda1-108">Это список OOB ресурсов, включенных в PowerShell 4.0, и описание возможностей ресурса.</span><span class="sxs-lookup"><span data-stu-id="1bda1-108">This is a list of the OOB resources included in PowerShell 4.0 and a description of the resource's capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="1bda1-109">Этот список неполный, так как количество OOB ресурсов увеличивалось с каждой версией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bda1-109">This is an incomplete list, as the number of OOB resources has grown with each version of PowerShell.</span></span>

|      <span data-ttu-id="1bda1-110">Ресурс</span><span class="sxs-lookup"><span data-stu-id="1bda1-110">Resource</span></span>      |                                                                                       <span data-ttu-id="1bda1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1bda1-111">Description</span></span>                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1bda1-112">**Файл**</span><span class="sxs-lookup"><span data-stu-id="1bda1-112">**File**</span></span>           | <span data-ttu-id="1bda1-113">Управляет состоянием файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="1bda1-113">Controls the state of files and directories.</span></span> <span data-ttu-id="1bda1-114">Копирует файлы из **Источника** в **Место назначения** и обновляет их при изменении **Источника** путем сравнения дат, контрольных сумм и хэшей.</span><span class="sxs-lookup"><span data-stu-id="1bda1-114">Copies files from a **Source** to a **Destination** and updates them when the **Source** changes by comparing dates, checksums, and hashes.</span></span> |
| <span data-ttu-id="1bda1-115">**Архив**</span><span class="sxs-lookup"><span data-stu-id="1bda1-115">**Archive**</span></span>        | <span data-ttu-id="1bda1-116">Распаковывает архивы и указывает местоположение.</span><span class="sxs-lookup"><span data-stu-id="1bda1-116">Unpacks archives and a specified location.</span></span> <span data-ttu-id="1bda1-117">Проверяет архивы с указанной **Контрольной суммой**.</span><span class="sxs-lookup"><span data-stu-id="1bda1-117">Validates the archives with a specified **Checksum**.</span></span>                                                                                         |
| <span data-ttu-id="1bda1-118">**Среда**</span><span class="sxs-lookup"><span data-stu-id="1bda1-118">**Environment**</span></span>    | <span data-ttu-id="1bda1-119">Управляет переменными среды.</span><span class="sxs-lookup"><span data-stu-id="1bda1-119">Manages environment variables.</span></span>                                                                                                                                                           |
| <span data-ttu-id="1bda1-120">**Группа**</span><span class="sxs-lookup"><span data-stu-id="1bda1-120">**Group**</span></span>          | <span data-ttu-id="1bda1-121">Управляет локальными группами и контролирует членство в группах.</span><span class="sxs-lookup"><span data-stu-id="1bda1-121">Manages local groups and controls group membership.</span></span>                                                                                                                                      |
| <span data-ttu-id="1bda1-122">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="1bda1-122">**Log**</span></span>            | <span data-ttu-id="1bda1-123">Записывает сообщения в журнал событий `Microsoft-Windows-Desired State Configuration/Analytic`.</span><span class="sxs-lookup"><span data-stu-id="1bda1-123">Writes messages to the `Microsoft-Windows-Desired State Configuration/Analytic` event log.</span></span>                                                                                               |
| <span data-ttu-id="1bda1-124">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="1bda1-124">**Package**</span></span>        | <span data-ttu-id="1bda1-125">Устанавливает или удаляет пакеты, используя **Аргументы** , **LogPath** , **ReturnCode** , другие параметры.</span><span class="sxs-lookup"><span data-stu-id="1bda1-125">Installs or uninstalls packages using **Arguments** , **LogPath** , **ReturnCode** , other settings.</span></span>                                                                                        |
| <span data-ttu-id="1bda1-126">**Реестр**</span><span class="sxs-lookup"><span data-stu-id="1bda1-126">**Registry**</span></span>       | <span data-ttu-id="1bda1-127">Управляет разделами и значениями реестра.</span><span class="sxs-lookup"><span data-stu-id="1bda1-127">Manages registry keys and values.</span></span>                                                                                                                                                        |
| <span data-ttu-id="1bda1-128">**Сценарий**</span><span class="sxs-lookup"><span data-stu-id="1bda1-128">**Script**</span></span>         | <span data-ttu-id="1bda1-129">Позволяет разрабатывать собственные блоки сценариев [get-test-set](../resources/get-test-set.md).</span><span class="sxs-lookup"><span data-stu-id="1bda1-129">Allows you to design your own [get-test-set](../resources/get-test-set.md) script blocks.</span></span>                                                                                                |
| <span data-ttu-id="1bda1-130">**Служба**</span><span class="sxs-lookup"><span data-stu-id="1bda1-130">**Service**</span></span>        | <span data-ttu-id="1bda1-131">Настраивает службы Windows.</span><span class="sxs-lookup"><span data-stu-id="1bda1-131">Configures Windows services.</span></span>                                                                                                                                                             |
| <span data-ttu-id="1bda1-132">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="1bda1-132">**User**</span></span>           | <span data-ttu-id="1bda1-133">Управляет локальными пользователями и атрибутами.</span><span class="sxs-lookup"><span data-stu-id="1bda1-133">Manages local users and attributes.</span></span>                                                                                                                                                      |
| <span data-ttu-id="1bda1-134">**WindowsFeature**</span><span class="sxs-lookup"><span data-stu-id="1bda1-134">**WindowsFeature**</span></span> | <span data-ttu-id="1bda1-135">Управляет ролями и функциями.</span><span class="sxs-lookup"><span data-stu-id="1bda1-135">Manages roles and features.</span></span>                                                                                                                                                              |
| <span data-ttu-id="1bda1-136">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="1bda1-136">**WindowsProcess**</span></span> | <span data-ttu-id="1bda1-137">Настраивает процессы Windows.</span><span class="sxs-lookup"><span data-stu-id="1bda1-137">Configures Windows processes.</span></span>                                                                                                                                                            |

<span data-ttu-id="1bda1-138">Ресурсы OOB обеспечивают обычным операциям хорошую отправную точку.</span><span class="sxs-lookup"><span data-stu-id="1bda1-138">The OOB resources allow a good starting point for common operations.</span></span> <span data-ttu-id="1bda1-139">Если ресурсы OOB не соответствуют вашим потребностям, вы можете написать свой собственный [Пользовательский ресурс](../resources/authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="1bda1-139">If the OOB resources do not meet your needs, you can write your own [Custom Resource](../resources/authoringResource.md).</span></span> <span data-ttu-id="1bda1-140">Прежде чем написать собственный ресурс для решения проблемы, вы должны просмотреть огромное количество уже созданных как Microsoft, так и сообществом PowerShell ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="1bda1-140">Before you write a custom resource to solve your problem, you should look through the vast number of DSC resources that have already been created by both Microsoft and the PowerShell community.</span></span>

<span data-ttu-id="1bda1-141">Ресурсы DSC можно найти как в [коллекции PowerShell](https://www.powershellgallery.com/), так и на [GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="1bda1-141">You can find DSC resources in both the [PowerShell Gallery](https://www.powershellgallery.com/) and [GitHub](https://github.com/).</span></span> <span data-ttu-id="1bda1-142">Вы также можете установить ресурсы DSC непосредственно из консоли PowerShell, используя [PowerShellGet](/powershell/module/powershellget/).</span><span class="sxs-lookup"><span data-stu-id="1bda1-142">You can also install DSC resources directly from the PowerShell console using [PowerShellGet](/powershell/module/powershellget/).</span></span>

## <a name="installing-powershellget"></a><span data-ttu-id="1bda1-143">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1bda1-143">Installing PowerShellGet</span></span>

<span data-ttu-id="1bda1-144">Чтобы определить, есть ли у вас **PowerShell** , или получить справку по его установке, см. руководство [Установка PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="1bda1-144">To determine if you already have **PowerShell** get, or to get help installing it, see the following guide: [Installing PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span>

## <a name="finding-dsc-resources-using-powershellget"></a><span data-ttu-id="1bda1-145">Поиск ресурсов DSC с помощью PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1bda1-145">Finding DSC resources using PowerShellGet</span></span>

<span data-ttu-id="1bda1-146">После установки **PowerShellGet** на компьютер, вы можете найти и установить ресурсы DSC, размещенные в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="1bda1-146">Once **PowerShellGet** is installed on your system, you can find and install DSC resources hosted in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

<span data-ttu-id="1bda1-147">Сначала используйте командлет [Find-DSCResource](/powershell/module/powershellget/find-dscresource), чтобы найти ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="1bda1-147">First, use the [Find-DSCResource](/powershell/module/powershellget/find-dscresource) cmdlet to find DSC resources.</span></span> <span data-ttu-id="1bda1-148">При первом запуске `Find-DSCResource` вы увидите следующую подсказку для установки "поставщика NuGet".</span><span class="sxs-lookup"><span data-stu-id="1bda1-148">When you run `Find-DSCResource` for the first time, you see the following prompt to install the "NuGet provider".</span></span>

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based
repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies'
or 'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install
the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201
-Force'. Do you want PowerShellGet to install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

<span data-ttu-id="1bda1-149">После нажатия "y" (установки поставщика NuGet) вы увидите список ресурсов DSC, которые вы можете установить из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bda1-149">After pressing 'y', the "NuGet" provider is installed, you see a list of DSC resources that you can install from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="1bda1-150">Список не отображается, поскольку очень велик.</span><span class="sxs-lookup"><span data-stu-id="1bda1-150">List is not shown because it is very large.</span></span>

<span data-ttu-id="1bda1-151">Вы также можете указать параметр `-Name`, используя подстановочные знаки, или параметр `-Filter` без подстановочных знаков, чтобы сузить область поиска.</span><span class="sxs-lookup"><span data-stu-id="1bda1-151">You can also specify the `-Name` parameter using wildcards, or `-Filter` parameter without wildcards to narrow down your search.</span></span> <span data-ttu-id="1bda1-152">В этом примере предпринимается попытка найти ресурс DSC TimeZone с использованием подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="1bda1-152">This example attempts to find a "TimeZone" DSC resource using the wildcards.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bda1-153">В настоящее время в командлете `Find-DSCResource` есть ошибка, которая не позволяет использовать подстановочные знаки в параметрах `-Name` и `-Filter`.</span><span class="sxs-lookup"><span data-stu-id="1bda1-153">Currently there is a bug in the `Find-DSCResource` cmdlet that prevents using wildcards in both the `-Name` and `-Filter` parameters.</span></span> <span data-ttu-id="1bda1-154">Во втором примере, поданном ниже, показано возможное решение с помощью `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="1bda1-154">The second example below shows a workaround using `Where-Object`.</span></span>

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

<span data-ttu-id="1bda1-155">Вы также можете использовать `Where-Object` для поиска ресурсов DSC с более детальной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="1bda1-155">You can also use `Where-Object` to find DSC resources with more granular filtering.</span></span> <span data-ttu-id="1bda1-156">Этот подход будет медленнее, чем использование встроенных параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="1bda1-156">This approach will be slower than using built in filtering parameters.</span></span>

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

<span data-ttu-id="1bda1-157">Дополнительные сведения о фильтрации см. в разделе [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="1bda1-157">For more information on filtering, see [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="installing-dsc-resources-using-powershellget"></a><span data-ttu-id="1bda1-158">Установка ресурсов DSC с помощью PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1bda1-158">Installing DSC Resources using PowerShellGet</span></span>

<span data-ttu-id="1bda1-159">Чтобы установить ресурс DSC, используйте командлет [Install-Module](/powershell/module/PowershellGet/Install-Module), указав имя модуля, отображаемого в имени **модуля** в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="1bda1-159">To install a DSC resource, use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet, specifying the name of the module shown under **Module** name in your search results.</span></span>

<span data-ttu-id="1bda1-160">Ресурс TimeZone существует в модуле ComputerManagementDSC, поэтому в этом примере устанавливается этот модуль.</span><span class="sxs-lookup"><span data-stu-id="1bda1-160">The "TimeZone" resource exists in the "ComputerManagementDSC" module, so that is the module this example installs.</span></span>

> [!NOTE]
> <span data-ttu-id="1bda1-161">Если коллекция PowerShell не является надежной, вы увидите предупреждение ниже с запросом подтверждения и указанием, как избежать последующих запросов при установке.</span><span class="sxs-lookup"><span data-stu-id="1bda1-161">If you have not trusted the PowerShell gallery, you see the warning below asking for confirmation, and instructing you how to avoid subsequent prompts on installs.</span></span>

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to
install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="1bda1-162">Нажмите "y", чтобы продолжить установку модуля.</span><span class="sxs-lookup"><span data-stu-id="1bda1-162">Press 'y' to continue installing the module.</span></span> <span data-ttu-id="1bda1-163">После установки вы можете проверить, установлен ли ваш новый ресурс, используя [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span><span class="sxs-lookup"><span data-stu-id="1bda1-163">After install, you can verify that your new resource is installed using [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span></span>

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="1bda1-164">Вы также можете просмотреть другие ресурсы в только что установленном модуле, указав параметр `-ModuleName`.</span><span class="sxs-lookup"><span data-stu-id="1bda1-164">You can also view other resources in your newly installed module, by specifying the `-ModuleName` parameter.</span></span>

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a><span data-ttu-id="1bda1-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1bda1-165">See also</span></span>

- [<span data-ttu-id="1bda1-166">Общие сведения о ресурсах</span><span class="sxs-lookup"><span data-stu-id="1bda1-166">What are Resources?</span></span>](../resources/resources.md)
