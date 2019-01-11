---
ms.date: 12/12/2018
keywords: DSC, powershell, ресурсов, в коллекции, программа установки
title: Установка дополнительных ресурсов DSC
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402907"
---
# <a name="install-additional-dsc-resources"></a><span data-ttu-id="b7efd-103">Установка дополнительных ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="b7efd-103">Install Additional DSC Resources</span></span>

<span data-ttu-id="b7efd-104">PowerShell включает несколько ресурсов Out of box для Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="b7efd-104">PowerShell includes several Out-of-the-box resources for Desired State Configuration (DSC).</span></span> <span data-ttu-id="b7efd-105">**PSDesiredStateConfiguration** модуль содержит все ресурсы DSC OOB, доступные в используемой определенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7efd-105">The **PSDesiredStateConfiguration** module contains all of the OOB DSC resources available on your specific instance of PowerShell.</span></span>

<span data-ttu-id="b7efd-106">Это список OOB ресурсы, включенные в PowerShell 4.0 и описание возможностей ресурса.</span><span class="sxs-lookup"><span data-stu-id="b7efd-106">This is a list of the OOB resources included in PowerShell 4.0 and a description of the resource's capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="b7efd-107">Это неполный список, поскольку количество ресурсов OOB выросло с каждой версией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7efd-107">This is an incomplete list, as the number of OOB resources has grown with each version of PowerShell.</span></span>

|<span data-ttu-id="b7efd-108">Ресурс</span><span class="sxs-lookup"><span data-stu-id="b7efd-108">Resource</span></span>  |<span data-ttu-id="b7efd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b7efd-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b7efd-110">**File**</span><span class="sxs-lookup"><span data-stu-id="b7efd-110">**File**</span></span>|<span data-ttu-id="b7efd-111">Управляет состоянием файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="b7efd-111">Controls the state of files and directories.</span></span> <span data-ttu-id="b7efd-112">Копирует файлы из **источника** для **назначения** и обновляет их при **источника** изменения, сравнивая даты, контрольные суммы и хэши.</span><span class="sxs-lookup"><span data-stu-id="b7efd-112">Copies files from a **Source** to a **Destination** and updates them when the **Source** changes by comparing dates, checksums, and hashes.</span></span>|
|<span data-ttu-id="b7efd-113">**Archive**</span><span class="sxs-lookup"><span data-stu-id="b7efd-113">**Archive**</span></span>|<span data-ttu-id="b7efd-114">Распаковывает архивы и указанное расположение.</span><span class="sxs-lookup"><span data-stu-id="b7efd-114">Unpacks archives and a specified location.</span></span> <span data-ttu-id="b7efd-115">Проверяет архивы с заданным **контрольной суммы**.</span><span class="sxs-lookup"><span data-stu-id="b7efd-115">Validates the archives with a specified **Checksum**.</span></span>|
|<span data-ttu-id="b7efd-116">**Environment**</span><span class="sxs-lookup"><span data-stu-id="b7efd-116">**Environment**</span></span>|<span data-ttu-id="b7efd-117">Управляет переменными среды.</span><span class="sxs-lookup"><span data-stu-id="b7efd-117">Manages environment variables.</span></span>|
|<span data-ttu-id="b7efd-118">**Группа**</span><span class="sxs-lookup"><span data-stu-id="b7efd-118">**Group**</span></span>|<span data-ttu-id="b7efd-119">Управляет локальными группами и контролирует членство в группе.</span><span class="sxs-lookup"><span data-stu-id="b7efd-119">Manages local groups and controls group membership.</span></span>|
|<span data-ttu-id="b7efd-120">**Log**</span><span class="sxs-lookup"><span data-stu-id="b7efd-120">**Log**</span></span>|<span data-ttu-id="b7efd-121">Записывает сообщения в `Microsoft-Windows-Desired State Configuration/Analytic` журнала событий.</span><span class="sxs-lookup"><span data-stu-id="b7efd-121">Writes messages to the `Microsoft-Windows-Desired State Configuration/Analytic` event log.</span></span>|
|<span data-ttu-id="b7efd-122">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="b7efd-122">**Package**</span></span>|<span data-ttu-id="b7efd-123">Устанавливает или удаляет пакеты с помощью **аргументы**, **LogPath**, **ReturnCode**, другие параметры.</span><span class="sxs-lookup"><span data-stu-id="b7efd-123">Installs or uninstalls packages using **Arguments**, **LogPath**, **ReturnCode**, other settings.</span></span>|
|<span data-ttu-id="b7efd-124">**Registry**</span><span class="sxs-lookup"><span data-stu-id="b7efd-124">**Registry**</span></span>|<span data-ttu-id="b7efd-125">Управляет разделы реестра и значения.</span><span class="sxs-lookup"><span data-stu-id="b7efd-125">Manages registry keys and values.</span></span>|
|<span data-ttu-id="b7efd-126">**Script**</span><span class="sxs-lookup"><span data-stu-id="b7efd-126">**Script**</span></span>|<span data-ttu-id="b7efd-127">Позволяет разрабатывать собственные [get теста set](../resources/get-test-set.md) блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="b7efd-127">Allows you to design your own [get-test-set](../resources/get-test-set.md) script blocks.</span></span>|
|<span data-ttu-id="b7efd-128">**Служба**</span><span class="sxs-lookup"><span data-stu-id="b7efd-128">**Service**</span></span>|<span data-ttu-id="b7efd-129">Настраивает службы Windows.</span><span class="sxs-lookup"><span data-stu-id="b7efd-129">Configures Windows services.</span></span>|
|<span data-ttu-id="b7efd-130">**User**</span><span class="sxs-lookup"><span data-stu-id="b7efd-130">**User**</span></span> |<span data-ttu-id="b7efd-131">Управляет локальными пользователями и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b7efd-131">Manages local users and attributes.</span></span>|
|<span data-ttu-id="b7efd-132">**WindowsFeature**</span><span class="sxs-lookup"><span data-stu-id="b7efd-132">**WindowsFeature**</span></span>|<span data-ttu-id="b7efd-133">Управляет ролей и компонентов.</span><span class="sxs-lookup"><span data-stu-id="b7efd-133">Manages roles and features.</span></span>|
|<span data-ttu-id="b7efd-134">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="b7efd-134">**WindowsProcess**</span></span>|<span data-ttu-id="b7efd-135">Настраивает процессов Windows.</span><span class="sxs-lookup"><span data-stu-id="b7efd-135">Configures Windows processes.</span></span>|

