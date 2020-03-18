---
ms.date: 02/28/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 863898d910cc3c75c3e5977a5b6b0657ba7ed512
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278258"
---
# <a name="dsc-resources"></a><span data-ttu-id="69020-103">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="69020-103">DSC Resources</span></span>

> <span data-ttu-id="69020-104">Относится к Windows PowerShell 4.0 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="69020-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="69020-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="69020-105">Overview</span></span>

<span data-ttu-id="69020-106">Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="69020-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="69020-107">В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).</span><span class="sxs-lookup"><span data-stu-id="69020-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="69020-108">Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="69020-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="69020-109">Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="69020-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="69020-110">Каждый ресурс содержит \*схему, которая определяет синтаксис, используемый ресурсом при [конфигурации](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="69020-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="69020-111">Схема ресурса может быть определена следующими способами.</span><span class="sxs-lookup"><span data-stu-id="69020-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="69020-112">Файлом **Schema.Mof**. Большинство ресурсов определяют свою _схему_ в файле schema.mof с помощью [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="69020-112">**'Schema.Mof'** file: Most resources define their _schema_ in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="69020-113">Файлом **\<Имя ресурса\>.schema.psm1**. [Составные ресурсы](../configurations/compositeConfigs.md) определяют свою *схему* в файле <ResourceName>.schema.psm1 с помощью [блока параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="69020-113">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="69020-114">Файлом **\<Имя ресурса\>.psm1**. Ресурсы DSC, основанные на классе, определяют свою _схему_ в описании класса.</span><span class="sxs-lookup"><span data-stu-id="69020-114">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="69020-115">Элементы синтаксиса обозначаются как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="69020-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="69020-116">Дополнительные сведения см. в статье [About Classes and Desired State Configuration](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc) (О классах и настройке требуемого состояния).</span><span class="sxs-lookup"><span data-stu-id="69020-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="69020-117">Чтобы получить синтаксис из ресурса DSC, используйте командлет [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) вместе с параметром `-Syntax`.</span><span class="sxs-lookup"><span data-stu-id="69020-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="69020-118">Это похоже на использование командлета [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с параметром `-Syntax` для получения синтаксиса командлета.</span><span class="sxs-lookup"><span data-stu-id="69020-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="69020-119">В выходных данных будет показан шаблон, используемый в указанном блоке ресурса.</span><span class="sxs-lookup"><span data-stu-id="69020-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="69020-120">Выходные данные должны соответствовать выходным данным, приведенным ниже, так как в будущем этот ресурс может измениться.</span><span class="sxs-lookup"><span data-stu-id="69020-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="69020-121">Например, синтаксис командлета, для которого _ключи_ в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="69020-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="69020-122">Типы указывают типы данных для каждого ключа в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="69020-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="69020-123">Ключ **Ensure** является необязательным, так как Present является его значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69020-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

```output
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="69020-124">Блок ресурсов **Служба** внутри конфигурации может выглядеть следующим образом. Это необходимо, чтобы **убедиться**, что служба подсистемы печати работает.</span><span class="sxs-lookup"><span data-stu-id="69020-124">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="69020-125">Перед использованием ресурса в конфигурации его необходимо импортировать с помощью командлета [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="69020-125">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="69020-126">Конфигурации могут содержать несколько экземпляров одного типа ресурса.</span><span class="sxs-lookup"><span data-stu-id="69020-126">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="69020-127">Имя каждого экземпляра должно быть уникально.</span><span class="sxs-lookup"><span data-stu-id="69020-127">Each instance must be uniquely named.</span></span> <span data-ttu-id="69020-128">В следующем примере второй блок ресурсов **Служба** добавляется для настройки службы DHCP.</span><span class="sxs-lookup"><span data-stu-id="69020-128">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="69020-129">Начиная с PowerShell 5.0, Intellisense была включена в DSC.</span><span class="sxs-lookup"><span data-stu-id="69020-129">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="69020-130">Новая функция позволяет использовать клавиши <kbd>TAB</kbd> и <kbd>CTRL</kbd>+<kbd>ПРОБЕЛ</kbd> для автозаполнения имен ключей.</span><span class="sxs-lookup"><span data-stu-id="69020-130">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Нажатие клавиши TAB для заполнения ресурса](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="69020-132">Типы ресурсов</span><span class="sxs-lookup"><span data-stu-id="69020-132">Types of resources</span></span>

<span data-ttu-id="69020-133">В Windows имеются встроенные ресурсы. Кроме того, существуют ресурсы для ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="69020-133">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="69020-134">Имеются ресурсы для [межузловых зависимостей](../configurations/crossNodeDependencies.md), ресурсы для управления пакетами, а также [ресурсы, принадлежащие сообществу и поддерживаемые им](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="69020-134">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="69020-135">Шаги, описанные выше, можно использовать для определения синтаксиса этих ресурсов и способов их использования.</span><span class="sxs-lookup"><span data-stu-id="69020-135">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="69020-136">Страницы, на которых было описано использование этих ресурсов, собраны в разделе **Справочные материалы**.</span><span class="sxs-lookup"><span data-stu-id="69020-136">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="69020-137">Встроенные ресурсы Windows</span><span class="sxs-lookup"><span data-stu-id="69020-137">Windows built-in resources</span></span>

- [<span data-ttu-id="69020-138">Ресурс Archive</span><span class="sxs-lookup"><span data-stu-id="69020-138">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="69020-139">Ресурс Environment</span><span class="sxs-lookup"><span data-stu-id="69020-139">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="69020-140">Ресурс File</span><span class="sxs-lookup"><span data-stu-id="69020-140">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="69020-141">Ресурс Group</span><span class="sxs-lookup"><span data-stu-id="69020-141">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="69020-142">Ресурс GroupSet</span><span class="sxs-lookup"><span data-stu-id="69020-142">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="69020-143">Ресурс Log</span><span class="sxs-lookup"><span data-stu-id="69020-143">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="69020-144">Ресурс Package</span><span class="sxs-lookup"><span data-stu-id="69020-144">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="69020-145">Ресурс ProcessSet</span><span class="sxs-lookup"><span data-stu-id="69020-145">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="69020-146">Ресурс Registry</span><span class="sxs-lookup"><span data-stu-id="69020-146">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="69020-147">Ресурс Script</span><span class="sxs-lookup"><span data-stu-id="69020-147">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="69020-148">Ресурс Service</span><span class="sxs-lookup"><span data-stu-id="69020-148">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="69020-149">Ресурс ServiceSet</span><span class="sxs-lookup"><span data-stu-id="69020-149">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="69020-150">Ресурс User</span><span class="sxs-lookup"><span data-stu-id="69020-150">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="69020-151">Ресурс WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="69020-151">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="69020-152">Ресурс WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="69020-152">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="69020-153">Ресурс WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="69020-153">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="69020-154">Ресурс WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="69020-154">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="69020-155">Ресурс WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="69020-155">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="69020-156">Ресурс WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="69020-156">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="69020-157">Ресурсы межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="69020-157">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="69020-158">Ресурс WaitForAll</span><span class="sxs-lookup"><span data-stu-id="69020-158">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="69020-159">Ресурс WaitForSome</span><span class="sxs-lookup"><span data-stu-id="69020-159">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="69020-160">Ресурс WaitForAny</span><span class="sxs-lookup"><span data-stu-id="69020-160">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="69020-161">Ресурсы управления пакетами</span><span class="sxs-lookup"><span data-stu-id="69020-161">Package Management resources</span></span>

- [<span data-ttu-id="69020-162">Ресурс PackageManagement</span><span class="sxs-lookup"><span data-stu-id="69020-162">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="69020-163">Ресурс PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="69020-163">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="69020-164">Ресурсы Linux</span><span class="sxs-lookup"><span data-stu-id="69020-164">Linux resources</span></span>

- [<span data-ttu-id="69020-165">Ресурс Linux Archive</span><span class="sxs-lookup"><span data-stu-id="69020-165">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- <span data-ttu-id="69020-166">Ресурс [Linux Environment](../reference/resources/linux/lnxEnvironmentResource.md)</span><span class="sxs-lookup"><span data-stu-id="69020-166">[Linux Environment Resource](../reference/resources/linux/lnxEnvironmentResource.md)</span></span>
- [<span data-ttu-id="69020-167">Ресурс Linux FileLine</span><span class="sxs-lookup"><span data-stu-id="69020-167">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="69020-168">Ресурс Linux File</span><span class="sxs-lookup"><span data-stu-id="69020-168">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="69020-169">Ресурс Linux Group</span><span class="sxs-lookup"><span data-stu-id="69020-169">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="69020-170">Ресурс Linux Package</span><span class="sxs-lookup"><span data-stu-id="69020-170">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="69020-171">Ресурс Linux Script</span><span class="sxs-lookup"><span data-stu-id="69020-171">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="69020-172">Ресурс Linux Service</span><span class="sxs-lookup"><span data-stu-id="69020-172">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="69020-173">Ресурс Linux SshAuthorizedKeys</span><span class="sxs-lookup"><span data-stu-id="69020-173">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="69020-174">Ресурс Linux User</span><span class="sxs-lookup"><span data-stu-id="69020-174">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