<span data-ttu-id="b7efd-136">Ресурсы OOB разрешить хорошей отправной точкой для выполнения распространенных операций.</span><span class="sxs-lookup"><span data-stu-id="b7efd-136">The OOB resources allow a good starting point for common operations.</span></span> <span data-ttu-id="b7efd-137">Если ресурсы OOB не удовлетворяют вашим потребностям, можно написать собственный [настраиваемый ресурс](../resources/authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="b7efd-137">If the OOB resources do not meet your needs, you can write your own [Custom Resource](../resources/authoringResource.md).</span></span> <span data-ttu-id="b7efd-138">Прежде чем писать настраиваемый ресурс решить проблему, при просмотре огромное число ресурсов DSC, которые уже были созданы корпорацией Майкрософт и сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7efd-138">Before you write a custom resource to solve your problem, you should look through the vast number of DSC resources that have already been created by both Microsoft and the PowerShell community.</span></span>

<span data-ttu-id="b7efd-139">Ресурсы DSC, можно найти в обоих [коллекции PowerShell](https://www.powershellgallery.com/) и [GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="b7efd-139">You can find DSC resources in both the [PowerShell Gallery](https://www.powershellgallery.com/) and [GitHub](https://github.com/).</span></span> <span data-ttu-id="b7efd-140">Ресурсы DSC также можно установить непосредственно из консоли PowerShell с помощью [PowerShellGet](/powershell/module/powershellget/).</span><span class="sxs-lookup"><span data-stu-id="b7efd-140">You can also install DSC resources directly from the PowerShell console using [PowerShellGet](/powershell/module/powershellget/).</span></span>

## <a name="installing-powershellget"></a><span data-ttu-id="b7efd-141">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b7efd-141">Installing PowerShellGet</span></span>

<span data-ttu-id="b7efd-142">Чтобы определить, есть ли у вас **PowerShell** получения, или Справка по его установке см. в статье в этом руководстве: [Установка PowerShellGet](/powershell/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="b7efd-142">To determine if you already have **PowerShell** get, or to get help installing it, see the following guide: [Installing PowerShellGet](/powershell/gallery/installing-psget).</span></span>

## <a name="finding-dsc-resources-using-powershellget"></a><span data-ttu-id="b7efd-143">Поиск ресурсов DSC с помощью PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b7efd-143">Finding DSC resources using PowerShellGet</span></span>

<span data-ttu-id="b7efd-144">Один раз **PowerShellGet** устанавливается на компьютере, можно найти и установить ресурсы DSC, размещенные в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="b7efd-144">Once **PowerShellGet** is installed on your system, you can find and install DSC resources hosted in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

<span data-ttu-id="b7efd-145">Во-первых, используйте [Find-DSCResource](/powershell/module/powershellget/find-dscresource) командлет, чтобы найти ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="b7efd-145">First, use the [Find-DSCResource](/powershell/module/powershellget/find-dscresource) cmdlet to find DSC resources.</span></span> <span data-ttu-id="b7efd-146">При запуске `Find-DSCResource` в первый раз появится приведенный ниже запрос на установку поставщика NuGet «».</span><span class="sxs-lookup"><span data-stu-id="b7efd-146">When you run `Find-DSCResource` for the first time, you see the following prompt to install the "NuGet provider".</span></span>

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

<span data-ttu-id="b7efd-147">После нажатия клавиши «y» «NuGet» поставщик установлен, отобразится список ресурсов DSC, которые можно установить из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7efd-147">After pressing 'y', the "NuGet" provider is installed, you see a list of DSC resources that you can install from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="b7efd-148">Список не отображается, поскольку очень велик.</span><span class="sxs-lookup"><span data-stu-id="b7efd-148">List is not shown because it is very large.</span></span>

<span data-ttu-id="b7efd-149">Можно также указать `-Name` с использованием подстановочных знаков, параметр или `-Filter` параметр без подстановочных знаков, чтобы сузить круг поиска.</span><span class="sxs-lookup"><span data-stu-id="b7efd-149">You can also specify the `-Name` parameter using wildcards, or `-Filter` parameter without wildcards to narrow down your search.</span></span> <span data-ttu-id="b7efd-150">В этом примере предпринимается попытка найти ресурс «Часовой пояс» DSC с использованием подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="b7efd-150">This example attempts to find a "TimeZone" DSC resource using the wildcards.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7efd-151">В настоящее время имеется ошибка в `Find-DSCResource` командлет, который предотвращает использование подстановочных знаков в обоих `-Name` и `-Filter` параметров.</span><span class="sxs-lookup"><span data-stu-id="b7efd-151">Currently there is a bug in the `Find-DSCResource` cmdlet that prevents using wildcards in both the `-Name` and `-Filter` parameters.</span></span> <span data-ttu-id="b7efd-152">Во втором примере ниже показано возможное решение с помощью `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="b7efd-152">The second example below shows a workaround using `Where-Object`.</span></span>

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

<span data-ttu-id="b7efd-153">Можно также использовать `Where-Object` для поиска ресурсов DSC с более детализированные фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b7efd-153">You can also use `Where-Object` to find DSC resources with more granular filtering.</span></span> <span data-ttu-id="b7efd-154">Этот подход будет медленнее, чем используя встроенные параметры фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b7efd-154">This approach will be slower than using built in filtering parameters.</span></span>

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

<span data-ttu-id="b7efd-155">Дополнительные сведения о фильтрации см. в разделе [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="b7efd-155">For more information on filtering, see [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="installing-dsc-resources-using-powershellget"></a><span data-ttu-id="b7efd-156">Установка ресурсов DSC с помощью PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b7efd-156">Installing DSC Resources using PowerShellGet</span></span>

<span data-ttu-id="b7efd-157">Для установки ресурсов DSC, используйте [Install-Module](/powershell/module/PowershellGet/Install-Module) командлет, указав имя модуля, отображается в поле **модуль** имя в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="b7efd-157">To install a DSC resource, use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet, specifying the name of the module shown under **Module** name in your search results.</span></span>

<span data-ttu-id="b7efd-158">Ресурс «Часовой пояс» существует в модуле «ComputerManagementDSC», чтобы он устанавливает модуль в этом примере.</span><span class="sxs-lookup"><span data-stu-id="b7efd-158">The "TimeZone" resource exists in the "ComputerManagementDSC" module, so that is the module this example installs.</span></span>

> [!NOTE]
> <span data-ttu-id="b7efd-159">Если в коллекции PowerShell не является доверенным, вы увидите предупреждение ниже запроса на подтверждение и инструкциями по избежать последующих запросов на устанавливает.</span><span class="sxs-lookup"><span data-stu-id="b7efd-159">If you have not trusted the PowerShell gallery, you see the warning below asking for confirmation, and instructing you how to avoid subsequent prompts on installs.</span></span>

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="b7efd-160">Нажмите клавишу «y», чтобы продолжить установку модуля.</span><span class="sxs-lookup"><span data-stu-id="b7efd-160">Press 'y' to continue installing the module.</span></span> <span data-ttu-id="b7efd-161">После установки, можно проверить, что установлен с помощью нового ресурса [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span><span class="sxs-lookup"><span data-stu-id="b7efd-161">After install, you can verify that your new resource is installed using [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span></span>

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

<span data-ttu-id="b7efd-162">Можно также просмотреть другие ресурсы в только что установленного модуля, указав `-ModuleName` параметра.</span><span class="sxs-lookup"><span data-stu-id="b7efd-162">You can also view other resources in your newly installed module, by specifying the `-ModuleName` parameter.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b7efd-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7efd-163">See also</span></span>

- [<span data-ttu-id="b7efd-164">Общие сведения о ресурсах</span><span class="sxs-lookup"><span data-stu-id="b7efd-164">What are Resources?</span></span>](../resources/resources.md)
